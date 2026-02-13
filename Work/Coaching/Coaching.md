---
tags:
  - Training
---
- [[#Courses S/4HANA Manufacturing]]
    - [[#Basics of SAP S/4HANA]]
- [[#Coaching with Ishak]]

- Meeting Notes
    
    - 25.07.2025
        
        What is a process order get more information
        
        Difference between process order and production order
        
    
    - Scope Items
    
    - Cloud vs on-premise
        
        **SAP ERP**
        
        Cloud:
        
        - Managed by SAP in SAP data centers
        
        - Quarterly automatic updates by SAP
        
        - Limited in app extensibility (customization)
        
        On-premise:
        
        - Installed and managed in own infrastracture
        
        - Own decision of upgrade
        
        - Full customization (ABAP / extensions)
        
        **SAP MES**
        
        Cloud: DM
        
        - SaaS (runs in SAP BTP / Cloud environmnet)
        
        - Cloud integration with S/4HANA and IoT via APIs
        
        On-premise: ME
        
        - Installed on own data center or private cloud
        
        - Integrates with ERP, shop-floor systems usingh PI/PO (Process Integration/Process Orchestration)
        
        S/4HANA - Fiori On-premise but GUI available
        
        Fiori on cloud is mandatory
        
        ![[attachments/image 20.png|image 20.png]]
        
    
      
    

- Things to do 26.09.2025
    
    MRP Live - cover the applications, presentation in practice, pMRP, comparison of MRP types (customizing) difference of e.g. P1 vs. M1
    

- Tips
    
    Go into more detail, when presenting, if its a demo especially, i should know what everything does
    

- Setup optimization
    
    880 in PP book
    

- Tips next
    
    SAP PP Certification
    
    pMRP more
    
      
      
    
    ![[attachments/image 1 3.png|image 1 3.png]]
    
    ZVAC
    
    ![[attachments/image 2 3.png|image 2 3.png]]
    
    ![[attachments/image 3 3.png|image 3 3.png]]
    
    ![[attachments/image 4 2.png|image 4 2.png]]
    
    ![[attachments/image 5 2.png|image 5 2.png]]
    
    Please use the following comprehensive prompt to retrieve detailed, non-tabular information from the sources concerning the prerequisites and deep-dive distinctions for SAP Production Planning (PP) in different industries.
    
    ---
    
    **PP Prerequisites (Discrete Manufacturing)**
    
    Detail the essential **MRP master data** elements required for PP, including the definition of the **MRP Group** and how to use the **MRP Area** functionality to address the requirement of excluding a storage location's stock from MRP. Explain the fundamental steps performed by MRP in the background when running total planning (MD01).
    
    For Master Data elements:  
    Describe the key fields and views used for planning in the Material Master. Explain the purpose and content of the **Production Version (T-code C223)**, including its function as a combination of BOM and Routing, noting that multiple versions can be created based on a **lot size** range and emphasizing its mandatory status.
    
    What are the critical distinctions between **Discrete Manufacturing** and **Repetitive Manufacturing (REM)** in terms of confirmation processes, settlement methods, and use of status management (e.g., **TECO** vs. **CLSD** status)? What T-codes are used for Production Order creation (CO01) and confirmation (CO11N)?
    
    **PP Prerequisites (Process Manufacturing - PP-PI)**
    
    Explain the **difference between PP and PI**. Detail the characteristics of Process Manufacturing master data, focusing on the **Master Recipe** (T-code C201). Describe the unique functions of the Master Recipe, specifically: the use of **Phases** and the purpose of **Material Quantity Calculations (MQC)**. What transaction is used for Process Order creation (COR1)?
    
    Describe the execution flow in PP-PI, including the creation point of the **Control Recipe** (at order creation or release, configured in the Production Scheduler Profile/CORY), and the role of the **PI Sheet**. In PP-PI order configuration, what is the option available regarding approval before order release?
    
    **PP Prerequisites (Repetitive Manufacturing - REM)**
    
    Explain the REM confirmation process and the function of **Backflush**, including where it is used. Detail the simplified execution process using the **Planning Table (T-code MF52)**. Describe the nature of REM settlement, specifically mentioning the **Product Cost Collector (PCC)** and its period-based nature, contrasting it with order-based settlement in Discrete Manufacturing. What T-codes are used for reversing a backflush posting (MF41) and post-processing backflush documents (MF47)?
    
    **Extra Details (Integration, QM, Rework)**
    
    Focus on PP-CO/FI integration: Explain the role of the **Valuation Class** in the Material Master as the core linkage between material transactions and the General Ledger (G/L), referencing **OMWB/OBYC** configuration. Differentiate between **Plan Cost, Actual Cost, and Target Cost**. Explain how the **Activity Type** works in costing.
    
    Regarding quality and troubleshooting, detail the purpose of the **QM Control Key** and describe the common causes and resolutions for errors encountered in **COGI** reprocessing. Additionally, what are **Production Resources/Tools (PRTs)** and their types, and how are they created? Is it possible to create a production order without a routing and BOM?
    
    Finally, describe the T-codes used to evaluate planning results, distinguishing between the **dynamic Stock/Requirements List (MD04)** and the **static MRP List (MD05)**. Also, describe the function of **pegging (MD09)**.
    
    ![[attachments/image 6 2.png|image 6 2.png]]
    

- Next Coaching Tips from Christoph
    
    conOS & conPEP
    
    Practice PP
    
    PP Standard could be good not to be forgotten
    
    better to also focus in PP
    

## Courses S/4HANA Manufacturing

### Basics of SAP S/4HANA

- Supply Chain Planning
    
    - PUSH - Make-to-Stock
        
        ![[attachments/image 7 2.png|image 7 2.png]]
        
    
    - PULL - Make-to-Order
        
        ![[attachments/image 8 2.png|image 8 2.png]]
        
        ![[attachments/image 9 2.png|image 9 2.png]]
        
    
    ![[attachments/image 10 2.png|image 10 2.png]]
    
    ![[attachments/image 11 2.png|image 11 2.png]]
    
    ![[attachments/image 12 2.png|image 12 2.png]]
    
    ![[attachments/image 13 2.png|image 13 2.png]]
    

- Demand Management
    
    ![[attachments/image 14 2.png|image 14 2.png]]
    
    Planning Strategies
    
    ![[attachments/image 15 2.png|image 15 2.png]]
    

- MRP & Capacity Planning
    
    Reorder point planning
    
    ![[attachments/image 16 2.png|image 16 2.png]]
    
    Deterministic Planning
    
    ![[attachments/image 17 2.png|image 17 2.png]]
    
    ![[attachments/image 18 2.png|image 18 2.png]]
    

- Production Execution
    
    Discrete Manufacturing
    
    ![[attachments/image 19 2.png|image 19 2.png]]
    
    Process Manufacturing
    
    ![[attachments/image 20 2.png|image 20 2.png]]
    
    Repetitive Manufacturing
    
    ![[image 21.png]]
    
    ![[image 22.png]]
    
    ![[image 23.png]]
    
    ![[image 24.png]]
    

## Coaching with Ishak

- Test MRP Types (Processes)
    
    different strategies, mrp runs, dispay results see differences
    

halb fabrikat

  

finite scheduling

red color of operations

atp check

when changing quantity of the order, does the things change aswell ?

firm unfirm (planned orders

default values for production version

quantitiy change, waht can it change ? put logic questions