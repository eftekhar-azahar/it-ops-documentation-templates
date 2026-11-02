# Priority and Escalation Matrix

| Field | Value |
|---|---|
| Service / contract | `<service name>` |
| Version | `<1.0>` · Effective `<YYYY-MM-DD>` |
| Owner | `<service delivery manager>` |
| Approved by | `<name, role>` |

## 1. Priority = Impact × Urgency

| Impact ↓ / Urgency → | **High**: no workaround, business stopped | **Medium**: workaround exists | **Low**: can wait |
|---|---|---|---|
| **High**: whole service, many users, revenue or safety | **P1** | **P2** | **P3** |
| **Medium**: one site, function or user group | **P2** | **P3** | **P3** |
| **Low**: single user, cosmetic | **P3** | **P4** | **P4** |

Examples to agree with the customer:

- **P1:** payment or billing service down for all users; data loss; security breach in progress
- **P2:** service degraded (slow, intermittent) for many users; a critical batch job failed
- **P3:** one feature failing with a workaround; one site affected
- **P4:** single-user issue, how-to question, cosmetic defect

## 2. Response and resolution targets

| Priority | Clock | First response | Update frequency | Resolution target |
|---|---|---|---|---|
| P1 | 24×7 | `<15 min>` | every `<30 min>` | `<4 h>` |
| P2 | 24×7 | `<30 min>` | every `<2 h>` | `<8 h>` |
| P3 | Business hours | `<2 h>` | daily | `<3 business days>` |
| P4 | Business hours | `<4 h>` | on change | `<5 business days>` |

Business hours: `<Sun–Thu 09:00–18:00, excluding public holidays>`. Time in *Pending Customer* status stops the resolution clock.

## 3. Functional escalation (who works it)

| Level | Team | Takes over when |
|---|---|---|
| L1 | `<Service Desk / NOC>` | All tickets start here: logging, triage, known fixes |
| L2 | `<Application Support / Cloud Operations>` | No known fix within `<30 min>` (P1/P2) or `<4 h>` (P3/P4) |
| L3 | `<Platform Engineering / Development>` | Code, configuration or infrastructure change needed |
| Vendor | `<vendor name, contract ID>` | Fault in third-party product; raise per vendor SLA |

## 4. Hierarchical escalation (who is informed)

| Elapsed vs resolution target | P1 | P2 | P3 / P4 |
|---|---|---|---|
| On logging | Shift lead + Incident Manager | Shift lead | — |
| 50% | Service Delivery Manager | Incident Manager | — |
| 75% | Head of Operations + customer contact | Service Delivery Manager | Team lead |
| 100% (breach) | Account / Head of Service | Head of Operations | Service Delivery Manager |

## 5. Contacts

| Role | Name | Phone | Email | Hours |
|---|---|---|---|---|
| Shift lead | | | | 24×7 rota |
| Incident Manager | | | | |
| Service Delivery Manager | | | | |
| Customer escalation contact | | | | |
| Vendor support | | | | |

## 6. Rules

1. Priority is set at logging and may be changed only by the Incident Manager, with the reason recorded on the ticket.
2. Every escalation is recorded on the ticket: time, from, to, reason.
3. A P1 opens a bridge call within `<15 min>` and gets a major-incident report within `<2 business days>`.
4. This matrix is reviewed `<every 6 months>` or after any P1.
