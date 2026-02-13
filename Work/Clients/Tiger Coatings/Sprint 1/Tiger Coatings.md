---
Last Sync: 2026-02-11T10:19
---
- [[#Phase 1]]
- [[#Phase 2]]
- [[#Phase 3]]

## Phase 1

- Documentation
    
    Timeline
    
    - conOS in D01
    
    - we can move faster (trainings, anfang november, 3 viertel december) possible timeline proposed by ishak
    
    - if everything in AT works fine, it shouldnt be bad in other countries
    
    - 31 december in austria
    
    - januar ausrollen 2 weeks for each plant
    
    - Start with Austira, then mexico, canada, china
    
    - how they want to be trained (key user) 5 people
    
    Roles
    
    - Production Plannung (EU)
        
        - Mario THOMAS (IT MANAGEMENT)
        
        Reinhard Transporte
        
        Lanser Georg
        
        Johannes mayer (fachlieken seite)
        
        ![[attachments/image 26.png|image 26.png]]
        
        ![[attachments/image 1 5.png|image 1 5.png]]
        
          
        
    
      
    
      
    
      
    

- Workshop
    
    ## Agenda
    
    1. **Kickoff & Team Introduction**
    
    1. **Levels of Planning in conOS**
    
    1. **Customization via BRF+ (color coding, object representation)**
    
    1. **Graphical Planning Board in Fiori (profiles, utilization, simulation)**
    
    1. **Discussion of Edge Cases (scheduled vs. process orders, maintenance orders, production versions, shift handling)**
    
    1. **Setup Optimization (Rüstoptimierung) and Future AI Options**
    
    1. **Performance and Technical Considerations**
    
    1. **Next Steps & Timeline**
    
    ---
    
    ## Key Highlights
    
    - **Planning Levels:** conOS bridges coarse and fine planning; includes material availability checks.
    
    - **BRF+ Customization:** Rules used for color coding process orders; improvements needed for readability (yellow vs. grey).
    
    - **Graphical Board:** Drag-and-drop scheduling, capacity utilization, unplanned order handling, locking to avoid conflicts.
    
    - **Shift Management:** Current model = 0–24h. External tools and conPEP add-on discussed.
    
    - **Production Versions:** Debate on strict vs. flexible rules for work centers.
    
    - **Setup Optimization:** Potential rules via BRF+ (color, gloss, material). AI integration considered for future.
    
    - **Performance:** Stable so far; VPN and remote connections can impact speed. Previous gateway indexing bug resolved.
    
    - **Timeline:**
        
        - September: Begin testing.
        
        - October: Key user testing and adjustments.
        
        - October Go-Live: Austria.
        
        - November/December Go-Live: US, Canada, Mexico.
        
        - 2026: Continuous improvements.
        
    
    ---
    
    ## Q&A Highlights
    
    - **Q:** How should scheduled vs. process orders be handled?
        
        **A:** Only process orders will be used; scheduled orders not relevant.
        
    
    - **Q:** Can maintenance (PM) orders be displayed in conOS?
        
        **A:** Yes, PM orders are supported; differentiation possible via order type.
        
    
    - **Q:** The yellow font is hard to read — what’s the solution?
        
        **A:** Options include darker yellow/orange, or using thicker font. Team to test preferences.
        
    
    - **Q:** Grey objects look too similar to non-working periods. Can we distinguish them?
        
        **A:** Yes, by using frame colors or alternate highlights for clarity.
        
    
    - **Q:** How should workplace groups and production versions be managed?
        
        **A:** Currently testing flexible allocation; stricter validation may be added later via BRF+ logic.
        
    
    - **Q:** Is Rüstoptimierung (setup optimization) possible?
        
        **A:** Yes, via BRF+ rules (e.g., light-to-dark colors). Complex rules could be handled with AI in future.
        
    
    - **Q:** How does locking work when multiple planners edit simultaneously?
        
        **A:** conOS uses pessimistic lock mode — orders are locked immediately to avoid overlap.
        
    
    - **Q:** Any performance concerns?
        
        **A:** No significant issues reported. Earlier gateway indexing bug was fixed. Large order volumes tested successfully.
        
    
    ---
    
    ✅ **Action Points**
    
    - Deliver updated transports (v25.06.1).
    
    - Assign planner/admin/gateway roles and start planner testing.
    
    - Collect feedback on usability, colors, and shift handling.
    
    - Use Z-planning profiles for customizations.
    
    - Aim for Austria go-live in October, followed by North America in Nov/Dec.
    

- CT Arbeitsplätze und Rezepte mit Phasen ohne Bedarf - Umplanung
    
    ![[attachments/image 2 5.png|image 2 5.png]]
    
    Steuernschlussel hat kein Kapabedarf
    

- Problem
    
    ![[attachments/image 3 5.png|image 3 5.png]]
    
    My first thought 0300 and its 0310 are not confirmed (
    
    When editing quantity all these errors appear  
    
    ![[attachments/image 4 4.png|image 4 4.png]]
    
    in transaction ST22  
    
    ![[attachments/image 5 4.png|image 5 4.png]]
    

- Meeting Notes 19.11.2025
    
    Role Problem for colleagues in America, see if the IT from TIGER Coatings tells that its roles or system
    
    Suche funktioniert mit 2 parameter nicht (Test in standard)
    
    19 conOS Team tiger coatings (Wartungsaufträge)
    
    ![[attachments/image 6 4.png|image 6 4.png]]
    
    Worklist schrift farbe sonder hintergrund auch (ob es möglich ist)
    
    When selecting an operation, there should be a button that shows operation highlighted into Worklist, function not only from worklist but both ways
    
    America (last wednesday)
    
    - Roles check (IT should fix)
    
    China (this monday should in january february to conOS)
    
    - still in excel :(
    
    Fix in the future
    
    PM Auftrag IW31 (quick info)
    
    - ticket customer relevance
    

## Phase 2

- First meeting
    
    Mexico/Canada they learn, works good (still use CM25 and conOS in parallel)
    
    Production had requirements,
    
    Z-Service in decision (January)
    
    After 14th January they are back in full form
    
    Focus for January
    
    - decide for Z-Service
    
    - Dashboard App preparation
    
      
    

- Tiger Coatings Z-Service
    
    1. Decision (Extensions)
        
        1. Define the problems
        
        1. Roles
        
        1. Feasibility is possible (one man day)
        
    
    1. What to prepare?
        
        1. Z-Service in customizing (names)
        
        1. Customizing from standard (all)
        
        1. Confirm the roles with Tiger IT
        
    
    1. Time slot (next week - 12 Jan)
    
    1. Dashboard (use case)
        
        1. The settings are the same so nothing should be very complicated
        
        1. UNTIL END OF JAN it should be work
        
    

- Tips
    
    What does a developer need from a consultant
    
    always ask for the opinion, questions if they have something left, problems etc
    

- edit order direct in the conOS not in COR2
    
    Make a mockup for Hannes prepare logic and ask Ishak if everything is okay
    

- Notes regardin production version
    
    Replicating problem on our system (we work now)
    
    unfortunately it will take time so end of february so we can release another hotfix  
    Because this is an urgent thing, what they can do is to do is to add an entry in customizing
    
    ![[attachments/image 7 4.png|image 7 4.png]]
    
    ![[attachments/image 8 3.png|image 8 3.png]]
    
    In customizing they need an additional entry 01 2 2 (temporary solution until we solve this solution, when we solve it)
    
    biermeier elias and strassmeier christian (cc ishak and selen)
    

- Notes Meeting 21.01.2026
    

## Phase 3

Transport handling

when doing a transport from one system to another, copy them when releasing them (ToC)

  

Info button, right click button for MD04

  

notiz only 20 characters limit (find what limit is here, custom view, table, note is included)

SE11 → STXL → TDLINE → Data type = CHAR, Lengh = 132

  

test to see if the note is saved directly or have to save the whole changes (automatically updated in worklist, also with changing the dates)

  

column for notes has to be automatically updated in worklist

  

AI interest (big)

Work center matrix

  

auftrage long text change is in the afutrag data Transactional data

two popups whencopying a service, they look the same but you have to pay attention

  

Lacke

2 spaten

Normale pulver lack, metalik lack

Raw materials,

kunstatz produktion

3 anlagen, hz bedarf produzierung

hatze einbesetzs und dieses pulver lack zu produzieren

Trocken pulver

pulver into metalikc, pize pigmente,

![[attachments/image 9 3.png|image 9 3.png]]


#TIGER #conOS #ZService
