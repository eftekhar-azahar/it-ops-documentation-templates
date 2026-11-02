# Incident Report: `<INC number>`

| Field | Value |
|---|---|
| Title | `<one line: what failed, for whom>` |
| Priority | `<P1–P4>` · Impact `<H/M/L>` · Urgency `<H/M/L>` |
| Service / CI | `<service, component>` |
| Status | `<Resolved / Monitoring / Open>` |
| Incident Manager | `<name>` |
| Report author / date | `<name>` · `<YYYY-MM-DD>` |

## 1. Summary

`<3–4 sentences a manager can read alone: what happened, who was affected, how long, how it was fixed, whether it can recur.>`

## 2. Impact

| Item | Value |
|---|---|
| Users / customers affected | `<number or scope>` |
| Business functions affected | `<e.g. bill payment, top-up>` |
| Start of impact | `<YYYY-MM-DD HH:MM>` |
| End of impact | `<YYYY-MM-DD HH:MM>` |
| Total duration | `<h:mm>` |
| SLA outcome | `<MET / NOT MET>` (target `<x h>`, actual `<y h>`, paused `<z min>`) |

## 3. Timeline (local time)

| Time | Event | By |
|---|---|---|
| `<HH:MM>` | Alert received / user report | `<monitoring tool / caller>` |
| `<HH:MM>` | Ticket logged, priority set to `<Px>` | L1 |
| `<HH:MM>` | Escalated to `<L2 team>`: `<reason>` | L1 |
| `<HH:MM>` | Bridge call opened (P1/P2) | Incident Manager |
| `<HH:MM>` | Cause identified: `<short>` | L2 |
| `<HH:MM>` | Fix / workaround applied: `<what>` | L2/L3 |
| `<HH:MM>` | Service confirmed restored by `<user / monitoring>` | |
| `<HH:MM>` | Ticket resolved | |

## 4. Diagnosis and resolution

- **Symptoms:** `<errors, alerts, user reports>`
- **Immediate cause:** `<what broke>`
- **Fix applied:** `<exact action, change number if any>`
- **Workaround used (if any):** `<what users did meanwhile>`

## 5. Root cause

`<Known / Under investigation in PRB <number>>`. Full analysis: see the RCA report.

## 6. Follow-up actions

| # | Action | Owner | Due | Ticket |
|---|---|---|---|---|
| 1 | | | | |
| 2 | | | | |

## 7. Communication log

| Time | Audience | Channel | Message summary |
|---|---|---|---|
| | | | |
