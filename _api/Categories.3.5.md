---
title: Categories
position: 3.5
type: 
description: 
content_markdown: |-
  ###### Categories are split into `CATEGORY_GROUP`, `CATEGORY_1`, `CATEGORY_2`, and `VERTICAL` is a high-level classification that is a parent of `CATEGORY_2`.


  Category nodes are linked by relationships from the software product node and the hardware product node. Run the following queries with the TQL endpoint to list the node labels:

  `MATCH (n:CATEGORY_2) RETURN n.label` 
   {: .info}
  `MATCH (n:CATEGORY_1) RETURN n.label`
   {: .info}  
  `MATCH (n:CATEGORY_GROUP) RETURN n.label`
   {: .info}
  `MATCH (n:VERTICAL) RETURN n.label`
   {: .info}
  
  The following diagram shows the categories and vertical nodes, and relationships.

  ![API Image](/images/cat_group.png){:class="img-responsive"} <br>

  <br>
  ### Category Group
  
  This category node features high-level classifications, such as Business Applications, Network Equipment, and Automatic Teller Machine (ATM). This categories parent is `CATEGORY_GROUP`, which features more global clasifications. 
  <br>
  Get a list of `CATEGORY_GROUP` labels by running the following MATCH query with the TQL endpoint:
  <br>
  `MATCH (n:CATEGORY_2) RETURN n.label`
  
  ### Category 1

  This category 1 node references classifications such as  Storage Area Networks (SAN), Collaboration", Cash/Coin Detector and Help and Service Desk. <br>
  <br>
  Get a list of `CATEGORY_GROUP` labels by running the following MATCH query with the TQL endpoint:
  <br>
  `MATCH (n:CATEGORY_2) RETURN n.label`

  ### Category 2

  This category 2 node references classifications that are more granular than Categrory 1 or Category Group, such as Sound Masking, Retail Hardware, Diagnostic and Therapeutic Radiation/Imaging Devices", "Cheque Deposit Machine (CQM) and Handhelds.
  Get a list of `CATEGORY_2` labels by running the following MATCH query with the TQL endpoint:
  <br>
  `MATCH (n:CATEGORY_2) RETURN n.label`
  

  ### Vertical

  The VERTICAL node is a high-level classification that features the following Verticals:

  * Cloud
  * Building and Facilities
  * Information and Technology
  * Medical and Health Care
  * Banking and Financial

  Get a list of the verticals by running the following MATCH query with the TQL endpoint:
  <br>
  `MATCH (n:VERTICAL) RETURN n LIMIT 25`


    
  
  #### Query Examples <br>
    
  To use the MATCH statements in the following examples, you append the MATCH statement to the following tql endpoint and run a GET request from a API client or use cURL. <br>
  <br>
  `https://v6-1.technopedia.com/tql?q=<MATCH Statement>`
 
left_code_blocks:
  - code_block: |
      MATCH (n:CATEGORY_1) RETURN n.label LIMIT 5

       RESPONSE SAMPLE

      {
        "results": [
            {
                "n.label": "Storage Area Networks (SAN)"
            },
            {
                "n.label": "Collaboration"
            },
            {
                "n.label": "Cash/Coin Detector"
            },
            {
                "n.label": "Help and Service Desk"
            },
            {
                "n.label": "Surgical Instrument"
            }
        ]
      {  


    title: Category_1 Example
    language: javascript

  - code_block: >-
      MATCH (n:CATEGORY_2) RETURN n.label, n.description LIMIT 2


      RESPONSE SAMPLE

      {
        "results": [
            {
                
                "n.description": "An electromechanical device designed to deal with body's musculoskeletal system. Use both surgical and nonsurgical means to treat musculoskeletal trauma, spine diseases, sports injuries, degenerative diseases, infections, tumors, and congenital disorders.",
                "n.label": "Electromechanical Orthopaedic Equipment"
            },
            {
                "n.description": "Devices which help with performing emergency procedure for the purpose of reviving heart and lung function.",
                "n.label": "Cardiopulmonary Resuscitation Devices"
            }
        ]
      {  
    title: Example one
    language: javascript

  - code_block: |-
      MATCH (n:CATEGORY_2) WHERE n.label = "Distributed Network Architecture" RETURN n LIMIT 2

       RESPONSE SAMPLE

      {
        "results": [
            {
                "n.cat_taxonomy2012_id": null,
                "n.cat_taxonomy2012_parent_id": null,
                "n.description": "The arrangement of a network computers in which several processors are located on scattered machines but are capable of working both independently and jointly",
                "n.label": "Distributed Network Architecture",
                "n.technopedia_id": "e87e4d7f-6990-4f31-b67d-ca2340a70fb4"
            }
        ]
      {  

    title: Example two
    language: javascript

  - code_block: |- 
      MATCH (n:CATEGORY_2)-[v:BELONGS_TO]->(c:CATEGORY_1) RETURN c, n LIMIT 2
      
      Return records for CATEGORY_2 and CATEGORY_1 where CATEGORY_2 has a child relationship with CATEGORY_1

       RESPONSE SAMPLE

      {
        "results": [
            {
                " "c.cat_taxonomy2012_id": null,
                "c.description": "Application software designed to enhance productivity within group of individuals, by which users can create a workspace and add workflow in order to achieve commmon goal",
                "c.label": "Collaboration",
                "c.technopedia_id": "3916d728-0401-43c2-a158-dcac6a0ffd0c",
                "n.cat_taxonomy2012_id": null,
                "n.cat_taxonomy2012_parent_id": null,
                "n.description": "A status indicator that conveys ability and willingness of a potential communication partner",
                "n.label": "Presence",
                "n.technopedia_id": "6b009946-ee6f-4821-bd0a-03a25a8710fe"
            },
            {
                "c.cat_taxonomy2012_id": null,
                "c.description": "Application software designed to enhance productivity within group of individuals, by which users can create a workspace and add workflow in order to achieve commmon goal",
                "c.label": "Collaboration",
                "c.technopedia_id": "3916d728-0401-43c2-a158-dcac6a0ffd0c",
                "n.cat_taxonomy2012_id": null,
                "n.cat_taxonomy2012_parent_id": null,
                "n.description": "An online service, platform, or site that focuses on building and reflecting of social networks or social relations among people, who, for example, share interests and/or activities",
                "n.label": "Social Networking",
                "n.technopedia_id": "0869fc49-1870-41f5-801b-480238c60782"
            }
        ]
      {  

    title: Example three
    language: javascript

  - code_block: |- 
      MATCH (sp:SOFTWARE_PRODUCT)-[:BELONGS_TO]->(cat2:CATEGORY_2)-[:BELONGS_TO]->(cat1:CATEGORY_1)-[:BELONGS_TO]->(catgrp:CATEGORY_GROUP) RETURN sp.product, cat2.label, cat1.label, catgrp.label LIMIT 2
      
       RESPONSE SAMPLE

      {
        "results": [
            {
                "cat1.label": "Supply Chain Management (SCM)",
                "cat2.label": "Supplier Relationship Management",
                "catgrp.label": "Business Applications",
                "sp.product": "SnapVSS"
            },
            {
                "cat1.label": "Supply Chain Management (SCM)",
                "cat2.label": "Supplier Relationship Management",
                "catgrp.label": "Business Applications",
                "sp.product": "Network Optimization (OPT)"
            },
            {
                "cat1.label": "Supply Chain Management (SCM)",
                "cat2.label": "Supplier Relationship Management",
                "catgrp.label": "Business Applications",
                "sp.product": "Supplier Quality"
            },
            {
                "cat1.label": "Supply Chain Management (SCM)",
                "cat2.label": "Supplier Relationship Management",
                "catgrp.label": "Business Applications",
                "sp.product": "Pocket ChangeOrder"
            }
        ]
      {  

    title: All categories example
    language: javascript

  - code_block: |- 
      MATCH (hardware:HARDWARE_PRODUCT)-[:BELONGS_TO]->(cat2:CATEGORY_2)-[:BELONGS_TO]->(cat1:CATEGORY_1)-[:BELONGS_TO]->(catgrp:CATEGORY_GROUP) RETURN hardware.product, cat2.label, cat1.label, catgrp.label LIMIT 6
      
       RESPONSE SAMPLE

      {
        "results": [
            {
                "cat1.label": "Landscape Maintenance",
                "cat2.label": "Environmental Monitoring and Protection",
                "catgrp.label": "Building Maintenance",
                "hardware.product": "Ecomar"
            },
            {
                "cat1.label": "Landscape Maintenance",
                "cat2.label": "Irrigation System",
                "catgrp.label": "Building Maintenance",
                "hardware.product": "SmartLine Controller"
            },
            {
                "cat1.label": "Landscape Maintenance",
                "cat2.label": "Irrigation System",
                "catgrp.label": "Building Maintenance",
                "hardware.product": "ProLine"
            },
            {
                "cat1.label": "Landscape Maintenance",
                "cat2.label": "Irrigation System",
                "catgrp.label": "Building Maintenance",
                "hardware.product": "SmartBox Controller"
            },
            {
                "cat1.label": "Landscape Maintenance",
                "cat2.label": "Irrigation System",
                "catgrp.label": "Building Maintenance",
                "hardware.product": "HermitCrab"
            },
            {
                "cat1.label": "Landscape Maintenance",
                "cat2.label": "Ground Preparation Equipment",
                "catgrp.label": "Building Maintenance",
                "hardware.product": "Floor Grinders & Polishing"
            }
        ]
      {  

    title: Category_Group Example
    language: javascript
right_code_blocks:
  - code_block: |2
        label
        description
    title: Category_Group_Attributes
    language: bash

  - code_block: |2-
        technopedia_id
        label
        description
        cat_taxonomy2012_id
        categrory_group
    title: Category_1 Attributes
    language: bash

  - code_block: |2-
        technopedia_id
        label
        description
        cat_taxonomy2012_id
        cat_taxonomy2012_parent_id
    title: Category_2 Attributes
    language: bash

  - code_block: |2-
        technopedia_id
        name
        short name
        
    title: Vertical Attributes
    language: bash

  - code_block: |2-
        (CATEGORY_2)-[:BELONGS_TO]->(VERTICAL)

        (CATEGORY_2)-[:BELONGS_TO]->(CATEGORY_1)

        (CATEGORY_2)<-[:BELONGS_TO]-(HARDWARE_PRODUCT)

        (CATEGORY_2)-[:BELONGS_TO]-(CATEGORY_1)

        (CATEGORY_1)<-[:BELONGS_TO]-(CATEGORY_2)

        

        
    title: Relationships
    language: bash
---