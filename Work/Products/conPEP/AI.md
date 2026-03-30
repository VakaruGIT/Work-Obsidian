- Who people are and what they can do: name, role(s), main/secondary usages, pooled vs fixed work center, entry/leaving dates, active status.  
- When/where they work: shift date, start/end/break, role used in that shift, work center/capacity, utilization, origin (HR vs manual).  
- What’s wrong: per‑day ShiftMessages (e.g., “minimum 1 Technician/Shift Lead missing”) to drive gap resolution.  
- Availability signals: absences (UsageID 00000099), pooled capacity (StatPooledCapaAssignment), cross‑skills (multiple Usages).  
  
Quick‑win lookup use cases  
- “Who is working in Plant 1010 this week by role?”  
- “Show Bruce Banner’s shifts next week” or “Where is Bruce assigned on 01.01.2026?”  
- “List all Technicians who are active and not absent on 12.01.2026 early shift.”  
- “Who has Shift Leader capability?” (UsageID ‘00000012’)  
- “Show staffing for Work Center WELDSET from 01.01–09.01.2026.”  
- “Which people are in pool POOL02 and available today?”  
  
Exception handling and gap fixing  
- Understaffed shift resolution:  
- Detect warnings in to_ShiftMessages (e.g., missing Technician/Shift Lead).  
- Suggest candidates: cross‑skilled staff (Usages), not absent, not already scheduled, with pooled or relevant work center capability.  
- Propose an assignment and ask for confirmation; then write back as a manual shift (DataOrigin=MANUAL).  
- Example: “We’re missing a Technician on 12.01.2026 early shift. Propose top 3 options to cover.”  
- Absence backfill:  
- “Alphonso Davies is absent 26–30.01.2026 late shift. Who can backfill as Operator or Technician from the pool?”  
- Double‑booking/over‑utilization check:  
- Flag if a person is assigned overlapping times or multiple 100% utilizations in the same time window.  
- HR vs manual override audit:  
- “Show shifts created manually last 7 days and their impact on warnings.”  
  
Planning support and “what‑if”  
- Shift building assistant:  
- “Build an early‑shift roster for 13.01.2026 that satisfies 1 Technician and 1 Shift Lead minimum.”  
- What‑if simulation before writing:  
- “If I move Steven Rogers (POOL02) to SING_ACT on 12.01.2026 as Technician, will warnings clear?”  
- Cross‑skill deployment:  
- “Find Operators who can act as Technician for next week’s nights.”  
- Pooled capacity allocation:  
- “Distribute POOL02 staff to cover all 3 packaging work centers tomorrow, meet min roles, minimize manual overrides.”  
- Work center continuity:  
- “Keep WELDSET staffed at 100% Operator coverage this week; propose swaps that avoid absences.”  
  
Proactive alerts and summaries  
- Daily staffing digest to team leads:  
- “At 15:00, send tomorrow’s gaps: missing Technician/Shift Lead by plant/work center, with 3 best candidates to fix.”  
- Real‑time alerts on change:  
- “Notify when any early shift flips from HR to MANUAL or when a new absence creates a coverage gap.”  
- KPI rollups:  
- “How many warning messages did we have per day last week?” “Trend of Technician gaps in Feb.”  
  
Employee self‑service  
- “When am I working next week?” “Which work center am I assigned to tomorrow?”  
- “Who is my shift lead on Friday?” (Find someone with ‘Shift Leader’ usage on that shift.)  
- “Can I swap my 02.01.2026 early shift? Show compatible teammates.”  
  
Data quality and governance helpers  
- “List persons with missing email or image” (field completeness).  
- “Flag shifts with breakTime = 0 where policy expects 1800 seconds.”  
- “Show active persons with EntryDate in the future or past LeavingDate.”  
  
Example end‑to‑end flows  
- Fix a minimum‑role gap:  
- Bot: “12.01.2026 Early shift has no Technician.” → Suggests Alphonso (Technician, not absent) or Steven (pool) → On approval, creates a manual Technician shift → Rechecks warnings → Confirms gap resolved.  
- Absence impact and backfill:  
- Bot: “Alphonso absent 26–30.01 late shift; Warnings expected at COSPAC01.” → Suggests cross‑skilled Operators or pool resources → Writes assignments on approval → Sends summary.  
- HR vs Manual audit:  
- Bot lists all MANUAL shifts created this week, the warnings they cleared, and any new overlaps introduced.  
  
Sample prompts to publish for users  
- “Who’s on the early shift in Plant 1010 on 13.01.2026 by role?”  
- “Do we meet minimum roles tomorrow? If not, fix them.”  
- “Find available Technicians not assigned or absent on 14.01.2026 06:00–14:00.”  
- “Assign Steven Rogers from POOL02 to WELDSET as Operator on 02.01.2026 early shift.”  
- “Show all manual shifts in the last 7 days and their creators.”  
- “Where is Bruce Banner scheduled this month? Any manual overrides?”  
- “Summarize all shift warnings next week by day and work center.”  
- “Which Operators can also act as Technician?”  
- “How many Technician hours are planned for February in Plant 1010?”  
- “Send me a daily 16:00 alert of uncovered shifts for tomorrow.”  
  
Implementation tips  
- Use OData filtering/expansion to pull Shifts with to_ShiftMessages for a date range and plant.  
- Build a fast availability finder: for a given time window and role, exclude absences (UsageID 00000099), exclude already‑scheduled persons, prefer main usage match, then secondary usage, then pool.  
- Respect role‑based access: personal schedules vs global rosters