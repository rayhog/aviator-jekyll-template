---
title: Hardware Product
position: 2.2
type: 
description: Hardware information in Technopedia is classified by product, model, and power. 
content_markdown: |-

  `MATCH (n:HARDWARE_PRODUCT) RETURN n LIMIT 25`
   {: .info}
  
  <br>
  The following image shows the hardware nodes, relationships, and relevant connections.
    
  ![API Image](/images/hardware.png){:class="img-responsive"} <br>
  <br>
  ####
  Query Examples <br>
      

  To use the MATCH statements in the following examples, you append the MATCH statement to the following tql endpoint and run a GET request from a API client or use cURL.<br>
  `https://v6-1.technopedia.com/tql?q=<MATCH Statement>`



left_code_blocks:
  - code_block: |
      MATCH (n:HARDWARE_PRODUCT) RETURN n.product, n.desupported_flag

      RESPONSE SAMPLE
      { 

        "results": [
            {
                "n.desupported_flag": null,
                "n.product": "Express5800/A1080a Series"
            },
            {
                "n.desupported_flag": null,
                "n.product": "Phaser 3125 (Networked)"
            {
                "n.desupported_flag": "TRUE",
                "n.product": "ProLiant BL460c G6 Server Blade"
            },    
                        {
                "n.desupported_flag": null,
                "n.product": "Pro 3010 Desktop PC"
            },
            {
                "n.desupported_flag": null,
                "n.product": "Essentio Series"
            },
            {
                "n.desupported_flag": null,
                "n.product": "DX100 Series"
            },
            {
                "n.desupported_flag": null,
                "n.product": "500 Series Notebook PC"
            },
            {
                "n.desupported_flag": null,
                "n.product": "ThinkCentre A51"
            },
            {
                "n.desupported_flag": null,
                "n.product": "3Com OfficeConnect Cable/DSL Gateway"
            }
        ]
      {    
            

    title: Example one
    language: javascript

    
  - code_block: >-
      MATCH (product:HARDWARE_PRODUCT)<-[:HAS_A]-(model:HARDWARE_MODEL) RETURN  product, model


      RESPONSE SAMPLE

      {  
        "results": [
        {
            "model.cpu_sockets": 4,
            "model.cpu_url": "http://www.necam.com/docs/?id=6ee81afc-8691-484e-9549-b21b83f6302e",
            "model.created_at": "2010-04-23 11:31:47",
            "model.date_introduced": "3/30/2010",
            "model.desupported_flag": null,
            "model.model": "A1080a-S",
            "model.modified_at": "2013-10-18 16:54:07",
            "model.technopedia_id": "807bd3dc-2100-4116-a4e2-cbf741e725d4",
            "product.cat_manufacturer_id": null,
            "product.create_date": null,
            "product.desupported_flag": null,
            "product.modified_at": "2011-03-16 09:46:45",
            "product.product": "Express5800/A1080a Series",
            "product.technopedia_id": "f6d32439-001b-4ca7-abb1-cd7627086ade"
        },
        {
            "model.cpu_sockets": 8,
            "model.cpu_url": "http://www.necam.com/docs/?id=6ee81afc-8691-484e-9549-b21b83f6302e",
            "model.created_at": "2010-04-23 11:32:43",
            "model.date_introduced": "3/30/2010",
            "model.desupported_flag": null,
            "model.model": "A1080a-E",
            "model.modified_at": "2013-10-18 16:54:22",
            "model.technopedia_id": "5cb93d0e-63d0-43eb-89d8-7d1d25ff4ce5",
            "product.cat_manufacturer_id": null,
            "product.create_date": null,
            "product.desupported_flag": null,
            "product.modified_at": "2011-03-16 09:46:45",
            "product.product": "Express5800/A1080a Series",
            "product.technopedia_id": "f6d32439-001b-4ca7-abb1-cd7627086ade"
        }
       ]
      {  
    title: Example two
    language: javascript
  - code_block: |-
      MATCH (hw:HARDWARE_PRODUCT)-[a:BELONGS_TO]->(cat_2:CATEGORY_2)-[e:BELONGS_TO]->(cat_1:CATEGORY_1)-[y:BELONGS_TO]->(cat_group:CATEGORY_GROUP) RETURN hw, cat_2, cat_1, cat_group LIMIT 2

      RESPONSE SAMPLE
      {  
         "results": [
        {
            "cat_1.cat_taxonomy2012_id": null,
            "cat_1.description": "The process of preserving the landscape clean, safe, and 
             attractive.",
            "cat_1.label": "Landscape Maintenance",
            "cat_1.technopedia_id": "ef2864c2-4215-4ee7-b373-d6054560cca9",
            "cat_2.cat_taxonomy2012_id": null,
            "cat_2.cat_taxonomy2012_parent_id": null,
            "cat_2.description": "A group of devices that is designed to maintain and protect the 
             environment.",
            "cat_2.label": "Environmental Monitoring and Protection",
            "cat_2.technopedia_id": "56974f54-ef68-48fa-871f-efbfb6144baa",
            "cat_group.label": "Building Maintenance",
            "hw.cat_manufacturer_id": null,
            "hw.create_date": null,
            "hw.desupported_flag": null,
            "hw.modified_at": "2017-09-06 11:16:36",
            "hw.product": "Ecomar",
            "hw.technopedia_id": "f7796096-89fc-4dec-a949-15730d4915c6"
        },
        {
            "cat_1.cat_taxonomy2012_id": null,
            "cat_1.description": "The process of preserving the landscape clean, safe, and attractive.",
            "cat_1.label": "Landscape Maintenance",
            "cat_1.technopedia_id": "ef2864c2-4215-4ee7-b373-d6054560cca9",
            "cat_2.cat_taxonomy2012_id": null,
            "cat_2.cat_taxonomy2012_parent_id": null,
            "cat_2.description": "An irrigation control system is a device used to operate 
             automatic watering systems such as drip irrigation systems or lawn sprinklers.",  
            "cat_2.label": "Irrigation System",
            "cat_2.technopedia_id": "6b727766-ac35-422b-8046-6c9f17d13160",
            "cat_group.label": "Building Maintenance",
            "hw.cat_manufacturer_id": null,
            "hw.create_date": null,
            "hw.desupported_flag": null,
            "hw.modified_at": "2017-12-12 17:16:26",
            "hw.product": "SmartLine Controller",
            "hw.technopedia_id": "b60dc2ae-c262-4cbc-9baa-6df87270745f"
       }
        ]
      {       
        
    title: Example three
    language: javascript

  - code_block: |-
      MATCH (hw:HARDWARE_PRODUCT)-[a:HAS_A]->(manu:MANUFACTURER) RETURN hw, manu.manufacturer

      RESPONSE SAMPLE
      {
          
        "results": [
            {
                "hw.cat_manufacturer_id": null,
                "hw.create_date": null,
                "hw.desupported_flag": null,
                "hw.modified_at": "2011-03-16 09:46:45",
                "hw.product": "Express5800/A1080a Series",
                "hw.technopedia_id": "f6d32439-001b-4ca7-abb1-cd7627086ade",
                "manu.manufacturer": "NEC"
            },
            {
                "hw.cat_manufacturer_id": null,
                "hw.create_date": null,
                "hw.desupported_flag": null,
                "hw.modified_at": "2011-03-21 11:22:10",
                "hw.product": "Phaser 3125 (Networked)",
                "hw.technopedia_id": "4d35ec28-0f16-4787-acca-885679265b59",
                "manu.manufacturer": "Xerox"
            },
            {
                "hw.cat_manufacturer_id": null,
                "hw.create_date": null,
                "hw.desupported_flag": null,
                "hw.modified_at": "2017-06-01 11:29:10",
                "hw.product": "Pro 3010 Desktop PC",
                "hw.technopedia_id": "e2b8fab2-681f-48f5-8ac7-57cb7f36e97b",
                "manu.manufacturer": "Hewlett-Packard Company"
           }
        ]
      {  
        
      
        
    title: Example four
    language: javascript

  - code_block: |-
      https://v6-1.technopedia.com/tql?q=MATCH (hardware:HARDWARE_PRODUCT)-[a:BELONGS_TO]->(cat_2:CATEGORY_2)-[e:BELONGS_TO]->(vertical:VERTICAL) RETURN hardware, cat_2, vertical
      
      RESPONSE SAMPLE
      {
        "results": [
          {
              "cat_2.cat_taxonomy2012_id": null,
              "cat_2.cat_taxonomy2012_parent_id": null,
              "cat_2.description": "A computer or device on a network that manages network resource",
              "cat_2.label": "Servers",
              "cat_2.technopedia_id": "195fa6b3-7d0f-4317-995f-d3c9f1ae08e7",
              "hardware.cat_manufacturer_id": null,
              "hardware.create_date": null,
              "hardware.desupported_flag": null,
              "hardware.modified_at": "2011-03-16 09:46:45",
              "hardware.product": "Express5800/A1080a Series",
              "hardware.technopedia_id": "f6d32439-001b-4ca7-abb1-cd7627086ade",
              "vertical.name": "Information and Technology",
              "vertical.short_name": "IT",
              "vertical.technopedia_id": "0be7a9ed-b538-4942-b6ce-b9243566305f"
          },
          {
              "cat_2.cat_taxonomy2012_id": null,
              "cat_2.cat_taxonomy2012_parent_id": null,
              "cat_2.description": "A common type of computer printer that rapidly produces high  quality text and graphics on plain paper. It employs a xerographic printing 
               process, where image is produced by the direct scanning of a laser beam across the printer's photoreceptor",  
              "cat_2.label": "Laser Printers",
              "cat_2.technopedia_id": "bcb655cc-b5ef-4915-838f-8ff68cb65cce",
              "hardware.cat_manufacturer_id": null,
              "hardware.create_date": null,
              "hardware.desupported_flag": null,
              "hardware.modified_at": "2011-03-21 11:22:10",
              "hardware.product": "Phaser 3125 (Networked)",
              "hardware.technopedia_id": "4d35ec28-0f16-4787-acca-885679265b59",
              "vertical.name": "Medical and Health Care",
              "vertical.short_name": "MD",
              "vertical.technopedia_id": "81520b3f-6ffc-42c7-afce-a25bbdc63385"
          }
        ]
      {  
    title: Example five
    language: javascript

  - code_block: |-
      curl -G -H "Authorization: Bearer b93477a9-057b-4878-a16b93477a9-057b-4878-a16f-d7f7d1f27a7af-d7f7d1f27a7a" "https://v6.technopedia.com/tql" --data-urlencode' "q=MATCH (h:HARDWARE_PRODUCT) RETURN h.product"

      
    title: cURL
    language: bash    
right_code_blocks:
  - code_block: |2
      technopedia_id
      product
      desupported_flag
      create_date
      modified_at
    title: Hardware Product Attributes
    language: bash
  - code_block: |2-
      (HARDWARE_PRODUCT)-[:HAS_A]<-(MANUFACTURER)
                
      (HARDWARE_PRODUCT)-[:BELONGS_TO]->(CATEGORY_2)

      (HARDWARE_PRODUCT)-[:HAS_A]->(SUPPORT_STAGE)

      (HARDWARE_PRODUCT)-[:HAS_A]->(SUPPORT_STAGE)-[:HAS_A]->(SUPPORT_POLICY)
            
      (HARDWARE_PRODUCT)-[:HAS_A]->(CERTIFICATION)


      
      
    title: Relationships
    language: bash
---