# IT Ops Documentation Templates

![markdown](https://img.shields.io/badge/format-Markdown-000000?logo=markdown)
![license](https://img.shields.io/badge/license-MIT-blue)

Ready-to-use templates for IT service management and operations teams: priority and escalation, incidents, root cause analysis, change requests, monthly SLA reporting, SOPs, a service request catalog and shift handover.

They are written in plain Markdown, so they work in GitHub, Confluence, Notion, a wiki or a ticket's description field, and they convert to Word or PDF with any Markdown tool.

## Templates

| # | Template | Use it for | Process |
|---|---|---|---|
| 01 | [Priority and escalation matrix](templates/01-priority-and-escalation-matrix.md) | Impact × urgency → priority; response/resolution targets; functional and hierarchical escalation | Incident Management |
| 02 | [Incident report](templates/02-incident-report.md) | Summary, impact, timeline, resolution and follow-ups for a P1/P2 | Incident Management |
| 03 | [RCA report](templates/03-rca-report.md) | Five whys, contributing factors, CAPA, verification, approval | Problem Management |
| 04 | [Change request (RFC)](templates/04-change-request.md) | Risk, schedule, pre-checks, steps, validation, rollback, CAB approval, closure | Change Management |
| 05 | [Monthly SLA report](templates/05-sla-monthly-report.md) | Compliance by type and priority, breaches, waivers and disputes, trends, sign-off | Service Level Management |
| 06 | [SOP](templates/06-sop-template.md) | Step-by-step operational procedure with expected results and escalation | Operations |
| 07 | [Service request catalog](templates/07-service-request-catalog.md) | Request types, required information, approvals, fulfilment targets | Request Fulfilment |
| 08 | [Shift handover](templates/08-shift-handover.md) | NOC / 24×7 handover: open P1/P2, near-breach tickets, changes, pending items | Operations |

See them in use: [worked example: incident report + RCA](examples/example-incident-and-rca.md) (fictional scenario).

## How the templates fit together

```
Alert / user report
      │
      ▼
Priority matrix (01) ──► Incident (02) ──► resolved ──► SLA report (05)
      │                       │
      │                       └── recurring or P1 ──► RCA (03) ──► CAPA ──► Change request (04)
      │
      └── request, not a fault ──► Service request catalog (07)

SOPs (06) are linked from tickets; shift handover (08) carries open work across shifts.
```

## Conventions

- `<angle brackets>` mark text to replace; example values show the expected format.
- Times are local, `YYYY-MM-DD HH:MM`.
- SLA rules used throughout: customer-pending time stops the clock; waived tickets are excluded from the compliance base; compliance = Met ÷ (Met + Not met).

## Related projects

- [sla-calculation-engine](https://github.com/eftekhar-azahar/sla-calculation-engine): calculates the numbers for template 05 from a ticket export
- [sql-operations-toolkit](https://github.com/eftekhar-azahar/sql-operations-toolkit): PostgreSQL views and functions for SLA, MTTR/MTBF and backlog reporting
- [bash-ops-scripts](https://github.com/eftekhar-azahar/bash-ops-scripts): health checks and log triage used during incidents

## Author

**Md. Eftekhar Azahar**, Cloud PaaS Engineer (Cloud Managed Services). [GitHub](https://github.com/eftekhar-azahar) · [LinkedIn](https://www.linkedin.com/in/eftekhar-azahar)
