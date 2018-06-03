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
  
  Get a list of `CATEGORY_GROUP` labels by running the following MATCH query with the TQL endpoint:

  `MATCH (n:CATEGORY_2) RETURN n.label`
  
  ### Category 1


  This category 1 node references classifications such as  Storage Area Networks (SAN), Collaboration", Cash/Coin Detector and Help and Service Desk. <br>

  Get a list of `CATEGORY_GROUP` labels by running the following MATCH query with the TQL endpoint:

  `MATCH (n:CATEGORY_2) RETURN n.label`

  ### Category 2

  This category 2 node references classifications that are more granular than Categrory 1 or Category Group, such as Sound Masking, Retail Hardware, Diagnostic and Therapeutic Radiation/Imaging Devices", "Cheque Deposit Machine (CQM) and Handhelds.
  Get a list of `CATEGORY_2` labels by running the following MATCH query with the TQL endpoint:

  `MATCH (n:CATEGORY_2) RETURN n.label`
  

  ### Vertical

  The VERTICAL node is a high-level classification that features the following Verticals:

  * Cloud
  * Building and Facilities
  * Information and Technology
  * Medical and Health Care
  * Banking and Financial

  `MATCH (n:VERTICAL) RETURN n LIMIT 25`


    
  
  #### Query Examples <br>
    
  To use the MATCH statements in the following examples, you append the MATCH statement to the following tql endpoint and run a GET request from a API client or use cURL. <br>
  
  `https://v6-1.technopedia.com/tql?q=<MATCH Statement>`
 
left_code_blocks:
  - code_block: |
      MATCH (n:CATEGORY_1) RETURN n.label LIMIT 5

       RESPONSE SAMPLE

      {
        "results": [
            {
                "test",
                "s.test",
                "s.anything"
            }
        ]
      {  


    title: Category_1 Example
    language: javascript

  - code_block: >-
      MATCH (n:CATEGORY_2) RETURN n.label, n.description LIMIT 2


      RESPONSE SAMPLE

      {
         
          }
    title: Example one
    language: javascript

  - code_block: |-
      MATCH (n:CATEGORY_2) WHERE n.label = "Distributed Network Architecture" RETURN n LIMIT 2

       RESPONSE SAMPLE

      {
        "results": [
            {
                "test",
                "s.test",
                "s.anything"
            }
        ]
      {  

    title: Example two
    language: javascript

  - code_block: |- 
      MATCH (n:CATEGORY_2)-[v:BELONGS_TO]->(c:CATEGORY_1) RETURN c, n LIMIT 25
      
      Return records for CATEGORY_2 and CATEGORY_1 where CATEGORY_2 has a child relationship with CATEGORY_1

       RESPONSE SAMPLE

      {
        "results": [
            {
                "test",
                "s.test",
                "s.anything"
            }
        ]
      {  

    title: Example three
    language: javascript

  - code_block: |- 
      MATCH (n:CATEGORY_2) WHERE n.label = "Distributed Network Architecture" RETURN n LIMIT 2
      
       RESPONSE SAMPLE

      {
        "results": [
            {
                "test",
                "s.test",
                "s.anything"
            }
        ]
      {  

    title: Category_Group Example
    language: javascript

  - code_block: |- 
      MATCH (n:CATEGORY_2) WHERE n.label = "Distributed Network Architecture" RETURN n LIMIT 2
      
       RESPONSE SAMPLE

      {
        "results": [
            {
                "test",
                "s.test",
                "s.anything"
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