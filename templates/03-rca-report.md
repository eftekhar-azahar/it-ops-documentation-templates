# Root Cause Analysis (RCA): `<PRB number>`

| Field | Value |
|---|---|
| Related incidents | `<INC numbers>` |
| Service | `<service>` |
| RCA owner | `<name, team>` |
| Participants | `<names / teams>` |
| Date of analysis | `<YYYY-MM-DD>` |
| Status | `<Draft / Under review / Approved>` |

## 1. Problem statement

`<What happened, when, how often, measured impact. One paragraph, facts only, no blame.>`

## 2. Evidence reviewed

- `<logs, monitoring graphs, change records, configuration diffs, vendor tickets>`

## 3. Five whys

| # | Why? | Answer | Evidence |
|---|---|---|---|
| 1 | Why did the service fail? | | |
| 2 | Why did that happen? | | |
| 3 | Why? | | |
| 4 | Why? | | |
| 5 | Why? (root cause) | | |

## 4. Contributing factors

| Category | Factor | Contributed? |
|---|---|---|
| People / process | e.g. step missing from SOP, handover gap | `<Y/N + note>` |
| Technology | e.g. capacity limit, defect, single point of failure | |
| Change | e.g. recent deployment or config change | |
| Monitoring | e.g. no alert, alert threshold too late | |
| Third party | e.g. vendor outage, contract limit | |

## 5. Root cause

`<One or two sentences. The cause that, if removed, prevents recurrence.>`

## 6. Corrective and preventive actions (CAPA)

| # | Type | Action | Owner | Due | Status | Ticket |
|---|---|---|---|---|---|---|
| 1 | Corrective (fix this instance) | | | | Open | |
| 2 | Preventive (stop recurrence) | | | | Open | |
| 3 | Detection (catch it earlier) | | | | Open | |

## 7. Verification

- **How we will know it worked:** `<metric, e.g. zero repeats in 60 days; alert fires at 80% instead of 100%>`
- **Review date:** `<YYYY-MM-DD>`

## 8. Approval

| Role | Name | Date | Decision |
|---|---|---|---|
| Problem Manager | | | |
| Service owner | | | |
| Customer representative | | | |
