---
tags:
  - Training
---
- Processes
    
    ## 1. Core Production Execution (MTS / MTO / Process / Repetitive / Subcontracting / Rework)
    
    **GUI (SAP S/4HANA GUI / classic transactions):**
    
    - `**CO01 / CO02 / CO03**` → Create, change, display Production Orders
    
    - `**COR1 / COR2 / COR3**` → Create, change, display Process Orders
    
    - `**MF50**` → Planning Table (Repetitive Manufacturing)
    
    - `**MF60 / MFBF**` → Repetitive Manufacturing Backflush
    
    - `**CO11N**` → Production Order Confirmation
    
    - `**CO15**` → Confirmation of Production Order (final)
    
    - `**MIGO**`→ Goods Movements (261 GI, 101 GR, 531 Co-/By-product)
    
    - `**ME21N / ME22N / ME23N**` → Subcontracting Purchase Orders (for BJK, BMY) - Create, Change, Display
    
    - `**CO07 / CO08**` → Create Order w. Sales Order Reference (MTO)
    
    - `**C223**` → Production Version
    
    - `**CS01 / CS02 / CS03**` → BOM Management
    
    - `**CA01 / CA02 / CA03**` → Routing Maintenance
    
    - `C201 / C202 / C203` → Create, Change, DisplayMaster Recipe
    
    **Fiori Apps:**
    
    - _Manage Production Orders_
    
    - _Manage Process Orders_
    
    - _Manage Production Versions_
    
    - _Post Goods Movement_
    
    - _Post Production Confirmation_
    
    - _Reprocess Failed Goods Movements_
    
    - _Schedule Production_
    
    - _Monitor Material Coverage_
    
    - _Monitor Production Orders_
    
    - _Manage Work Center Capacity_
    
    ---
    
    ## **2. Planning & Capacity (MRP, Capacity Evaluation/Leveling, pMRP, Variant Config, Demand-Driven)**
    
    **GUI:**
    
    - `**MD01 / MD02 / MD03**` → MRP Runs (Plant, Material, Single-level)
    
    - `**MD04**` → Stock/Requirements List
    
    - `**CM01 / CM21 / CM25**` → Capacity Evaluation & Leveling
    
    - `**KKF6N**` → Cost Collector Analysis (Repetitive)
    
    - `**CU41 / CU50 / CU51**` → Variant Configuration
    
    - `**MDVP**` → MRP with Phantom Assemblies (silo-based process) Collective Availability Check
    
    **Fiori Apps:**
    
    - _Monitor Material Coverage_
    
    - _Manage Material Shortages_
    
    - _MRP Cockpit_
    
    - _Simulate pMRP_
    
    - _Schedule Production_
    
    - _Monitor Capacity Utilization_
    
    - _Manage Work Center Capacity_
    
    - _Change BOM / Mass Change BOM_
    
    - _Demand-Driven Replenishment_ (1Y2, 2QI)
    
    ---
    
    ## **3. Quality Management (1E1, 2V0, 2QN, 1V7)**
    
    **GUI:**
    
    - `**QA01 / QA02 / QA03**` → Inspection Lots
    
    - `**QE01 / QE11 / QE51N**` → Results Recording
    
    - `**QA11 / QA32**` → Usage Decision
    
    - `**QM01 / QM02 / QM03**` → Quality Notifications
    
    - `**QA33**` → Worklist for Usage Decisions
    
    **Fiori Apps:**
    
    - _Record Inspection Results_
    
    - _Manage Usage Decisions_
    
    - _Manage Defects_ (Nonconformance)
    
    - _Quality Technician Overview_ (2V0)
    
    - _Quality Engineer Overview_ (2V0)
    
    - _Monitor Quality Levels_
    
    - _Inspection Lot Worklist_
    
    ---
    
    ## **4. Logistics & Warehouse (Kanban, Batch Mgmt, Outbound)**
    
    **GUI:**
    
    - `**PKMC / PK01 / PK02 / PK13N**` → Kanban Control Cycle & Cards
    
    - `**VL01N / VL02N / VL03N**` → Outbound Delivery
    
    - `**LT03 / LT12**` → Warehouse Transfer Order Processing
    
    - `**MSC2N / MSC3N**` → Batch Management
    
    **Fiori Apps:**
    
    - _Kanban Board_
    
    - _Manage Kanban Containers_
    
    - _Post Goods Movement_
    
    - _Post Transfer Posting_
    
    - _Manage Outbound Deliveries_
    
    - _Display Batch Information_
    
    - _Batch Where-Used List_
    
    ---
    
    ## **5. Costing & Analytics (2QW, MES, ETO, Replenishment)**
    
    **GUI:**
    
    - `**KKBC_ORD / KKBC_HOE**` → Cost Analysis for Orders
    
    - `**COGI**` → Automatic Goods Movement Errors
    
    - `**COHV**` → Mass Processing of Orders
    
    - `**KKF6N**` → Product Cost Collector Display
    
    **Fiori Apps:**
    
    - _Production Cost Analysis_ (2QW)
    
    - _Plan/Actual Production Cost Analysis_
    
    - _Production Supervisor Overview_
    
    - _Production Planner Overview_
    
    - _Production Operations Overview_ (MES integration)
    
    - _Monitor Order Progress_
    

- Master Data & Orders
    
    # **1. Master Data – Foundation**
    
    ### **Work Centers / Resources**
    
    - **GUI Transactions**:
        
        - `CR01` / `CR02` / `CR03` → Work Center (create/change/display)
        
        - `CR11` → Capacity
        
        - `CRC1` / `CRC2` / `CRC3` → Resource (create/change/display
        
    
    - **Fiori Apps**:
        
        - _Manage Work Center Capacity_
        
        - _Display Work Center_
        
    
    ### **Bill of Material (BOM)**
    
    - **GUI Transactions**:
        
        - `CS01` / `CS02` / `CS03` → BOM (create/change/display)
        
        - `CS11` → BOM Explosion
        
    
    - **Fiori Apps**:
        
        - _Manage Bill of Material_
        
        - _Display Bill of Material_
        
        - _Mass Change BOM_
        
    
    ### **Routing / Recipe**
    
    - **GUI Transactions**:
        
        - `CA01` / `CA02` / `CA03` → Routing (discrete)
        
        - `C201` / `C202` / `C203` → Master Recipe (process)
        
    
    - **Fiori Apps**:
        
        - _Manage Routings_
        
        - _Manage Recipes_
        
    
    ---
    
    # **2. Production Orders (Discrete / MTO / MTS)**
    
    - **GUI Transactions**:
        
        - `CO01` / `CO02` / `CO03` → Production Order (create/change/display)
        
        - `CO11N` → Confirmation
        
        - `CO15` → Final Confirmation
        
        - `COHV` → Mass Processing of Orders
        
        - `MIGO` → Goods Movements (101 GR, 261 GI, 531 co-/by-products)
        
    
    - **Fiori Apps**:
        
        - _Manage Production Orders_
        
        - _Confirm Production Operations_
        
        - _Post Goods Movement_
        
        - _Reprocess Goods Movement Errors_
        
        - _Monitor Production Orders_
        
        - _Production Supervisor Overview_
        
    
    ---
    
    # **3. Process Orders (Process Industry)**
    
    - **GUI Transactions**:
        
        - `COR1` / `COR2` / `COR3` → Process Order (create/change/display)
        
        - `C202` / `C203` → Master Recipe maintenance
        
    
    - **Fiori Apps**:
        
        - _Manage Process Orders_
        
        - _Confirm Process Orders_
        
        - _Record Yield and Scrap_
        
        - _Monitor Process Orders_
        
    
    ---
    
    # **4. Repetitive Manufacturing (MTS – Lean)**
    
    - **GUI Transactions**:
        
        - `MF50` → Planning Table
        
        - `MF60` / `MFBF` → Backflush
        
        - `KKF6N` → Product Cost Collector Display
        
    
    - **Fiori Apps**:
        
        - _Manage Repetitive Manufacturing Profiles_
        
        - _Post Production Backflush_
        
        - _Analyze Production Variances_
        
    
    ---
    
    # **5. Planning & Capacity**
    
    - **GUI Transactions**:
        
        - `MD01 / MD02 / MD03` → MRP Run (plant/material/single)
        
        - `MD04` → Stock/Requirements List
        
        - `CM01 / CM21 / CM25` → Capacity Evaluation & Leveling
        
    
    - **Fiori Apps**:
        
        - _Monitor Material Coverage_
        
        - _Manage Material Shortages_
        
        - _MRP Cockpit_
        
        - _Simulate Predictive MRP (pMRP)_
        
        - _Manage Work Center Capacity_
        
        - _Monitor Capacity Utilization_
        
    
    ---
    
    # **6. Quality Management**
    
    - **GUI Transactions**:
        
        - `QA01 / QA02 / QA03` → Inspection Lots
        
        - `QE01 / QE51N` → Results Recording
        
        - `QA11 / QA32` → Usage Decision
        
        - `QM01 / QM02 / QM03` → Quality Notifications
        
    
    - **Fiori Apps**:
        
        - _Record Inspection Results_
        
        - _Manage Usage Decisions_
        
        - _Quality Engineer Overview_ (2V0)
        
        - _Quality Technician Overview_ (2V0)
        
        - _Manage Defects (Nonconformance)_
        
        - _Monitor Quality Levels_
        
    
    ---
    
    # **7. Logistics & Warehouse / Kanban**
    
    - **GUI Transactions**:
        
        - `PK01 / PK02 / PK13N` → Kanban Control Cycle
        
        - `VL01N / VL02N / VL03N` → Outbound Delivery
        
        - `MSC2N / MSC3N` → Batch Management
        
    
    - **Fiori Apps**:
        
        - _Kanban Board_
        
        - _Manage Kanban Containers_
        
        - _Manage Outbound Deliveries_
        
        - _Display Batch Information_
        
        - _Batch Where-Used List_
        
    
    ---
    
    # **8. Costing & Analytics**
    
    - **GUI Transactions**:
        
        - `KKBC_ORD` → Order Cost Analysis
        
        - `KKBC_HOE` → Cost Center Analysis
        
        - `COGI` → Goods Movement Errors
        
    
    - **Fiori Apps**:
        
        - _Production Cost Analysis_ (2QW)
        
        - _Plan/Actual Production Cost Analysis_
        
        - _Production Planner Overview_
        
        - _Production Operations Overview_
        
    

- Relevant Fields & Information
    
    - Information (Process)
        
        # Master Recipe (Process Manufacturing)
        
        Short intro: A **Master Recipe** defines _how_ a process material is made: phases, resources, parameters, and which components are consumed in each phase. It’s the execution backbone for **process orders**, PI sheets/XSteps, batch/yield control, and costing.
        
        ## Useful for:
        
        - **Formula & phase control**: time/temperature/speed set-points and sequencing.
        
        - **Phase-level consumption**: backflush/staging per phase for accurate inventory.
        
        - **Compliance & traceability**: PI sheets/XSteps, batch genealogy, e-signatures.
        
        ## Business Goal:
        
        - Run **repeatable, compliant** batches with clear operator guidance.
        
        - Get **accurate costs & yields** at phase and co-/by-product level.
        
        - Enable **automation** (messages to/from PCS/DCS; fewer manual postings).
        
        ## Use Case:
        
        A syrup plant mixes, heats, holds, and filters a batch. The recipe phases define set-points (°C, rpm, minutes), consume sugar/flavorings at the right step, collect IPC results, and post GR for main product plus co-/by-products.
        
        ---
        
        ## Fields & details to get right (the checklist)
        
        ### 1) Header & control
        
        - **Material + Plant**: header material (finished/semi-finished) and plant scope.
        
        - **Recipe usage & status**: production usage; set to **Released** before use.
        
        - **Group / Alternative / Version text**: meaningful IDs for multiple variants.
        
        - **Validity**: **Valid-from** date and (if used) **change number** for auditability.
        
        - **Lot-size range** (if maintained in recipe): enables selection by batch size.
        
        - **Texts/attachments**: SOPs, safety, cleaning (via DMS links) for operator context.
        
        ### 2) Structure: operations & phases
        
        - **Operations vs. Phases**: in process industries, **phases** are the executable steps.
        
        - **Sequence & relationships**: normal, parallel, or alternative; overlaps; **minimum transfer quantity** for pipeline/continuous transfers.
        
        - **Control key (PI)** at phase: in-house/external processing, confirmation, auto-GI/GR relevance, PI sheet requirement.
        
        - **Standard values & units**: setup/process/labor times with correct UoM (MIN, H, PC); define **formulas** that compute time from quantities where needed.
        
        ### 3) Resource assignments (capacity & costing)
        
        - **Primary resource**: tank/reactor/line (capacity category).
        
        - **Secondary resources**: utilities/helpers (e.g., operator, CIP skid, filter press).
        
        - **Splits/individual capacities**: if multiple identical lines exist.
        
        - **Costing linkage**: resource → cost center & activity types for setup/machine/labor.
        
        - **PRTs** (optional): tools/fixtures with availability or calibration constraints.
        
        ### 4) Component assignment at phase level
        
        - **Which components at which phase**: precise **phase assignment** for each BOM item.
        
        - **Backflush** (yes/no): typically **yes** in process; ensure it’s on the **phase**, not header.
        
        - **Bulk material** indicator** (if applicable) & **fixed/variable** quantity behavior.
        
        - **Scrap factors**: component/operation scrap to avoid under-issue.
        
        - **Alternative items** / usage probability & priority (managed substitutions).
        
        - **Staging**: production supply area, issue **storage location**, and staging method.
        
        - **Batch determination**: search procedure and class characteristics required if batches are selected automatically at issue.
        
        ### 5) Co-/By-products & costing
        
        - **Identify outputs**:
            
            - **Main product** (valued, planned).
            
            - **Co-products** (intentional, valued; participate in cost split).
            
            - **By-products** (secondary, less valuable; typically negative qty posting).
            
        
        - **Apportionment structure** for co-products: cost distribution bases (qty, value, equivalence numbers).
        
        - **Posting behavior**: align with **GR movement types** (e.g., by-product via 531), and define whether GR is **automatic** at confirmation.
        
        - **Yield dependencies**: target vs. actual yield drives variance & cost settlement.
        
        ### 6) PI Sheets / XSteps (Process Management)
        
        - **PI sheet required** (phase control key): ensure recipe phases generate PI sheets.
        
        - **Process Instruction Categories (PICs)**: reusable templates of parameters (e.g., _Target Temperature_, _Hold Time_, _Agitator Speed_).
        
        - **Characteristics / parameters**: bind PICs to **measurable values**, with **targets**, **limits**, **units**, and **entry requirements** (mandatory, range-checked).
        
        - **Control recipe destination(s)**: where the instructions go (MES/PCS, browser PI sheet, file). Multiple destinations allowed (e.g., line + lab).
        
        - **Process Message Categories**: for sending/receiving **process data** (e.g., actual temp, mass flow totals) and **status** (start/finish, alarms).
        
        - **E-signatures / audit trail** (if required): approval on critical steps or UD.
        
        - **Long texts/XStep hierarchy**: structured instructions with operator prompts and interlocks.
        
        ### 7) In-process quality (QM integration)
        
        - **Inspection type (03)** for in-process control (set in material master).
        
        - **MICs** (master inspection characteristics) assigned at phase: sampling procedure, target values/tolerances, recording method (manual/automatic via messages).
        
        - **Results recording requirement**: block subsequent phases until IPC complete if needed.
        
        - **Usage Decision** triggers & follow-up actions (e.g., rework loop).
        
        ### 8) Batches & genealogy
        
        - **Batch management** on header & components (material master level).
        
        - **Batch classification**: key characteristics (potency, viscosity, assay) for selection & release.
        
        - **Batch derivation** rules (e.g., from input lots to output lot).
        
        - **SLED/expiry** & conversion factors (if potency-adjusted consumption is used).
        
        - **Genealogy**: ensure phase-level backflush to enable accurate where-used.
        
        ### 9) Scaling & yields
        
        - **Base quantity**: recipe is authored for a base batch size—confirm unit consistency.
        
        - **Scaling method**: **linear** vs. **fixed + variable** (don’t scale CIP/cleaning).
        
        - **Component behavior**: **fixed** (e.g., catalyst charge) vs **proportional** (e.g., solvent).
        
        - **Target yield & planned scrap**: header/phase; used by scheduling, costing, and PV selection.
        
        ### 10) External processing (if a phase is subcontracted)
        
        - **External processing indicator** on phase + purchasing data link (service/material).
        
        - **Lead time** & **processing time** alignment with vendor capacity.
        
        - **What ships out/returns**: define **components provided** and **intermediate GR** on return.
        
        - **Quality integration** on return (inspection type 01/04 as required).
        
        ### 11) Texts, documents, compliance
        
        - **SOPs, safety, cleaning, formulations**: attach via document links.
        
        - **Labels/PI sheet printouts**: layout & language variants.
        
        - **Change control**: use **change numbers** with effectivity for any regulated changes.
        
        ### 12) Status management & consistency checks
        
        - **Recipe Released** before PV/Order use.
        
        - **Unit of measure** alignment across materials, components, and time formulas.
        
        - **Storage locations / PSA** consistent across recipe, BOM, and shop-floor setup.
        
        - **Production Version** exists and points to **this recipe + correct BOM** (see below).
        
        ---
        
        ## Production Version (tie-in for process)
        
        - **Material + Plant + Version ID**.
        
        - **Recipe reference**: group & alternative (or version counter).
        
        - **BOM reference**: alternative BOM if multiple exist.
        
        - **Validity (date & lot-size intervals)** to drive automatic selection.
        
        - **Active** for planning/execution; use multiple PVs for different lines/tanks or scales.
        
        ---
        
        ## Prerequisites (don’t skip)
        
        - **Material master**: MRP type, procurement type = in-house (or special procurement for subcontract), work scheduling data, inspection types.
        
        - **BOM**: correct quantities/UoM; co-/by-product indicators; scrap factors; alt items if used.
        
        - **Resources (work centers)**: capacity model, cost center & activity types, default control keys; secondary resources where needed.
        
        ---
        
        ## Common pitfalls (quick fixes)
        
        - **PI sheet not generated** → Phase control key not PI-relevant or recipe not Released.
        
        - **Wrong component issues** → Items not assigned to the correct **phase**; staging/PSA mismatch.
        
        - **Cost split off** → No **apportionment structure** for co-products; by-product quantities/signs wrong.
        
        - **Batch selection fails** → Missing **batch determination** search procedure or classification.
        
        - **Time calc weird** → Formula units or base quantity/scaling set incorrectly.
        
        - **Order can’t find recipe** → **Production Version** missing, invalid, or wrong lot-size/date range.
        
        ---
        
        ### One-page flow you can follow
        
        1. Materials (batch/QM flags, work scheduling)
        
        1. BOM (comp qty, co/by flags, scrap)
        
        1. Resources (capacity, costing, defaults)
        
        1. **Master Recipe** (phases, resources, components per phase, times, PI/XSteps, QM MICs)
        
        1. **Production Version** (link recipe+BOM, validity, lot-size)
        
        1. Test with a **small process order** (simulate PI sheet, confirm, GI/GR, co/by split)
        
        If you want, I can turn this into a printable **A4 checklist** or a **swimlane diagram** (Recipe authoring → PV → Order → PI sheet) you can keep on your desk.
        
    
    - Master Data
        
        ```mermaid
        flowchart LR
            A[Material Master] --> B[Basic Data]
            A --> C[MRP Views]
            A --> D[Work Scheduling]
            A --> E[Accounting / Costing]
            A --> F[Quality / Batch]
        
            B --> B1[Description]
            B --> B2[Unit of Measure]
            B --> B3[Material Type]
        
            C --> C1[MRP Type]
            C --> C2[Lot Size]
            C --> C3[Procurement Type]
            C --> C4[Safety Stock]
        
            D --> D1[Production Scheduler]
            D --> D2[In-House Production Time]
        
            E --> E1[Valuation Class]
            E --> E2[Price Control S/V]
            E --> E3[Costing Lot Size]
        
            F --> F1[Inspection Type]
            F --> F2[Batch Mgmt Flag]
        ```
        
    
    - BOM
        
        ```mermaid
        flowchart LR
            A[BOM] --> B[Header]
            A --> C[Items]
            A --> D[Item Categories]
            A --> E[Scrap Factors]
            A --> F[Assignments]
        
            B --> B1[Material]
            B --> B2[Plant]
            B --> B3[BOM Usage]
            B --> B4[Validity Dates]
        
            C --> C1[Component Material]
            C --> C2[Quantity]
            C --> C3[UoM]
        
            D --> D1[Stock Item L]
            D --> D2[Non-Stock N]
            D --> D3[Text Item R]
            D --> D4[Co-/By-Product]
        
            E --> E1[Component Scrap %]
            E --> E2[Operation Scrap %]
        
            F --> F1[Link to Operations]
        ```
        
    
    - Work Center / Resource
        
        ```mermaid
        flowchart LR
            A[Work Center / Resource] --> B[Basic Data]
            A --> C[Capacities]
            A --> D[Scheduling]
            A --> E[Costing]
            A --> F[Defaults]
        
            B --> B1[Category]
            B --> B2[Plant]
            B --> B3[Description]
        
            C --> C1[Available Capacity]
            C --> C2[Shifts]
            C --> C3[Individual Capacities]
        
            D --> D1[Formulas]
            D --> D2[Setup Time]
            D --> D3[Run Time]
            D --> D4[Queue/Wait Time]
        
            E --> E1[Cost Center]
            E --> E2[Activity Types]
        
            F --> F1[Control Keys]
            F --> F2[Standard Values]
        ```
        
    
    - Routing
        
        ```mermaid
        flowchart LR
            A[Routing] --> B[Header]
            A --> C[Operations]
            A --> D[Work Center Assignments]
            A --> E[Component Assignments]
            A --> F[Standard Values]
            A --> G[Control Data]
        
            B --> B1[Material / Group]
            B --> B2[Plant]
            B --> B3[Usage]
            B --> B4[Validity]
        
            C --> C1[Operation Sequence]
            C --> C2[Operation Description]
            C --> C3[Operation Number]
        
            D --> D1[Work Center]
            D --> D2[Capacity Category]
            D --> D3[Scheduling Parameters]
        
            E --> E1[Link to BOM Items]
            E --> E2[Component Allocation]
        
            F --> F1[Setup Time]
            F --> F2[Machine Time]
            F --> F3[Labor Time]
        
            G --> G1[Control Key]
            G --> G2[Inspection Characteristics]
            G --> G3[Backflush Indicator]
        ```
        
    
    - Recipe (Process Industry)
        
        ```mermaid
        flowchart LR
            A[Master Recipe] --> B[Header]
            A --> C[Phases]
            A --> D[Components]
            A --> E[PI Sheets / XSteps]
            A --> F[QM Integration]
            A --> G[Outputs]
            A --> H[Scaling]
        
            B --> B1[Material + Plant]
            B --> B2[Usage]
            B --> B3[Status]
            B --> B4[Validity]
        
            C --> C1[Sequence]
            C --> C2[Control Key]
            C --> C3[Resources]
            C --> C4[Standard Values]
        
            D --> D1[Phase Assignment]
            D --> D2[Backflush]
            D --> D3[Staging]
        
            E --> E1[Parameters - PICs]
            E --> E2[Process Messages]
            E --> E3[E-Signatures]
        
            F --> F1[Inspection Chars]
            F --> F2[In-Process Checks]
        
            G --> G1[Main Product]
            G --> G2[Co-Products]
            G --> G3[By-Products]
            G --> G4[Yield / Scrap]
        
            H --> H1[Linear Scaling]
            H --> H2[Fixed+Variable]
        ```
        
    
    - Production Version
        
        ```mermaid
        flowchart LR
            A[Production Version] --> B[Material + Plant]
            A --> C[BOM Link]
            A --> D[Recipe Link]
            A --> E[Validity]
            A --> F[Lot-Size Interval]
            A --> G[Status]
        
            C --> C1[Number]
            C --> C2[Alternative]
        
            D --> D1[Group]
            D --> D2[Counter]
        
            E --> E1[Valid-From]
            E --> E2[Valid-To]
        ```
        
    
    - Production / Process Order
        
        ```mermaid
        flowchart LR
            A[Production / Process Order] --> B[Header]
            A --> C[Operations / Phases]
            A --> D[Components]
            A --> E[Costs]
            A --> F[Execution]
            A --> G[Status Mgmt]
        
            B --> B1[Material]
            B --> B2[Order Type]
            B --> B3[Quantity]
            B --> B4[Dates]
        
            C --> C1[Work Centers]
            C --> C2[Control Keys]
            C --> C3[Standard Times]
        
            D --> D1[Assigned BOM Items]
            D --> D2[Reservations]
            D --> D3[Issue Method]
        
            E --> E1[Planned Costs]
            E --> E2[Actual Costs]
            E --> E3[Settlement Rules]
        
            F --> F1[Goods Issue]
            F --> F2[Confirmation]
            F --> F3[Goods Receipt]
        
            G --> G1[Created]
            G --> G2[Released]
            G --> G3[Confirmed]
            G --> G4[TECO]
            G --> G5[Closed]
        ```
        
    
    ```mermaid
    flowchart TD
        A[Material Master] --> B[BOM]
        B --> C[Work Center / Resource]
        C --> D[Routing / Recipe]
        D --> E[Production Version]
        E --> F[Production / Process Order]
        F --> G[Execution: GI / Confirmation / GR]
    ```