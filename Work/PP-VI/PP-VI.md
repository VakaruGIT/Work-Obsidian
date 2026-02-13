---
tags:
  - Training
---
- [[#On-site 23.09.2025 (MRP)]]
- [[#On-site 10.12.2025 (Capacity Planning & Production Planning)]]
- [[#Online 16.01.2026 (QPPD - Quality, Product and Product Definition)]]

## On-site 23.09.2025 (MRP)

- Customer Independent Requirements (CIRs)
    
    ### Overview of CIRs
    
    Customer Independent Requirements (CIRs) are a functionality in SAP that can be used when the SD (Sales & Distribution) module is not fully set up. They serve as templates for potential future customer orders without requiring a specific sold-to party or pricing c onditions. CIRs create their own document type (01) separate from regular sales orders.
    
    ### Transactions and Requirements Types
    
    - **MD81**: Dedicated transaction for creating CIRs
    
    - **MD61/MD62**: Standard transactions for planned primary requirements
    
    - **Requirement Types**: CIRs use specific requirement types (like VSF) that differ from those used for planned primary requirements
    
    - CIRs appear in requirements plans and can be viewed in MD04
    
    ### Planning Strategies and Consumption
    
    - CIRs work with specific planning strategies that determine how requirements are consumed
    
    - Strategy groups combine requirement types and requirement classes to define consumption behavior
    
    - In the demonstrated example (Strategy 50), a plan order with VP type was created from planned primary requirements
    
    - When CIRs were added, they consumed the planned primary requirements based on the defined strategy
    
    ### Practical Applications
    
    - CIRs can convert plan orders with VP type (not directly convertible to production orders) into orders that can be converted to production orders
    
    - This allows for production planning without creating full customer orders
    
    - Rejecting CIRs removes them completely from the requirements list
    
    - A customer order can be created later referencing the CIR, but it creates a separate document
    
    ### Key Use Cases
    
    - When SD module is not completely set up but customer-driven production is needed
    
    - For transitioning from make-to-stock to make-to-order without full SD configuration
    
    - For planning production capacity while only committing to actual production when customer demand materializes
    
    ### Open Questions
    
    - [ ] Explore if CIRs can be used with forecasting functionality
    
    - [ ] Determine specific business scenarios where CIRs provide advantages over standard processes
    
    - [ ] Investigate retail applications where specific customer relationships aren't required
    

- Notes
    
    Team 3 (Me, Sara, Markus)
    
    ![[attachments/image 3.png|image 3.png]]
    
    ![[attachments/image 1 2.png|image 1 2.png]]
    
    MRP Definition; different MRP versions; VB, VM, V1, V2 Customizing
    
    Material classes (bedarfsplannung V - Verbrauch, P - Plan, ND - No Planning
    
    nach wert, nach wichtigikeit, nach menge, nach Quantität,
    
    ![[attachments/image 2 2.png|image 2 2.png]]
    
    # MRP (Materialbedarfsplanung) in SAP S/4HANA
    
    ## Ziel von MRP
    
    - Sicherstellen, dass Materialien und Produkte **rechtzeitig** und in der **richtigen Menge** für Produktion und Lieferung verfügbar sind.
    
    - Automatisierung von Planung und Beschaffung.
    
    Eingangsgrößen der MRP-Planung
    
    - Aktuelle Bestände
    
    - Produktionsaufträge (geplant)
    
    - Kundenaufträge & Absatzprognosen
    
    - Durchlaufzeiten & Losgrößen
    
    - Stücklisten (BOM) & Arbeitspläne (Routing)
    
    ## Ergebnisse des MRP-Laufs
    
    - Bestellanforderungen (BANF)
    
    - Planaufträge
    
    - Umlagerungsanforderungen
    
    - Lieferplanabrufe
    
    ## Ablauf des MRP-Laufs
    
    1. Prüfung Planungsdatei
    
    1. Nettobedarfsermittlung (Bestand, Sicherheitsbestand, offene Bedarfe)
    
    1. Beschaffungsmenge berechnen
    
    1. Terminierung (Basis- oder Durchlaufzeitplanung)
    
    1. Beschaffungsvorschlag ermitteln
    
    1. Ermittlung abhängiger Bedarfe (BOM-Explosion)
    
    ## Einflussfaktoren auf MRP
    
    - **Materialstammdaten**
        
        - MRP-Verfahren (Typ)
        
        - Losgrößenverfahren
        
        - Dispositionsbereich (MRP-Area)
        
        - Beschaffungstyp & Sonderbeschaffung
        
        - Sicherheitsbestand
        
        - Terminierungsverfahren
        
    
    - **Stücklisten & Arbeitspläne**
    
    - **MRP-Parameter** (Planungsdateieintrag, Terminierungslogik)
    
      
    
    - **VB** – Manueller Meldebestand, keine Kundenaufträge berücksichtigt.
    
    - **VM** – Automatischer Meldebestand (System berechnet ROP (reorder point) + Sicherheitsbestand per Prognose).
    
    - **V1** – Wie VB, aber inkl. externer Bedarfe (z. B. Kundenaufträge, Reservierungen).
    
    - **V2** – Wie VM, aber inkl. externer Bedarfe.
    
    **Externe Bedarfe:** Kundenaufträge, Reservierungen, freigegebene Umlagerungsbestellungen, freigegebene BANF.
    
    ---
    
    👉 Kurzform:
    
    - **VB = statisch**
    
    - **V1 = statisch + Bedarf**
    
    - **VM = automatisch**
    
    - **V2 = automatisch + Bedarf**
    
    ![[attachments/image 3 2.png|image 3 2.png]]
    

- pMRP
    
    - Facts
        
        Identify potential capacity issues and evaluate possbile solutions as early as possible based on simplified requirements plan using a simplified material requirements algorithm. Result of the simulation
        
        ![[image 4.png]]
        
        With a simulation you can display capacity issues and other issues that affect delivery. Various options to solve problem. Add constraints.
        
          
        
        Steps:
        
        1. Define simulation scenario by determining which data based on MRP should be considered as reference
        
        1. Process pMRP Simulations
        
        1. Adjust Simulation
        
        1. Analyze plan
        
        Analyze how changes impact delivery performance , capacity situation, supply situation
        
        Implement the changes to operations
        
        ! When deciding to implement the simulation results in operative MRP, release the simulation
        
        When **releasing** a sim, quantities of demand-driven materials are changed and you can choose to create PIR for demand-driven MRP components, top-level materials and/or subassembly components and activate to the PIR version
        
          
        
        Check and adjust buffer levels for your products, before starting a new operative MRP run
        
          
        
        Pre-requisites:
        
        **Master Data:**
        
        1. Materials
        
        1. BOM
        
        1. Work Centers
        
        1. Routings
        
        1. Production Versions
        
        **Transnational Data:**
        
        - PIRs
        
    
    - Fiori Apps
        
        1. Schedule pMRP simulation creation
        
        1. Process pMRP Simulations
        
        1. Process pMRP Capacity Simulations
        
        ![[image 5.png]]
        
        ![[image 6.png]]
        
        ![[image 7.png]]
        
        First part is to create **DEMAND** in the form of PIRs for four weeks with active versions
        
        DEMO !!!!!
        
        Problems, example where we see capacity überlastet
        
        Active fehler sehen
        
        ![[image 8.png]]
        
        1. Data via Components
        
        1. Data via Top-Level Materials
        
        1. Data via Work Centers
        
        Explain the templates and why did i choose this exct one for the Demo
        
        First application (know everything)
        
    

- MRP Live [Blog](https://blog.sap-press.com/what-are-the-differences-between-mrp-live-and-classic-mrp) and [Video](https://www.youtube.com/watch?v=O_5NfhpykKE)
    
    ![[image 9.png]]
    
    - Facts
        
        MRP Live: `MD01N`
        
        - Pushes much of the planning logic into HANA rather than relying on ABAP loops and intermediate tables.
        
        - Reduces data transfer overhead and improves throughput
        
        ![[image 10.png]]
        
        ![[image 11.png]]
        
        ![[image 12.png]]
        
        ![[image 13.png]]
        
        ![[image 14.png]]
        
        ![[image 15.png]]
        
        ![[image 16.png]]
        
        ![[image 17.png]]
        
        ![[image 18.png]]
        
        ![[image 19.png]]
        
        Classic MRP: `MD01 MD02 MD03`
        
        - Set of transactions that you use to plan materials, allowing to plan entire plant, single material and components.
        
        - Developed in ABAP
        
        - No longer target architecture for the future
        
        |Dimension|**Classic MRP**|**MRP Live (S/4HANA)**|**Project Recommendation**|
        |---|---|---|---|
        |**Technology**|ABAP-based execution on application server|In-memory HANA execution via AMDP (SQLScript)|For large datasets → MRP Live ensures speed & scalability|
        |**Performance**|Sequential, slower, limited parallelization|Massively faster due to in-memory set-based processing|Prefer MRP Live where high volume / frequent planning needed|
        |**Fallback**|Always processes in classic logic|Automatic fallback to classic if unsupported features exist (e.g., configurable materials)|Use mixed mode if required, but optimize data to maximize Live scope|
        |**Enhancements**|ABAP-based BAdIs|AMDP-based BAdIs (different extension concept)|Projects with many custom MRP enhancements → assess rework effort|
        |**Reporting**|Snapshot **MRP Lists** (MD05, MD06, MD07)|No MRP Lists. Use **Fiori apps** (Monitor Coverage, Manage Coverage, Master Data Issues)|Train planners early to move from list-based to interactive apps|
        |**User Interface**|SAP GUI transactions (MD01, MD02, etc.)|Fiori apps + new MD01N for Live execution|Recommend Fiori rollout to planners alongside activation of MRP Live|
        |**Scope & Coverage**|All features supported (configurable materials, long-term planning, special procurement)|Some limitations (configurable materials, long-term planning, exotic cases)|If scope includes unsupported features → plan selective fallback|
        |**Strategic Direction**|Maintenance only, no new innovations|SAP’s future path; foundation for Predictive MRP, PP/DS integration, etc.|Use MRP Live as default in new S/4HANA implementations|
        
    
    - Fiori Apps
        
        Schedule MRP Runs
        
        Monitor Material Coverage
        
        Display MRP Master Data Issues
        
        - Check negative tests which problems are there possible to be
        
    
    MRP Bereich
    
    Integration mit PP/DS
    
    Differences Teilweise / Nahtlos
    
    pegging
    
    bedarf
    

## On-site 10.12.2025 (Capacity Planning & Production Planning)

- PEO (Production Engineering and Operations

## Online 16.01.2026 (QPPD - Quality, Product and Product Definition)

- Hauptknoten
    
    Every material has a specification number (with different details such as measurements, specific requirements which are needed for product)