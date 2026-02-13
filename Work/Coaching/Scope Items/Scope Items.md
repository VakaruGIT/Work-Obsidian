---
tags:
  - Training
---
- MTS Discrete Manufacturing (BJ5)
    
    Uses BOM, Routing, work center, production orders
    
    Useful for:
    
    - **Forecast-driven** planning
    
    - High-volume production of standardized parts or products
    
    - Strong control over order-level costs and variances
    
    Business Goal:
    
    - Minimize lead time and pre-produce stock based on forecast, not sales order
    
    Use case:
    
    - Automotive parts, electronics, tools
    
    ```mermaid
    flowchart LR
        A[Forecast PIRs] --> B[MRP Run]
        B --> C[Planned Order]
        C --> D[Production Order]
        D --> E[Execution: GI 261 / Confirmation / GR 101]
        E --> F[Stock: Unrestricted]
    
        C --> C1[BOM Explosion]
        C --> C2[Routing: Operations + Work Centers]
    ```
    

- MTS Process Manufacturing (BJ8)
    
    Bulk production of process materials (e.g. using recipes and PI sheets) Process Instruction (PI)
    
    Useful for:
    
    - **Volume-based production** triggered by forecast (PIRs)
    
    - Managing bulk liquids, powders, or mixtures
    
    - **Batch management**, yield and formula
    
    Business goal:
    
    - Scape up production to meet anticipated demand while managing complex formulations
    
    Use-case:
    
    - Paints, food base materials, detergents
    
    ```mermaid
    flowchart LR
        A[Forecast PIRs] --> B[MRP Run]
        B --> C[Planned Order]
        C --> D[Process Order]
        D --> E[Execution: PI Sheet / GI 261 / Confirmation / GR 101]
        E --> F[Stock: Batch Managed]
    
        D --> D1[Master Recipe: Phases + Resources]
        D --> D2[BOM: Formula + Batch Mgmt]
    ```
    

- MTS Process, Production Order - Fertigung Auftrag (2UG)
    
    Same as BJ8 but uses production orders instead of process orders
    
    Useful for:
    
    - When companies in process industries prefer production over logic
    
    - Simpler reporting/settlement for some orgs
    
    Business Goal:
    
    - Process manufacturing in companies that don’t require full PI (Process Instruction) sheet integration
    
    Use-cases:
    
    - Bottling, beverages, food
    
    ```mermaid
    flowchart LR
        A[Forecast PIRs] --> B[MRP Run]
        B --> C[Planned Order]
        C --> D[Production Order instead of Process Order]
        D --> E[Execution: GI 261 / Confirmation / GR 101]
        E --> F[Stock: Unrestricted]
    
        D --> D1[Recipe Logic Simplified]
        D --> D2[No PI Sheet Required]
    ```
    

- MTS with Co-/By-Products Process (3L7)
    
    Variant of BJ8 that includes joint production of multiple materials from one batch
    
    Useful for:
    
    - Tracking main, co- and by-products
        
        - Co-product (Valuable, intentional ouptut from main product)
        
        - By-product (secondary, unintended, less valuable material)
        
    
    - Allocating cost to all outputs (Herstellkosten)
        
        - Co-product can go into calculation (influence) by-product cannot
        
    
    - Legal reporting (e.g. disposal of by-products)
    
    Business Goal:
    
    - Optimize material value chain; monetize by-products
    
    Use-case: Chemical processing (e.g. producing glycerin + soap), slaughterhouses
    
    Booking it by 531 Goods Movement
    
    Bringing both needs a different goods movement
    
    261 - Good issue
    
    101 - Goods receipt
    
    531 - Goods receipt for co- & by-product
    
    Bill of material
    
    L in bill of material (X is unusual) L for lagermaterial
    
    ```mermaid
    flowchart LR
        A[Forecast PIRs] --> B[MRP Run]
        B --> C[Planned Order]
        C --> D[Process Order w/ Co- & By-Products]
        D --> E[Execution: GI 261 / GR 101 Main + GR 531 Co-/By-products]
        E --> F[Stock Updates + Cost Split]
    
        D --> D1[Recipe: Define Co- & By-Products]
        D --> D2[Apportionment Structure for Costs]
    ```
    

- MTS Production Repetitive (BJH)
    
    High-volume production with no production orders, using product cost collectors
    
    Useful for:
    
    - Lean, continuous production with minimal overhead
    
    - Rate-based scheduling (e.g., takt time)
    
    - Backflushing components *Most of the time*
        
        - Backflushing is an automated goods issue process in production where the system automatically deducts component materials from inventory when the finished product is reported as completed, without requiring manual postings for each withdrawal.
        
    
    Business Goal:
    
    - Reduce transactional overhead, streamline reporting
    
    Use-case:
    
    - Assembly Lines (Brakes, batteries)
    
    Planned order, additional object cost collector and on cost collector we can actually see the costs
    
    ```mermaid
    flowchart LR
        A[Forecast PIRs] --> B[MRP Run]
        B --> C[Planned Orders]
        C --> D[Repetitive Backflush MFBF]
        D --> E[Execution: Automatic GI + GR]
        E --> F[Costs via Product Cost Collector]
    
        C --> C1[Rate-Based Scheduling MF50]
        C --> C2[Production Lines instead of Orders]
    ```
    

- MTO Final Assembly Discrete (BJE)
    
    MTO triggered by sales order, production order is created per sales order item
    
    **MTO produces stock for one customer order**
    
    Useful for:
    
    - **Customer-specific variants** built on standard base
    
    - **Late-stage customization**
    
    Business Goal:
    
    - Offer product variety without stocking every combination
    
    Use-Case:
    
    - Laptops, custom bicycles, configurable machinery
    
    ```mermaid
    flowchart LR
        A[Sales Order] --> B[MRP Run]
        B --> C[Planned Order]
        C --> D[Production Order Make-to-Order]
        D --> E[Execution: GI 261 / Confirmation / GR 101]
        E --> F[Stock Assigned to Sales Order]
    ```
    

- MTO Semifinished Goods Planning (1BM)
    
    Combines **stocked finished goods** with final MTO assembly
    
    Useful for:
    
    - Decoupling long lead-time components from order-driven assembly
    
    - Hybrid push/pull strategy
    
    Business Goal:
    
    - Reduce lead time while offering customization
    
    Use-case:
    
    - Industrial pumps, medical equipment, laptop
    
    ```mermaid
    flowchart LR
        A[Sales Order] --> B[MRP Run]
        B --> C[Planned Order for Final Assembly]
        C --> D[Production Order MTO]
        D --> E[Execution: GI / Confirmation / GR]
        E --> F[Sales Order Stock]
    
        B --> B1[Stocked Semi-Finished Goods Planned Independently]
    ```
    

- MTO Process Manufacturing (3OK)
    
    Process manufacturing variant of MTO
    
    Useful for:
    
    - Producing **custom formulas** or **packaging** per customer specs
    
    - Batch traceability tied to **sales order**
    
    Business Goal:
    
    - Offer made-to-order flexibility in process industries
    
    Use-case: Pharma, cosmetics, food supplements
    
    ```mermaid
    flowchart LR
        A[Sales Order] --> B[MRP Run]
        B --> C[Planned Order]
        C --> D[Process Order]
        D --> E[Execution: PI Sheet / GI / Confirmation / GR]
        E --> F[Batch Stock Assigned to Sales Order]
    
        D --> D1[Custom Recipe: Customer-Specific Formula]
        D --> D2[Batch Traceability Linked to Sales Order]
    ```
    

- Production Subcontracting - External Processing (BJK) ———
    
    Uses subcontract purchase orders to send materials to an external vendor who performs specific operations. Vendor returns the finished / semi-finished goods
    
    Useful for:
    
    - Outsourcing specific operations (e.g. coating, welding, painting)
    
    - When in-house capacity or capability is missing
    
    - Ensures traceability of material sent to and received from vendor
    
    Business goal:
    
    - Extend production capacity and capability without investing in machinery or workforce
    
    - Leverage vendor expertise while maintaining integration into SAP production and procurement
    
    Use case:
    
    - A manufacturer of engine parts sends machined shafts to a vendor for heat treatment or surface coating, then reintegrates them into final assembly
    
    ```mermaid
    flowchart TD
        A[Production Order] --> B[Operation Marked as External]
        B --> C[Purchase Requisition Auto-Created]
        C --> D[Subcontract Purchase Order]
        D --> E[Send Components to Vendor]
        E --> F[Vendor Executes Operation e.g. Coating, Welding]
        F --> G[Receive Goods from Vendor GR 101]
        G --> H[Continue Production Order Processing]
    ```
    

- Subcontracting - Lohnbearbeitung (BMY) ———
    
    Similar to BJK but broader, classic subcontracting in SAP MM rather than production-focused external processing
    
    Involves sending raw materials / components to a subcontractor, who provides a service to turn them into finished products
    
    Useful for:
    
    - Outsourcing full product assembly or packaging
    
    - Keeping control over material ownership while vendor adds value
    
    - Lower cost of production via specialized subcontractors
    
    Business Goal:
    
    - Flexibly expand production without increasing fixed costs
    
    - Achieve lower costs or access specialized capabilities via partners
    
    Use Case:
    
    - Electronics company sends circuit boards and components to an EMS (Electronic Manufacturing Services) provider who assembles, tests, and delivers finished boards
    
    ![[attachments/image 2.png|image 2.png]]
    
    ```mermaid
    flowchart LR
        A[Procurement Need] --> B[Subcontracting Purchase Order]
        B --> C[Send Components to Vendor GI 541]
        C --> D[Vendor Provides Assembly/Packaging Service]
        D --> E[Receive Finished Product from Vendor GR 101]
        E --> F[Stock Updated w/ Subcontracted FG]
    ```
    

- Rework Processing - Stock-Manufactured Material (BJN)
    
    Handles rework of materials that already been received into stock but are defective or below quality standards
    
    Useful for:
    
    - Correcting defects in already completed production lots
    
    - Minimizing scrap by reprocessing faulty materials
    
    - Maintaining inventory accuracy and traceability
    
    Business Goal:
    
    - Reduce waste and improve yield by reusing stock through controlled rework processes
    
    Use Case:
    
    - A batch of finished plastic bottles has molding defects → bottles are collected, re-melted and reprocessed into new stock
    
    ```mermaid
    flowchart LR
        A[Defective Material in Stock] --> B[Rework Order Created]
        B --> C[Material Issued from Stock GI 261]
        C --> D[Rework Operations Performed]
        D --> E[Confirmation of Rework]
        E --> F[Goods Receipt of Corrected Material GR 101]
        F --> G[Stock Updated with Reworked FG]
    ```
    

- Rework processing - Work-in-Process (BJQ)
    
    Focuses on rework while the material is still in production (not yet received into stock)
    
    Useful for:
    
    - Capturing rework costs early in the process
    
    - Ensuring production continuity without scrapping the entire batch
    
    - Keeping WIP valuation accurate in financial reporting
    
    Business Goal:
    
    - Prevent escalation of quality issues downstream
    
    - Provide transparency of rework effort and cost during production itself
    
    Use Case:
    
    - During the machining of metal parts, a measurement issue is found → parts are reworked before final operations, ensuring no defective items reach stock
    
    ```mermaid
    flowchart LR
    A[Defect Found in Production WIP] --> B[Rework Order Created]
    B --> C[Rework Executed on Same WIP Lot]
    C --> D[Confirm Rework Operations + Time]
    D --> E[Continue Normal Production Flow]
    E --> F[Goods Receipt of Corrected Material GR 101]
    
    ```
    

- Material Requirements Planning ‘MRP’ (J44)
    
    MRP runs to ensure material availability for production. Considers demand (forecasts, sales orders), BOMs, lead times.
    
    Useful for:
    
    - Planning procurement and production in advance
    
    - Ensuring on-time availability of components without overstocking
    
    - Automating replenishment proposals (planned orders, purchase reqs)
    
    Business Goal:
    
    - Balance material availability with inventory cost
    
    - Enables smooth production execution and reduce stockouts
    
    Use Cases:
    
    - Automotive OEM uses MRP to explode demand for engines → generates planned orders for pistons, purchase requisitions for spark plugs, and schedules assembly lines accordingly
    
    ```mermaid
    flowchart TD
        A[Demand: Forecasts / Sales Orders] --> B[MRP Run]
        B --> C[Net Requirements Calculation]
        C --> D[BOM Explosion]
        D --> E[Planned Orders for In-House Production]
        D --> F[Purchase Requisitions for External Procurement]
        E --> G[Converted to Production Orders]
        F --> H[Converted to Purchase Orders]
    ```
    

- Production Capacity Leveling (3LQ)
    
    Also known as Capacity Planning / Scheduling. Balances production orders across available resources (work centers / machines) to avoid overloads
    
    Useful for:
    
    - Resolving capacity bottlenecks
    
    - Prioritizing orders based on due dates or strategy
    
    - Aligning shop-floor execution with feasible production plans
    
    Business Goal:
    
    - Ensure realistic, achievable production schedules
    
    - Increase machine utilization while avoiding overloading/idle time
    
    Use Case:
    
    - In a packaging plant, multiple filling machines exist → capacity leveling allocates production orders across them to balance workload and meet delivery commitments
    
    ```mermaid
    flowchart TD
        A[Capacity Requirements from Orders] --> B[Capacity Planning Table]
        B --> C[Detect Overloads / Bottlenecks]
        C --> D[Reschedule or Split Orders]
        D --> E[Distribute Load Across Resources]
        E --> F[Feasible Production Schedule Released]
    ```
    

- Production Capacity Evaluation (31L)
    
    Analyzes available vs. required capacity for work centers/machines based on planned and released production orders
    
    Useful for:
    
    - Checking if capacity is sufficient to meet production demand
    
    - Identifying bottlenecks early in planning
    
    - Supporting decision-making before running capacity leveling (3LQ)
    
    Business Goal:
    
    - Increase transparency of capacity utilization
    
    - Enable proactive adjustments (overtime, subcontracting, rescheduling)
    
    Use Cases:
    
    - A tire plant runs capacity evaluation and sees that the curing presses will be overloaded in October → planners decide to subcontract part of the workload to a partner plant
    
    ```mermaid
    flowchart TD
        A[Planned + Released Orders] --> B[Calculate Required Capacity]
        B --> C[Compare vs. Available Capacity]
        C --> D[Identify Overload / Underutilization]
        D --> E[Decision: Adjust Plan, Add Overtime, Subcontract]
    ```
    

- Production Operations with Manufacturing Execution Systems (1Y5)
    
    Integration of SAP S/4HANA production with MES (third-party Manufacturing Execution Systems) for detailed shop-floor control
    
    Useful for:
    
    - Companies already running an MES (e.g. Siemens Opcenter, Rockwell, GE Proficy)
    
    - Detailed production scheduling, machine-level tracking, and operator guidance
    
    - Recording real-time production confirmations, scrap and downtime
    
    Business Goal:
    
    - Achieve high transparency and control on shop floor
    
    - Reduce lead times and improve OEE (Overall Equipment Effectiveness)
    
    - Leverage existing MES investments while keeping ERP integration
    
    Use Case:
    
    - Automotive supplier uses Siemens Opcenter as MES to control assembly lines → SAP provides production orders, MES executes and collects detailed data (cycle times, machine status) which is fed back to SAP for costing and analytics
    
    ```mermaid
    flowchart LR
        A[Production Order in SAP] --> B[Order Transfer to MES]
        B --> C[MES: Detailed Scheduling + Dispatch]
        C --> D[Shop Floor Execution in MES]
        D --> E[Data Collection: Confirmations, Scrap, Downtime]
        E --> F[Feedback of Actuals to SAP]
        F --> G[Costing + Analytics in SAP]
    ```
    

- Production Operations with SAP Manufacturing Execution (2JN)
    
    Same concept as 1Y5 but here the MES is SAP’s own solution (SAP Digital Manufacturing / SAP ME) integrated natively
    
    Useful for:
    
    - End-to-end SAP landscape with no third-party MES dependency
    
    - Advanced shop-floor features: electronic work instructions, machine connectivity, quality checks, genealogy & traceability
    
    - Real-time integration with ERP (materials, orders, confirmations)
    
    Business Goal:
    
    - Full digital thread from planning to execution within SAP ecosystem
    
    - Reduce integration complexity and maintenance
    
    - Enable Industry 4.0 capabilities (IoT, digital twins, predictive quality)
    
    Use Case:
    
    - Medical devices manufacturer uses SAP DM to guide operators step-by-step, record inspection results, and trace every component used → full compliance with FDA Requirements
    
    ```mermaid
    flowchart LR
        A[Production Order in SAP] --> B[Native Integration with SAP DM]
        B --> C[Execution: Electronic Work Instructions, Machine Connectivity]
        C --> D[Data Capture: Confirmations, Scrap, Inspection Results]
        D --> E[Real-Time Feedback into S/4HANA]
        E --> F[Traceability + Compliance Records]
        F --> G[Analytics + KPI Dashboards]
    ```
    

- Analytics for Production Unit - Plan/Actual Production Cost (2QW)
    
    Used to compare planned vs. actual production costs at a unit or order level to identify variances and inefficiencies
    
    Useful for:
    
    - Monitoring deviations between planned and actual costs in production
    
    - Supporting decision-making with cost transparency
    
    - Identifying cost drivers and optimization potential
    
    Business Goal:
    
    - Improve cost control and reduce deviations
    
    - Enhance production efficiency by analyzing variances
    
    - Enable better budgeting and forecasting
    
    Use Case:
    
    Manufacturing plant produces 10.000 units of a product. The planned production cost was € 500,000 but actual costs ended up at € 540,000. Analytics identifies extra overtime labor and higher raw material consumption as the root causes
    
    ```mermaid
    flowchart TD
        A[Planned Costs from Order/Unit] --> B[Collect Actual Costs]
        B --> C[Compare Plan vs Actual]
        C --> D[Identify Variances]
        D --> E[Analyze Cost Drivers: Labor, Material, Overhead]
        E --> F[Management Decisions: Optimize, Rebudget, Corrective Action]
    ```
    

- Material Replenishment with Kanban
    
    - External Procurement
        
        Used when materials are replenished automatically from external suppliers using Kanban cards/triggers
        
        Useful for:
        
        - Automating procurement from suppliers when stock runs low
        
        - Reducing administrative workload in purchasing
        
        - Ensuring lean, just-in-time supply for production
        
        Business Goal:
        
        - Minimize stockouts and excess inventory
        
        - Speed up procurement cycles
        
        - Strengthen supplier integration into production flow
        
        Use Case:
        
        Automotive plant uses Kanban cards to replenish screws from a supplier. Once a bin is empty, the Kanban signal automatically creates a purchase order, and the supplier delivers directly to the production line
        
        ```mermaid
        flowchart LR
            A[Empty Bin / Kanban Signal] --> B[Automatic Purchase Order]
            B --> C[Supplier Delivery]
            C --> D[Goods Receipt into Production Supply Area]
            D --> E[Production Line Replenished]
        ```
        
    
    - In-House Production
        
        Used for replenishment of materials manufactured internally (in-house) with Kanban signals
        
        Useful for:
        
        - Triggering in-house production automatically when stock falls below threshold
        
        - Synchronizing production supply with consumption
        
        - Reducing manual planning effor
        
        Business Goal:
        
        - Improve production efficiency through pull-based manufacturing
        
        - Avoid overproduction and ensure availability
        
        - Support lean manufacturing principles
        
        Use Case:
        
        In a factory producing gearboxes, when assembly consumes the last gearbox from a storage bin, a Kanban signal is sent to the matching department, which immediately starts producing the next batch
        
        ```mermaid
        flowchart LR
            A[Empty Bin / Kanban Signal] --> B[Production Order Triggered]
            B --> C[In-House Manufacturing Started]
            C --> D[Goods Receipt into Production Supply Area]
            D --> E[Production Line Replenished]
        ```
        
    
    - Stock Transfer
        
        Used when replenishment comes from stock transfer between storage locations / plants triggered by Kanban
        
        Useful for:
        
        - Automating movement of materials between warehouses, plants, or storage areas
        
        - Reducing delays in internal supply chains
        
        - Ensuring production units receive timely materials from central stock
        
        Business Goal:
        
        - Optimize internal logistics flow
        
        - Lower transport and storage costs
        
        - Ensure continuous material supply without manual transfer orders
        
        Use Case:
        
        Company has a central warehouse and a production line warehouse. When a bin of lubricants at the production line is empty, a Kanban signal triggers a stock transfer from the central warehouse without manual intervention
        
        ```mermaid
        flowchart LR
            A[Empty Bin / Kanban Signal] --> B[Stock Transfer Order Triggered]
            B --> C[Material Moved from Central Warehouse]
            C --> D[Goods Receipt at Line Supply Area]
            D --> E[Production Line Replenished]
        ```
        
    

- Make-to-Stock Production with Variant Configuration (21D)
    
    Prebuild popular product variants for stock using Advanced Variant Configuration (AVC) and material variants; sales consume the stock. Ideal when demand for certain configurations is predictable
    
    Useful for:
    
    - stocking best-selling variant combinations (fast fulfillment)
    
    - Modeling characteristics/rules once in AVC and generating material variants
    
    - Forecast-driven planning (PIR/MRP) for configurable products
    
    Business goal:
    
    - Shorter lead times and higher on-time delivery
    
    - Lower order-related effort (configure once, build many)
    
    - Better capacity/load planning via forecasted variants
    
    Use case:
    
    - Forklift maker forecasts its top five mast/battery/tyre combos, creates material variants via AVC, produces stock, and ships immediately when orders arrive
    
    ```mermaid
    flowchart LR
        A[Forecast PIRs for Popular Variants] --> B[MRP Run]
        B --> C[Planned Order]
        C --> D[Production Order w/ AVC Config]
        D --> E[Execution: GI / Confirmation / GR]
        E --> F[Stock of Prebuilt Variants Ready for Sale]
    ```
    

- Make-to-Order Production with Variant Configuration (1YT)
    
    Customer sales order with configuration triggers production (no FG stock); AVC drives single- or multi-level configuration and the production order is created automatically
    
    Useful for:
    
    - Highly customized products where demand is not forecastable
    
    - Linking sales configuration directly to shop-floor execution and costing
    
    - Managing single- or multi-level configurable BOMs
    
    Business Goal:
    
    - Zero finished-goods inventory for variants
    
    - Full traceability from order to delivery
    
    - Deliver ETO-like customization with standardized rules/components
    
    Use Case: Customer orders a forklift with a specific mast height, battery and cab; the sales order configuration creates the production order and the unit is built and delivered against that order
    
    ```mermaid
    flowchart LR
        A[Sales Order + AVC Configuration] --> B[MRP Run]
        B --> C[Planned Order]
        C --> D[Production Order Configured]
        D --> E[Execution: GI / Confirmation / GR]
        E --> F[FG Delivered to Customer No Stock Kept]
    ```
    

- Make-to-Stock with Silo Material(Process Manufacturing) (3UL)
    
    Plan and execute MTS production based on process orders where bulk liquids/powders are stored in silos/tanks modeled as storage locations; often combined with phantom assemblies and tank management
    
    Useful for:
    
    - Continuous/batch processes using silos (chemicals, beverages, cement)
    
    - Coordinating tank levels with production & bottling/packing lines
    
    - Integrations like inbound storage tank management or co/by-product flows
    
    Business Goal:
    
    - Maximize line utilization while avoiding stockouts/overflows
    
    - Reduce losses/spillage with accurate silo visibility
    
    - Ensure batch traceability and QA through process orders
    
    Use case: A dairy syrup plant maintains minimum tank levels; MRP triggers process orders to refill silos, feeding multiple packaging lines without intrerruption
    
    ```mermaid
    flowchart LR
        A[Forecast Tank Min Levels / PIRs] --> B[MRP Run]
        B --> C[Planned Order]
        C --> D[Process Order to Refill Silo]
        D --> E[Production + Tank Management]
        E --> F[Silo Stock Maintained for Continuous Packaging Lines]
    ```
    

- Quality Management in Discrete Management (1E1) !!!!!!!
    
    At goods receipt from production (or in-process), the system creates an inspection lot (used to record results of quality control) from an inspection plan; technicians record results and the quality engineer makes a usage decision to release, block or scrap
    
    Useful for:
    
    - Posting GR to quality-inspection stock and controlling release
    
    - Standardizing inspections via plans, characteristics and sampling
    
    - Using Fiori appls to process lots, results, and usage decisions
    
    Business Goal:
    
    - Assure product quality and compliance
    
    - Reduce scrap/rework through early detection
    
    - Speed up release decisions with clear structured worklists
    
    Use case: after assembling controllers, GR posts to Q-Inspection stock; the technician records measurements per the inspection plan, and the engineer posts a UD to move conforming stock to unrestricted
    
    Can be done during or after the production (after GR)
    
    ```mermaid
    flowchart TD
        A[Goods Receipt from Production] --> B[Inspection Lot Created]
        B --> C[Technician Records Results]
        C --> D[Quality Engineer Usage Decision]
        D --> E[Release to Stock OR Block OR Scrap]
    ```
    

- SAP Fiori Analytical Apps for Quality Management (2V0) !!!!!!
    
    Role-based overview pages for quality engineers/technicians highlight inspection lots awaiting usage decision, defects, quality levels and tasks, with drill downs for actions
    
    Useful for:
    
    - Monitoring lots without usage decisions and backlog trends
    
    - Tracking top defective materials and action limits
    
    - Managing and prioritizing quality tasks
    
    Business Goal:
    
    - Proactive, KPI-drive quality management
    
    - Faster cycle time from defect to decision
    
    - Focus resources where risk/impact is highest
    
    Use Case: Each morning the quality engineer opens the overview page, spots a spike in “lots ready for UD”, drills into the plant/material, and assigns tasks to clear the queue before shipment cut-off
    
    ```mermaid
    flowchart TD
        A[Quality Engineer Opens Fiori Overview] --> B[See Lots Pending UD / Defects / KPIs]
        B --> C[Drill-Down by Plant / Material / Task]
        C --> D[Assign + Execute Quality Tasks]
        D --> E[Decisions Reflected in QM Process]
    ```
    

- Nonconformance Management (2QN)
    
    Operators record defects independently of classic quality notifications; the system triggers problem-solving via quality tasks and tracks closure for a closed-loop process
    
    Useful for:
    
    - Single defect logging at the point of detection
    
    - Assigning/monitoring corrective actions and dispositions
    
    - Analyzing recurring defects across materials, lines or shifts
    
    Business Goal:
    
    - Faster disposititioning to keep WIP moving
    
    - Better root-cause visibility and prevention
    
    - Reduced cost of poor quality through close-loop follow-up
    
    Use Case: during assembly, an operator logs a “surface scratch” NC; a task is created for rework inspection, parts are dispositioned, and actions are tracked to closure with analytics on repeat defects
    
    ```mermaid
    flowchart TD
        A[Operator Records Defect] --> B[Nonconformance Document Created]
        B --> C[System Creates Quality Tasks]
        C --> D[Disposition: Scrap / Rework / Use-as-is]
        D --> E[Closure + Analytics on Recurring Issues]
    ```
    

- Warehouse Outbound Processing to Customer with Batch Management (1V7)
    
    Used to manage outbound deliveries from warehouse to customer, ensuring batch traceability during picking, packing, and shipping
    
    Useful for:
    
    - Tracking batch-specific deliviers to customers
    
    - Ensuring regulatory compliance (e.g. pharma, food chemicals)
    
    - Handling returns or recalls quickly with batch traceability
    
    Business Goal:
    
    - Improve customer satisfaction with accurate, batch-specific deliveries
    
    - Ensure compliance with industry and legal regulations
    
    - Minimize risk and cost during recalls or quality issues
    
    Use Case:
    
    A pharmaceutical company ships vaccines to hospitals. Each delivery must be tied to a batch number to comply with health regulations, enabling quick recalls if a batch defect is discovered
    
    ```mermaid
    flowchart LR
        A[Delivery Created] --> B[Batch Determination in Warehouse]
        B --> C[Picking + Packing by Batch]
        C --> D[Goods Issue Posted]
        D --> E[Customer Shipment w/ Batch Traceability]
    ```
    

- Engineer-to-Order Production with Variant Configuration (4R8)
    
    Supports custom-made products where engineering and production are triggered by specific customer requirements
    
    Useful for:
    
    - Handling complex customer-specific orders
    
    - Linking engineering, BOM creation, and production in one flow
    
    - Managing variant configuration for highly customizable products
    
    Business Goal:
    
    - Reduce lead times for customer-specific engineering products
    
    - Integrate design and production for cost efficiency
    
    - Increase competitiveness through product customization
    
    Use Case:
    
    A machinery manufacturer designs and produces a one-off custom conveyor system for a factory. SAP integrates the engineering specs into BOMs and production orders
    
    ```mermaid
    flowchart LR
        A[Customer-Specific Engineering Specs] --> B[Engineering Creates BOM + Routing]
        B --> C[Production Order Created]
        C --> D[Manufacturing Execution]
        D --> E[Goods Receipt of Custom Product]
        E --> F[Delivery to Customer]
    ```
    

- Change Manufacturing Bill of Material (BOM) for Production (3LO)
    
    Allows controlled changes to a BOM already in production, ensuring the process reflects correct materials
    
    Useful for:
    
    - Making real-time corrections to production BOMs
    
    - Reducing production stoppages due to material changes
    
    - Ensuring accurate cost tracking with updated materials
    
    Business Goal:
    
    - Enhance flexibility in handling material substitutions
    
    - Avoid production delays and scrap
    
    - Ensure product quality with correct components
    
    Use case:
    
    An electronics producer substituse a capacitor mid-production due to supplier shortage and updates the BOM immediately in SAP to reflect the change
    
    ```mermaid
    flowchart TD
        A[Production in Progress] --> B[Need for Material Change Detected]
        B --> C[Engineering Updates Production BOM]
        C --> D[Order Updated with New Components]
        D --> E[Execution Continues with Corrected Materials]
    ```
    

- Mass Change Manufacturing Bill of Material for Production (3LP)
    
    Enables mass updates to multiple BOMs simultaneously, instead of changing them one by one
    
    Useful for:
    
    - Managing engineering changes across multiple products
    
    - Reducing manual work in BOM maintenance
    
    - Maintaining consistency across product lines
    
    Business Goal:
    
    - Speed up mass updates and reduce errors
    
    - Standardize changes across multiple products
    
    - Support fast response to regulatory or supplier-driven changes
    
    Use case:
    
    An automotive supplier replaces one type of screw across all car models and uses SAP to mass-update hundreds of BOMs at once
    
    ```mermaid
    flowchart TD
        A[Engineering Change Requirement] --> B[Mass Change Function Executed]
        B --> C[Update Multiple BOMs at Once]
        C --> D[All Related Production Orders Reflect Changes]
    ```
    

- Demand-Driven Buffer Level Management (1Y2)
    
    Controls buffer (stock) levels dynamically based on actual demand signals and variablilty
    
    Useful for:
    
    - Maintaining optimal stock levels
    
    - Reacting to demand fluctuations quickly
    
    - Avoid overstock and stockouts
    
    Business Goal:
    
    - Improve service levels with balanced inventory
    
    - Reduce working capital tied in excess stock
    
    - Increase responsiveness in supply chain
    
    Use Case:
    
    A consumer goods company adjusts buffer stock of seasonal beverages during summer months, preventing shortages in peak demand
    
    ```mermaid
    flowchart TD
        A[Monitor Buffer Stock Levels] --> B[Adjust Levels Dynamically Based on Demand]
        B --> C[Trigger Replenishment Signals]
        C --> D[Stock Balanced: No Excess, No Stockouts]
    ```
    

- Demand-Driven Replenishment Planning and Execution (2QI)
    
    Manages replenishment based on actual cosnumption, ensuring materials flow through the supply chain without overplanning
    
    Useful for:
    
    - Automating replenishment based on real demand signals
    
    - Synchronizing supply with demand at all points in the chain
    
    - Reducing bullwhip effect in planning
    
    Business goal:
    
    - Improve material availability
    
    - Reduce excess inventory and expedite costs
    
    - Streamline supply chain execution
    
    Use Case:
    
    A spare parts distributor replenishes stock automatically based on actual consumption at regional warehouses, ensuring mechanics always have the right parts available
    
    ```mermaid
    flowchart TD
        A[Consumption in Supply Chain] --> B[Replenishment Order Triggered]
        B --> C[Stock Refilled to Buffer Locations]
        C --> D[Continuous Flow Across Supply Chain]
    ```
    

- Predictive Material and Resource Planning (pMRP) (4B5) [[]]
    
    Uses simulations and predictive models to evaluate future material and capacity needs
    
    Useful for:
    
    - Running what-if simulations for material and resource constraints
    
    - Predicting capacity bottlenecks in advance
    
    - Supporting strategic planning with scenario-based data
    
    Business goal:
    
    - Improve production stability by anticipating shortages
    
    - Support management in making proactive sourcing decisions
    
    - Reduce firefighting caused by late material shortages
    
    Use Case:
    
    A high-tech company uses pMRP to simulate the effect of a semiconductor supplier delay on production capacity, adjusting sourcing before distruptions occur
    
    ```mermaid
    flowchart TD
        A[Future Demand Scenarios] --> B[Run Predictive MRP Simulation]
        B --> C[Material Availability Projection]
        B --> D[Capacity Availability Projection]
        C --> E[Identify Potential Shortages]
        D --> F[Identify Future Bottlenecks]
        E --> G[Simulate Mitigation Options Alt Sourcing, Expediting]
        F --> G
        G --> H[Decision: Adjust Procurement or Capacity Plans]
    ```