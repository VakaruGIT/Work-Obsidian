Coverage and compliance (ensure minimum staffing and detect gaps)  
- List all shifts in [plant] between [start date] and [end date] that have staffing warnings, grouped by date and role. Function: compliance check using ShiftMessages.  
- For [plant] in [week/date range], summarize coverage by role (assigned headcount vs. required, if rules/messages exist). Function: gap analysis.  
- Show days where Technician or Shift Lead minimums were not met and who was scheduled then. Function: fast shortage triage.  
  
Absences and availability  
- Who is absent in [plant] during [date range], and what roles would they normally cover (main usage vs. scheduled usage)? Function: absence impact assessment.  
- For [date], list available people in [plant] who can cover role [role/UsageID] (based on Usages), excluding those already scheduled or absent. Function: backfill candidate list.  
- Show absence rates by week for [plant], split by role. Function: availability KPI.  
  
Work center and pool allocation  
- For work center [WorkCenter] in [date range], list assigned people, capacity utilization, and data origin (HR vs MANUAL). Function: allocation visibility and audit.  
- From pool [StatPooledCapaAssignment] in [plant], suggest reassignments to cover [role] shortages on [date], prioritizing matching Usages. Function: pool-to-demand rebalancing.  
- Find shifts in [plant] missing WorkCenter or Capacity where a CapacityID exists; flag for correction. Function: data quality and allocation integrity.  
  
Role/skill alignment and flexibility  
- List shifts where a person’s scheduled role (UsageID) differs from their main usage, in [date range]. Function: cross-skilling visibility and risk control.  
- Show people who have worked outside their main usage more than [X] days in [period]. Function: capability breadth/training planning.  
- For role [role], rank people by recent days worked in that role in [period]. Function: practical proficiency proxy.  
  
Utilization, load balancing, and KPIs  
- Compute per-person utilization for [period] in [plant] (working W time vs. absent N time), and flag under/over-utilized resources. Function: workload balancing.  
- Aggregate capacity utilization by role and work center per day for [period]. Function: daily load overview.  
- Provide a weekly staffing heatmap (roles x weekdays) for [plant]. Function: pattern spotting and smoothing.  
  
Shift program and pattern analytics  
- Break down shifts by ShiftID/ShiftText used in [period], with headcount and hours. Function: program adoption and planning.  
- Show start/end/break distributions by shift program to spot anomalies. Function: schedule consistency audit.  
  
Rule/alert management  
- Summarize all open rule warnings from ShiftMessages in [period], grouped by rule (e.g., “min 1 Technician”), with trend over time. Function: rule adherence tracking.  
- For [date], turn warnings into an actionable to-do list with candidate reassignments. Function: guided remediation.  
  
Data integrity and governance  
- Find persons in [plant] missing key master data (email, image, qualifications not loaded), or with inconsistent static vs. scheduled assignments. Function: master-data hygiene.  
- Detect shifts with zero or malformed capacity utilization values. Function: transactional data quality.  
  
Reporting and export  
- Generate a roster summary for [plant]/[work center]/[personnel no] for [period] as CSV or JSON. Function: downstream reporting.  
- Produce an iCal/ICS calendar for [personnel no] for [period]. Function: personal scheduling.  
  
What-if and replanning  
- If [personnel no] becomes absent on [date], propose a replan that maintains minimums, showing trade-offs and impacts on other roles. Function: contingency planning.  
- If we increase minimum [role] requirement to [X] on [date range], where do we have gaps and who could cover them? Function: scenario analysis.  
