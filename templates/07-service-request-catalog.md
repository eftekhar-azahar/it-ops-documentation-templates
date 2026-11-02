# Service Request Catalog: `<Service / Platform>`

Each request type has a fixed category, the information needed to start, the approvals required and a fulfilment target, so requests can be logged correctly the first time and measured consistently.

| Field | Value |
|---|---|
| Version | `<1.0>` · Effective `<YYYY-MM-DD>` |
| Owner | `<service owner>` |

## Catalog

| ID | Category | Request type | Information required | Approval | Fulfilment team | Target (business hours) |
|---|---|---|---|---|---|---|
| SR-ACC-01 | Access | New user account | Name, role, manager, systems | Line manager | L1 | `<8 h>` |
| SR-ACC-02 | Access | Role / permission change | User, current and new role, reason | Line manager + system owner | L1 | `<8 h>` |
| SR-ACC-03 | Access | Account disable (leaver) | User, last working day | HR / line manager | L1 | `<4 h>` |
| SR-CLD-01 | Cloud resource | New VM / ECS instance | Flavor, image, network, security group, owner, cost centre | Project owner | Cloud Ops | `<2 days>` |
| SR-CLD-02 | Cloud resource | Resize instance | Instance ID, new flavor, maintenance window | Project owner | Cloud Ops | `<1 day>` |
| SR-CLD-03 | Cloud resource | Security group rule | Source, destination, port, protocol, justification | Security | Cloud Ops | `<1 day>` |
| SR-CLD-04 | Cloud resource | Golden image update | Base image, packages, hardening baseline | Platform owner | Cloud Ops | `<3 days>` |
| SR-DAT-01 | Data | Report or data extract | Fields, filters, period, format, purpose | Data owner | L2 App Support | `<2 days>` |
| SR-DAT-02 | Data | Data correction | Record IDs, current and correct values, evidence | Business owner | L2 App Support | `<1 day>` |
| SR-INF-01 | Information | How-to / guidance | Question | None | L1 | `<4 h>` |

## Rules

1. A request that needs a configuration change to production is raised as a **change request**, not a service request.
2. The clock starts when all required information is received. Missing information moves the ticket to *Pending Customer* (clock stopped).
3. Requests not in this catalog are logged as `SR-OTH-00` and reviewed weekly for addition.
4. Categories are reviewed `<quarterly>`. Retire types with no requests in 6 months.
