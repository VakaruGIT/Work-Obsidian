| **Functionality**                                                                                                                              |
| ---------------------------------------------------------------------------------------------------------------------------------------------- |
| For [plant] in [week/date range], summarize coverage by role (assigned headcount vs. required, if rules/messages exist).                       |
| Show days where Technician or Shift Lead minimums were not met and who was scheduled then.                                                     |
| Who is absent in [plant] during [date range], and what roles would they normally cover (main usage vs. scheduled usage)?                       |
| For [date], list available people in [plant] who can cover role [role/UsageID] (based on Usages), excluding those already scheduled or absent. |
| For [date], turn warnings into an actionable to-do list with candidate reassignments.                                                          |
| From pool [StatPooledCapaAssignment] in [plant], suggest reassignments to cover [role] shortages on [date], prioritizing matching Usages.      |
| List shifts where a person’s scheduled role (UsageID) differs from their main usage, in [date range].                                          |
| Find shifts in [plant] missing WorkCenter or Capacity where a CapacityID exists; flag for correction.                                          |
| If [personnel no] becomes absent on [date], propose a replan that maintains minimums, showing trade-offs and impacts on other roles.           |
| If we increase minimum [role] requirement to [X] on [date range], where do we have gaps and who could cover them?                              |
| Compute per-person utilization for [period] in [plant] (working W time vs. absent N time), and flag under/over-utilized resources.             |