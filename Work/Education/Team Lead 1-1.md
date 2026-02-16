---
Last Sync: 2026-01-30T14:21
Occurrence: Monthly
---
- Meeting Notes
    
    - 24.07.2025
        
        No home office for interns
        
        Pleased, somehow mentions that I need to race other consultants
        
        Gave Home office when really needed
        
    
    - 31.08.2025
        
        ![[attachments/image 32.png|image 32.png]]
        
    
    - 26.09.2025
        
        ösd b2 zertifikat
        
    

- Fischer Support
    
    # Goal
    
    Interactive finite scheduling where **moved operations pull their chain**, then **detach for detailed edits**, with **local repair**, **setup optimization**, **bottleneck focus**, and **work-center changes**.
    
    # Core principles (3 lines)
    
    - **Propagation on move:** Predecessors and successors follow to keep logic and dates.
    
    - **Detach after drop:** Immediately freeze all moved items; you can detail-schedule any one without another ripple.
    
    - **Local repair only:** Fix conflicts around the impacted resources; no global replan.
    
    # Interaction model — Selection → Propagation → Detach
    
    1. **Scope (before move):**
        
        `None` (only selected) • `Immediate predecessors and successors` (one hop) • `Full chain` • `Time-window chain` (within chosen dates)
        
    
    1. **Move:**
        
        **Rigid block** (keep internal gaps) or **Elastic cluster** (allow gaps within min–max lags).
        
    
    1. **Propagate:**
        
        Apply the same time delta to the chosen scope; enforce **min lag / max lag**; if violated, **insert buffers** (waiting time), don’t extend the scope.
        
    
    1. **Detach (after drop):**
        
        Freeze all moved ops; then **detail-schedule** any single operation (slot, resource, split) **without further propagation** unless you re-enable it.
        
    
    # Local repair (capacity + conflicts)
    
    Order of attempts (stop at first success):
    
    1. **Snap** to nearest free slot on the same machine (work center).
    
    1. **Nudge one neighbor** (cheapest side).
    
    1. **Alternative machine** (parallel resource with capability).
    
    1. **Split** across the conflict window (if allowed).
    
    1. If precedence would break, **insert a buffer**.
        
        **Finite capacity** must hold at commit (no overlaps).
        
    
    # Multi-select (any number)
    
    - Show a **dependency halo**; non-related ops are greyed out.
    
    - Group modes: **Rigid** (keep spacing) • **Elastic** (respect min–max lags) • **Free set** (move together now; independent in repair).
    
    - After drop: everything frozen; micro-adjust one op without moving others.
    
    # Bottleneck + setup (simple rules)
    
    - **Bottleneck-first** (the resource currently limiting throughput sequences first).
    
    - **Setup optimization:** Batch by **setup family** (same tool/material/parameters), then **earliest due date** inside the batch.
    
    - During local repair, **penalize breaking batches**; prefer solutions that keep batch integrity.
    
    # Defaults (predictable behavior)
    
    - Propagation: **Off after drop** (button: “Propagate chain” to re-enable).
    
    - Conflict resolution order: **Snap → Nudge → Alternative machine → Split → Buffer**.
    
    - Tie-breaks: pick **lowest cost** (lateness, setup change, number of operations moved, priority); if equal, sample among the **top few** (not pure random).
    
    # One-liner for stakeholders
    
    **“Move with chain-safe propagation, then detach for precise fixes—capacity-cleaned locally, setup-aware, bottleneck-led, and ready for released-order work-center changes.”**
    

- REFLECTION
    
    Main Problems:
    
    1. Didn’t take notes (too invested visually)
    
    1. Thought I understood everything when actually it was the opposite
    
    1. Didn’t know how to sell my solution (explanation)
    
    1. Visually present a process instead of showing notes or findings
    
    1. Stressed out when couldn’t find answer to question
    
    Solution to these problems:
    
    - Take notes on main problem (cause, possible solutions, expectations)
    
    - Ask questions during this process
    
    - Even if you think everything was crystal clear, ask if this what the person meant
    
    - Create Mockups or visually represent your idea instead of just talking
    
    - Keep calm and try to understand why the person doesn’t get what you are explaining
    

- Tips
    
    - Systemzugriff Tip
        
        SE16N SPRO PFCG ST22 STMS Checken
        
        We need access to see if there are any problems when transports are sent
        
        Check installed system versions and installation number
        
        Column specification
        
        Rüstoptimierung (check about it, setup groups)
        
        Setup Matrix
        
        conOS optimizer
        
        Aufnehmen (to record)
        
        check which time frame did they talk about the extension
        
        slides update (put the product team)
        
    

- HJG
    
    1. Flexibilitate home-office
        
        1. am observat ca sunt zile in care agenda mea nu include meet-uri sau colaborari intensive in echipa, iar prezenta nu aduce in plus de valoare procesului. Cand am avut interviul acum un an, am discutat ca dupa ce o sa ma obisnuiesc voi avea posibil home office. Consider ca sunt integrat si as vrea sa stabilim daca pot sa lucrez home office pentru restul lunii februarie inainte de a incepe part-time. As putea sa mi optimizez si timpul de livrare in acest sens
        
    
    1. Flexibilitatea orelor (Work-life)
        
        1. Sunt dedicat sa termin task urile la timp, chiar daca asta inseamna ore suplimentare, mi as dori ca acest efort sa fie echilibrat, printr o flexibilitate crescuta in zilele urmatoare care imi permite sa continui munca de acasa sau sa ajustez programul pentru a mentine ritmul de lucru sustenabil
        
    
    1. Hands-on data science
        
        1. Sunt pasionat de data science si ai. Daca munca actuala este doar teoretica sau administrativa, doresc implicare tehnica
        
          
        
          
        
    

- HJG DE
    
    - **Home-Office und Produktivität:** Da ich mittlerweile voll integriert bin, habe ich festgestellt, dass meine Effizienz bei Fokus-Aufgaben an Tagen ohne Meetings im Home-Office deutlich höher ist. Ich schlage vor, für den Rest des Februars verstärkt remote zu arbeiten. Dies würde es mir ermöglichen, meine Lieferzeiten vor dem Wechsel in die Teilzeit noch einmal zu optimieren.
    
    - **Flexibilität und Nachhaltigkeit:** Es ist für mich selbstverständlich, Aufgaben termingerecht abzuschließen, auch wenn dies gelegentlich Überstunden erfordert. Um langfristig ein nachhaltiges Arbeitstempo beizubehalten, wünsche ich mir die Flexibilität, meine Arbeitszeiten nach solchen Spitzenbelastungen eigenverantwortlich anzupassen.
    
    - **Technischer Fokus (Data Science):** Da meine Leidenschaft im Bereich AI und Data Science liegt, strebe ich eine stärkere technische Einbindung an. Ich möchte meine Fähigkeiten gerne „hands-on“ in unsere Projekte einbringen, um über administrative Aufgaben hinaus einen messbaren Mehrwert zu schaffen.