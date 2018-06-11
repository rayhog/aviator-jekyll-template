---
title: Hardware Model
position: 2.3
type: 
description: The hardware model node defines information about the model, such as dimensions and other general specifications. The hardware model
  has a relationship with the hardware product, which you can use to get more information about hardware.
   
content_markdown: |-
  This query example returns all hardware models.
  
  `MATCH (a:HARDWARE_MODEL) RETURN a.model`
  {: .info}
  
  <br>
  You can get manufacturer data for the hardware model by using the relationships to connect to that node.
  For example, the following query returns five results that include the model, product, and manufacturer.<br>

  <br>
  `MATCH (hw_mod:HARDWARE_MODEL)-[:HAS_A]->(hw_prod:HARDWARE_PRODUCT)-[:HAS_A]->(manu:MANUFACTURER) RETURN hw_mod.model, hw_prod.product, manu.manufacturer LIMIT 5`
  
  <br> 
  The following diagram shows hardware nodes and related software nodes.  
  
  ![API Image](/images/hard_mod.png){:class="img-responsive"} <br>
  
  #### Query Examples <br>
    
  To use the MATCH statements in the following examples, you append the MATCH statement to the following tql endpoint and make a GET request from a API client or use cURL. <br>
  <br>
  `https://v6-1.technopedia.com/tql?q=<MATCH Statement>`

left_code_blocks:
  - code_block: |
      MATCH (n:HARDWARE_MODEL) RETURN n.model, n.cpu_sockets

      RESPONSE SAMPLE

      {
        "results": [
            {
                "n.cpu_sockets": 1,
                "n.model": "24663K0"
            },
            {
                "n.cpu_sockets": 1,
                "n.model": "10AC002CUM"
            },
            {
                "n.cpu_sockets": 1,
                "n.model": "4284GQ5"
            },
            {
                "n.cpu_sockets": 1,
                "n.model": "4180D57"
            },
            {
                "n.cpu_sockets": 1,
                "n.model": "4177RL9"
            },
            {
                "n.cpu_sockets": 1,
                "n.model": "23943S3"
            },
            {
                "n.cpu_sockets": 1,
                "n.model": "17-f110nr"
            }
        ]
      {  

    title: Example one
    language: javascript

    
  - code_block: >-
      MATCH (hw_mod:HARDWARE_MODEL)-[:HAS_A]->(hw_prod:HARDWARE_PRODUCT)-[:HAS_A]->(manu:MANUFACTURER) RETURN hw_mod.model, hw_prod.product, manu.manufacturer LIMIT 5
         
      RESPONSE SAMPLE

      {
        "results": [
            {
                "hw_mod.model": "A1080a-S",
                "hw_prod.product": "Express5800/A1080a Series",
                "manu.manufacturer": "NEC"
            },
            {
                "hw_mod.model": "A1080a-E",
                "hw_prod.product": "Express5800/A1080a Series",
                "manu.manufacturer": "NEC"
            },
            {
                "hw_mod.model": "A1080a-D",
                "hw_prod.product": "Express5800/A1080a Series",
                "manu.manufacturer": "NEC"
            },
            {
                "hw_mod.model": "3125N",
                "hw_prod.product": "Phaser 3125 (Networked)",
                "manu.manufacturer": "Xerox"
            },
            {
                "hw_mod.model": "3125V_N",
                "hw_prod.product": "Phaser 3125 (Networked)",
                "manu.manufacturer": "Xerox"
            }
        ]
      {  

    title: Example two
    language: javascript
  - code_block: |-
      MATCH (mod:HARDWARE_MODEL)-[:HAS_A]->(prod:HARDWARE_PRODUCT) WHERE prod.product CONTAINS "108" RETURN mod.model, prod.product LIMIT 5

      RESPONSE SAMPLE

      {
        "results": [
                {
                    "mod.model": "A1080a-S",
                    "prod.product": "Express5800/A1080a Series"
                },
                {
                    "mod.model": "A1080a-E",
                    "prod.product": "Express5800/A1080a Series"
                },
                {
                    "mod.model": "A1080a-D",
                    "prod.product": "Express5800/A1080a Series"
                },
                {
                    "mod.model": "WAP-4000A",
                    "prod.product": "54/108Mbps Wireless Access Point"
                },
                {
                    "mod.model": "FI9903P",
                    "prod.product": "Outdoor Waterproof IP66 H.264 1080P PnP IP Camera"
                }
        ]
      {  

    title: Example three
    language: javascript

  - code_block: |-
      MATCH (n:HARDWARE_MODEL)-[:HAS_A]->(h:HARDWARE_PRODUCT)-[:BELONGS_TO]->(m:CATEGORY_2)-[:BELONGS_TO]->(w:VERTICAL) RETURN n, h, m, w LIMIT 5

      RESPONSE SAMPLE

      {
        "results": [
            {
                "h.create_date": null,
                "h.desupported_flag": null,
                "h.modified_at": "2011-03-16 09:46:45",
                "h.product": "Express5800/A1080a Series",
                "h.technopedia_id": "f6d32439-001b-4ca7-abb1-cd7627086ade",
                "m.description": "A computer or device on a network that manages network resource",
                "m.label": "Servers",
                "m.technopedia_id": "195fa6b3-7d0f-4317-995f-d3c9f1ae08e7",
                "n.cpu_sockets": 4,
                "n.cpu_url": "http://www.necam.com/docs/?id=6ee81afc-8691-484e-9549-b21b83f6302e",
                "n.created_at": "2010-04-23 11:31:47",
                "n.date_introduced": "3/30/2010",
                "n.desupported_flag": null,
                "n.max_non_operating_humidity": null,
                "n.max_non_operating_temp": null,
                "n.max_operating_temp": null,
                "n.min_non_operating_humidity": null,
                "n.min_non_operating_temp": null,
                "n.min_operating_temp": null,
                "n.model": "A1080a-S",
                "n.modified_at": "2013-10-18 16:54:07",
                "n.technopedia_id": "807bd3dc-2100-4116-a4e2-cbf741e725d4",
                "w.name": "Information and Technology",
                "w.short_name": "IT",
                "w.technopedia_id": "0be7a9ed-b538-4942-b6ce-b9243566305f"
            },
            {
                "h.create_date": null,
                "h.desupported_flag": null,
                "h.modified_at": "2011-03-16 09:46:45",
                "h.product": "Express5800/A1080a Series",
                "h.technopedia_id": "f6d32439-001b-4ca7-abb1-cd7627086ade",
                "m.description": "A computer or device on a network that manages network resource",
                "m.label": "Servers",
                "m.technopedia_id": "195fa6b3-7d0f-4317-995f-d3c9f1ae08e7",
                "n.cpu_sockets": 8,
                "n.cpu_url": "http://www.necam.com/docs/?id=6ee81afc-8691-484e-9549-b21b83f6302e",
                "n.created_at": "2010-04-23 11:32:43",
                "n.date_introduced": "3/30/2010",
                "n.desupported_flag": null,
                "n.max_non_operating_humidity": null,
                "n.max_non_operating_temp": null,
                "n.max_operating_temp": null,
                "n.min_non_operating_humidity": null,
                "n.min_non_operating_temp": null,
                "n.min_operating_temp": null,
                "n.model": "A1080a-E",
                "n.modified_at": "2013-10-18 16:54:22",
                "n.technopedia_id": "5cb93d0e-63d0-43eb-89d8-7d1d25ff4ce5",
                "w.name": "Information and Technology",
                "w.short_name": "IT",
                "w.technopedia_id": "0be7a9ed-b538-4942-b6ce-b9243566305f"
            }
        ]
      {  

    title: Example four
    language: javascript

  - code_block: |-
      MATCH (n:HARDWARE_MODEL)-[:HAS_A]->(h:HARDWARE_PRODUCT)-[e:BELONGS_TO]->(m:CATEGORY_2)-[:BELONGS_TO]->(w:VERTICAL) RETURN n, h, m, w
      
      RESPONSE SAMPLE

      {
        "results": [
            {
                "h.create_date": null,
                "h.desupported_flag": null,
                "h.modified_at": "2011-03-16 09:46:45",
                "h.product": "Express5800/A1080a Series",
                "h.technopedia_id": "f6d32439-001b-4ca7-abb1-cd7627086ade",
                "m.description": "A computer or device on a network that manages network resource",
                "m.label": "Servers",
                "m.technopedia_id": "195fa6b3-7d0f-4317-995f-d3c9f1ae08e7",
                "n.cpu_sockets": 4,
                "n.cpu_url": "http://www.necam.com/docs/?id=6ee81afc-8691-484e-9549-b21b83f6302e",
                "n.created_at": "2010-04-23 11:31:47",
                "n.date_introduced": "3/30/2010",
                "n.desupported_flag": null,
                "n.max_non_operating_humidity": null,
                "n.max_non_operating_temp": null,
                "n.max_operating_temp": null,
                "n.min_non_operating_humidity": null,
                "n.min_non_operating_temp": null,
                "n.min_operating_temp": null,
                "n.model": "A1080a-S",
                "n.modified_at": "2013-10-18 16:54:07",
                "n.technopedia_id": "807bd3dc-2100-4116-a4e2-cbf741e725d4",
                "w.name": "Information and Technology",
                "w.short_name": "IT",
                "w.technopedia_id": "0be7a9ed-b538-4942-b6ce-b9243566305f"
            },
            {
                "h.create_date": null,
                "h.desupported_flag": null,
                "h.modified_at": "2011-03-16 09:46:45",
                "h.product": "Express5800/A1080a Series",
                "h.technopedia_id": "f6d32439-001b-4ca7-abb1-cd7627086ade",
                "m.description": "A computer or device on a network that manages network resource",
                "m.label": "Servers",
                "m.technopedia_id": "195fa6b3-7d0f-4317-995f-d3c9f1ae08e7",
                "n.cpu_sockets": 8,
                "n.cpu_url": "http://www.necam.com/docs/?id=6ee81afc-8691-484e-9549-b21b83f6302e",
                "n.created_at": "2010-04-23 11:32:43",
                "n.date_introduced": "3/30/2010",
                "n.desupported_flag": null,
                "n.max_non_operating_humidity": null,
                "n.max_non_operating_temp": null,
                "n.max_operating_temp": null,
                "n.min_non_operating_humidity": null,
                "n.min_non_operating_temp": null,
                "n.min_operating_temp": null,
                "n.model": "A1080a-E",
                "n.modified_at": "2013-10-18 16:54:22",
                "n.technopedia_id": "5cb93d0e-63d0-43eb-89d8-7d1d25ff4ce5",
                "w.name": "Information and Technology",
                "w.short_name": "IT",
                "w.technopedia_id": "0be7a9ed-b538-4942-b6ce-b9243566305f"
            }
        ]
      {  

    title: Example five
    language: javascript

  - code_block: |-
      curl -G -H "Authorization: Bearer b93477a9-057b-4878-a16b93477a9-057b-4878-a16f-d7f7d1f27a7af-d7f7d1f27a7a" "https://v6-1.technopedia.com/tql"  --data-urlencode' "q=MATCH (h:HARDWARE_MODEL) RETURN h.model"
    title: cURL 
    language: bash
right_code_blocks:
  - code_block: |2
      technopedia_id
      model
      url
      desupported_flag
      cpu_sockets
      cpu_url
      date_introduced
      model_profile
      min height
      max height
      min width
      max width
      min depth
      max depth
      min weight
      max weight
      min_operating_temp
      max_operating_temp
      min_non_operating_temp
      max_non_operating_temp
      min_non_operating_humidity
      max_non_operating_humidity
      min_operating_humidity
      max_operating_humidity
      created_at
      modified_at

    title: Hardware Model Attributes
    language: bash
  - code_block: |2-
      (HARDWARE_MODEL)-[:HAS_A]->(HARDWARE_PRODUCT)

      (HARDWARE_MODEL)-[:HAS_A]->(SUPPORT_STAGE)
      
      (HARDWARE_MODEL)-[:HAS_A]->(SUPPORT_STAGE)-[:HAS_A]->(SUPPORT_POLICY)
    title: Relationships
    language: bash
  - code_block: |2-
      [:HAS_A]->(HARDWARE_PRODUCT)
        no attributes
      
      [:HAS_A]->(SUPPORT_STAGE)
        created_at
        modified_at
        end date


    title: Relationship Attributes
    language: bash
---