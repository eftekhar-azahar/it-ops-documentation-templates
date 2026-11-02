# Change Request (RFC): `<CR number>`

| Field | Value |
|---|---|
| Title | `<what is changing, where>` |
| Change type | `<Standard / Normal / Emergency>` |
| Requested by | `<name, team>` · `<YYYY-MM-DD>` |
| Implementer | `<name, team>` |
| Services / CIs affected | `<list>` |
| Related tickets | `<INC / PRB / SR numbers>` |

## 1. Reason for change

`<Business or technical reason. What happens if we don't do it.>`

## 2. Description

`<What will be done, step by step summary. Detailed steps go in section 6.>`

## 3. Risk and impact assessment

| Question | Answer |
|---|---|
| Downtime required? | `<None / x minutes>` |
| Users affected during change | `<scope>` |
| Risk level | `<Low / Medium / High>` |
| What could go wrong | `<main risks>` |
| How we would notice | `<monitoring, checks>` |
| Tested in non-production? | `<Yes, where / No, why>` |

## 4. Schedule

| Item | Value |
|---|---|
| Planned start | `<YYYY-MM-DD HH:MM>` |
| Planned end | `<YYYY-MM-DD HH:MM>` |
| Rollback decision point | `<time by which go/no-go is called>` |
| Freeze-period conflict? | `<None / details>` |

## 5. Pre-checks

- [ ] Backup / snapshot taken: `<what, where>`
- [ ] Monitoring baseline recorded
- [ ] Stakeholders notified `<x hours>` before
- [ ] Access and credentials confirmed

## 6. Implementation steps

| # | Step | Expected result | Done |
|---|---|---|---|
| 1 | | | |
| 2 | | | |

## 7. Validation (post-implementation test)

| # | Test | Expected | Result |
|---|---|---|---|
| 1 | | | `<Pass/Fail>` |

## 8. Rollback plan

| # | Step | Time needed |
|---|---|---|
| 1 | | |

Rollback is triggered if: `<criteria>`.

## 9. Approvals (CAB)

| Role | Name | Decision | Date |
|---|---|---|---|
| Change Manager | | `<Approved / Rejected>` | |
| Service owner | | | |
| Customer | | | |

## 10. Closure

| Field | Value |
|---|---|
| Actual start / end | |
| Outcome | `<Successful / Successful with issues / Failed – rolled back>` |
| Incidents caused | `<None / INC numbers>` |
| Implemented within approved window? | `<Yes / No>` |
