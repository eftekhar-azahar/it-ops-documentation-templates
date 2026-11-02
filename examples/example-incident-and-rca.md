# Worked example: Incident report + RCA

> Fictional scenario for demonstration. "ShopPay" and all names, numbers and times are invented.

---

## Incident Report: INC-2610-0042

| Field | Value |
|---|---|
| Title | ShopPay payment API timing out for all card payments |
| Priority | P1 · Impact High · Urgency High |
| Service / CI | ShopPay Payments · payment-api, payments-db |
| Status | Resolved |
| Incident Manager | Duty Incident Manager |
| Report author / date | L2 Application Support · 2026-10-31 |

### 1. Summary

From 09:02 to 10:14 on 30 October, card payments in the ShopPay app failed or timed out for most users. The payment API's database connection pool was exhausted because a reporting job deployed the night before held connections open. Rolling back the job's schedule and restarting the API restored service. A problem record (PRB-2610-0007) tracks the permanent fix.

### 2. Impact

| Item | Value |
|---|---|
| Users affected | ~70% of payment attempts failed |
| Business functions | Card payments, wallet top-up |
| Start / end of impact | 2026-10-30 09:02 / 10:14 |
| Total duration | 1:12 |
| SLA outcome | MET (target 4 h, actual 1 h 12 min, paused 0) |

### 3. Timeline

| Time | Event | By |
|---|---|---|
| 09:02 | Monitoring alert: payment API p95 latency > 30 s | Monitoring |
| 09:06 | Ticket logged as P1 | L1 NOC |
| 09:10 | Escalated to L2 Application Support: no known fix | L1 NOC |
| 09:15 | Bridge call opened | Incident Manager |
| 09:31 | Logs show `DB connection pool exhausted (active=50, max=50)` | L2 |
| 09:44 | Pool held by new nightly reporting job (CR-2610-0019) | L2 |
| 09:58 | Job disabled under emergency change CR-2610-0021; API restarted | L3 |
| 10:14 | Payments succeeding; error rate back to baseline | Monitoring |
| 10:40 | Ticket resolved after 25 min stable | Incident Manager |

### 4. Diagnosis and resolution

- **Symptoms:** payment timeouts, `OutOfMemoryError` on one worker, connection-pool errors
- **Immediate cause:** reporting job opened 45 long-running connections at 09:00, leaving the API 5
- **Fix applied:** job disabled (CR-2610-0021), payment-api restarted
- **Workaround:** none; wallet balance payments unaffected

---

## RCA: PRB-2610-0007

### Five whys

| # | Why? | Answer |
|---|---|---|
| 1 | Why did payments fail? | The API could not get database connections. |
| 2 | Why? | A reporting job held 45 of the 50 pooled connections. |
| 3 | Why did a reporting job use the payment pool? | It was configured with the payment-api database user and pool. |
| 4 | Why wasn't that caught? | The change review checked the SQL, not the connection settings. |
| 5 | Why? (root cause) | The change template has no question on shared resources (pools, quotas, credentials). |

**Root cause:** reporting workloads can share production connection pools because change reviews don't check shared-resource use.

### CAPA

| # | Type | Action | Owner | Due | Status |
|---|---|---|---|---|---|
| 1 | Corrective | Move reporting job to read replica with its own user and pool | L3 Platform | 2026-11-07 | Open |
| 2 | Preventive | Add "shared resources used?" to the change request template | Change Manager | 2026-11-05 | Open |
| 3 | Detection | Alert at 80% pool usage instead of on exhaustion | Cloud Ops | 2026-11-04 | Open |

**Verification:** no pool-exhaustion events in 60 days; alert tested by load test before closure.
