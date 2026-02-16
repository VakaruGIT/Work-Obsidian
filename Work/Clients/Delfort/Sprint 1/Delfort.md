---
Last Sync: 2026-02-11T11:07
---
- [[#Alignments]]
- [[#User Training]]

- Delfort Workshop CM25 Analysis
    
    - TOY (Finnish Plant)
        
        **TERVAKOSKI Plant (Paper mill - owned by delfort)**
        
        - **Sales-driven** process (always in paper industry)
        
        - **no Classic MRP(MD01-MD02) run for finished and semifinished materials**
        
        - Plan most expensive machines (paper machines)
        
        ---
        
        - Block Planning is first (like a forecast, similar to PIRs)
            
            - They dont use PIRs
            
            - Creates "blocks of paper grades"
            
            - Tool: **ZPP_BLOCK_PLANNING**
            
        
        ---
        
        - Create customer order
        
        - Run **SALES DEPENDENT MRP Run** (MD50)
        
        - **RESULT of MD50**: SALES ORDER allocation successful or not?
        
        ---
        
        - If not successful -> planner solves conflict
            
            - Manual Allocation **ZPP_BLPL_ALLOC_SOI**
            
            - Or "taking paper from stock"
            
            - Or "creating another block"
            
        
        ---
        
        - Use **CM25** when Released
            
            - To get sequence number
            
        
        - **Important**: They **don’t plan paper machines in CM25**
            
            - They plan **post processes**
            
        
          
        
        ## Extra Questions
        
        - **Pegging problems?** (logic that checks)
            
            - No, there is the **competence of the planner**.
            
            - Planner sees "what is the earliest time."
            
            - Planner checked "required time."
            
        
        - **Process Order: Conversion -> Dispatching**
            
            - **Conversion Happens before Dispatching**.
            
            - They convert planned orders -> **COHV**.
            
        
        - **Stock Wizard (Custom Tool)**
            
            - "Second process"
            
            - Used for "existing stock and create production there."
            
            - Transaction: **ZPP_WIZARD_RES**
            
            - **CO08** is sometimes used.
            
        
        - **Releasing Orders**
            
            - Most orders **CO02 manually**.
            
            - They "check that before releasing."
            
            - Release status = "to be ready for instructions" ("no big deal").
            
            - Specific order user status? -> IDK (just releasing it).
            
        
        - **Why are they not using CM25?**
            
            - Planned orders and Production orders are **not used in CM25**.
            
            - Production Creation is **not** done in CM25.
            
            - **Reason:** It "Doesn’t work for their use case."
            
            - Paper has block planning (visual tool).
            
            - Standard CM25 is "Visually awful."
            
        
        - **Sequencing (The "Excel" Process)**
            
            - They use **Excel files** to get the sequence.
            
            - They "share this with production."
            
            - They need to "dispatch to get sequence number."
            
            - This **sequence number** is a **"user function,"** not a standard SAP dispatch number.
            
            - Used for "sheeting (one production/one run)."
            
            - They "only select one not multiple orders in one run."
            
        
        - **Changes After Release?** (Postpone, Delete, etc.)
            
            - **Possible.**
            
            - How: They "close it and modify it."
            
            - To postpone: They "put in excel for desired week."
            
            - **Crucial:** There are **"no dates in production order."**
            
            - (User did not understand when they close orders - "stock reset ? research ? reassert ?")
            
        
        - **After Dispatching**
            
            - Goes to **MES System**.
            
            - MES system is named **MESCAT**.
            
        
        - **Overall Profiles (Custom) what do they do ?**
            
            Map more profiles (Strategy profiles, Color)
            
            Customizing (overall profiles) research
            
            - ZOPPSHE01 SHEET
                
                ![[attachments/image 27.png|image 27.png]]
                
            
            - ZDLFSFCG02 BOB
                
                ![[attachments/image 1 6.png|image 1 6.png]]
                
                  
                
            
        
        - **Summary Questions**
            
            - **Z Transactions?** Yes (ZPP_BLOCK_PLANNING, ZPP_BLPL_ALLOC_SOI, ZPP_WIZARD_RES). This implies SAP Contractors were involved.
            
            - **Sequence Number?** It's a custom field/function, not standard SAP?
                
                - Information field not influencing activites ?
                    
                    - in TOY no, printing work instructions
                    
                
            
        
        - How would it be shown to production ?
            
            - Check (extract excel format from conos - solution ?)
            
            BS Arbeitplätze
            
        
          
        
    
    - PFW (Austria Tirol Plant)
        
        - Introduction
            
            Hallo an alle, mein Name ist Andrei, ich bin Junior PP-Berater mit Schwerpunkt in KI implementation und arbeite seit Februar bei concircle. Ich bin froh, hier zu sein
            
        
        Simple MTO Process
        
        All cm25 have Fertigungs aufträge and kunden
        
        Overall profiles
        
        - Only one ZDLFSFCG01
        
        - Variante holen (doppel klick)
            
            - Standard (BS* 1400)
            
        
        - Kein sequenznummer
        
        Machines operate (we cannot see arbeitszeiten farb konfiguration)
        
        Farb konfiguration
        
        Erste Rückmeldung wechseln wir
        
        ![[attachments/image 2 6.png|image 2 6.png]]
        
          
        
    
    - OPP (Czech Republic Plant)
        
        ZOPPBOB01 - Overall profile
        
        pool capacity is used (lots)
        
        they will want color configuration customizing  
        change production version based on bobbin width (pre-fabricated knifes)
        
        ![[attachments/image 3 6.png|image 3 6.png]]
        
    
    - FEU (Austrian ÖO Plant)
        
        - No sheeting
        
        - Order for:
            
            - Doctor Winding
            
            - Bobbin slitting
            
            - Coating
            
            - Stock Wizard (ZPP_WIZARD_RES) - MTS orders majority
            
            ![[attachments/image 4 5.png|image 4 5.png]]
            
            ![[attachments/image 5 5.png|image 5 5.png]]
            
            ![[attachments/image 6 5.png|image 6 5.png]]
            
            ![[attachments/image 7 5.png|image 7 5.png]]
            
              
            
        
    

- New Words
    
    Mühsam - braucht viel arbeit
    
    Anwendung - application
    
    Schmerzpunkt - Die Punkten wo es schwer tut
    
    Aufdruck - Imprint
    
    Stoßen - bump
    
    Bedienung - service
    
    Kreislauf - circuit
    
      
    
      
    

- Help to find + Screenshot in Test task (where to go into customizing)
    
    ![[attachments/image 8 4.png|image 8 4.png]]
    
    se11
    
    se16n
    
    cyuser
    
    ![[attachments/image 9 4.png|image 9 4.png]]
    

- Tips
    
    Make a rough presentation through the app
    
    1. Explain Planning Profile, Time Profile and Capacity and then the function of saving a variant.
    
    1. What we see ? Dispatched, Deallocated, Utilization
    
    1. Quick info, Operation details, order details
    
    1. Worklist (Usually give example a dispatched)
    
    1. Capacity Summary
    
    Give Real life examples  
    Make a story line
    

- Customizing Tips
    
    T-code SE10 For transport creation
    
    CAPOP CNF 2206  
    COLSEL 2012
    
    AP_Z* for the Z applications
    
    AP_CO9_*_
    
    AP_Z_COS_###\#_COL#####
    
    - include contained objects
    
    - Select service, then mass change, then everything and activate
    
    COLSEL for field extensions
    
    CAPOP_CNF coloring rules
    
    LOOP RULES OTHERWISE IT WONT READ THE DT CNF
    

# Alignments

- 22.01.2025 (Intern)
    
    PFW Wattens
    
    FEU Traum
    
    OPP
    
    TOY Terakovski
    
    Customizing can only display not dispatched orders
    
      
    

# User Training

- Key User Training DE
    
    - Introduction
        
        Welcome to the introduction, what have we done until now
        
        Functions
        
        Fiori Catalogue, Z-Catalogue (6, but usually only Planning Profile is active)
        
        Smart Tiles (Kacheln)
        
        Variant Details that was previously saved as an extra Tile
        
    
    - Planning Board
        
        - Overview
            
            Geplant, ungeplant, Auslastung pro Kapazität
            
            Variant that is selected (Planungsprofil, Zeitprofil, Kapazität)
            
            It would be better to simply say what we have in the dashboard (Planing Profile, Time Profile, Capacity)  
            based on this input, the gannt diagram will get updated with the selected data.
            
            Jumping too much, watch out on the functions, explain each button, not the last one.  
            What is Delfort strategy profile ?
            
            - There are all the planning
            
            Filterin of the workcenters in the gannnt
            
            ![[attachments/image 10 3.png|image 10 3.png]]
            
            The capacity is not that important for PFW
            
            All buttons, should be explained, from first to last in the small dashboard
            
            ![[attachments/image 11 3.png|image 11 3.png]]
            
            Zoom in zoom out
            
            PFW Time profile
            
            When someone explains, stop moving and doing stuff in the presentation
            
            too fast…
            
            Variant for worklist also needs to be explained
            
            Filter variants with what they need has to be taken into consideration
            
            Operation Quick info with customer fields, also the functions that are there
            
            User Z functions explanation
            
            explain possible functionalities
            
        
        - Worklist
            
            Drag and drop, also planning profile explanation
            
        
    
    - Sentences & Words
    

- Key User Training EN
    
    1. First present Planning Profile, then Time Profile, then Capacities, and explain the possibility to save these into a Variant which is fully customizable
    
    1. After that, show the tile which was saved
    
    1. After that go in the app and show them how to change the tiles
    
    1. Then each button and function (starting from notifications, and pause at worklist, explain there all functionalities
    
    1. Then continue from the button and explain there, last thing should be the strategy profile, then in the gannt explain possible function
    
    1. customer specific
    
    1. ask if they need all
    
    1. logic and customization can be availabe
    
    - what fields they want
    

- User Guide
    
    How to use Customizing / BRF+ ?
    
    Functions ?
    
    Color specifications, new buttons, how to work in the app
    
    UPDATE USER GUIDE EN VERSION
    
    - Customizing
        
        - AP_Z_COS_2012_COLSEL
            
            information, worklist, quickinfo
            
        
        - AP_Z_COS_2206_CAPOP_CNF
            
            Activate (DT_Mapping)
            
            Chart ID 1 (Dispatched), 2 (Not dispatched)
            
            colors
            
        
    
    - Transport Manager
        
        STMS
        
    

Rüstbalken ausblenden

#conOS 