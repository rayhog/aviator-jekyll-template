---
title: Hardware Product
position: 2.2
type: 
description: Hardware information in Technopedia is classified by product, model, and power. 
content_markdown: |-

  `MATCH (n:HARDWARE_PRODUCT) RETURN n LIMIT 25`
  {: .info}
  
  <br>


  <br> 
  IMAGE LATER 
  
  ![API Image](/images/hardware.png){:class="img-responsive"} <br>
  
  ###### Returns a specific hardware item from the Technopedia database.<br> 
  ![API Image](/images/tid.png){:class="img-responsive"} <br>



left_code_blocks:
  - code_block: |
      MATCH (n:HARDWARE_PRODUCT) RETURN n.product, n.create_date

      RESPONSE SAMPLE
      {
          
          }

    title: Example 1
    language: javascript

    
  - code_block: >-
      MATCH (n:HARDWARE_PRODUCT)<-[:HAS_A]-(m:HARDWARE_MODEL) RETURN n, m


      RESPONSE SAMPLE

      {
          
          }
    title: Example 2
    language: javascript
  - code_block: |-
      https://v6-1.technopedia.com/tql?q=MATCH (hw:HARDWARE_PRODUCT)-[a:BELONGS_TO]->(cat_2:CATEGORY_2)-[e:BELONGS_TO]->(cat_1:CATEGORY_1)-[y:BELONGS_TO]->(cat_group:CATEGORY_GROUP) RETURN hw, cat_2, cat_1, cat_group LIMIT 2

      RESPONSE SAMPLE
      {  
         "results": [
        {
            "cat_1.cat_taxonomy2012_id": null,
            "cat_1.description": "The process of preserving the landscape clean, safe, and attractive.",
            "cat_1.label": "Landscape Maintenance",
            "cat_1.technopedia_id": "ef2864c2-4215-4ee7-b373-d6054560cca9",
            "cat_2.cat_taxonomy2012_id": null,
            "cat_2.cat_taxonomy2012_parent_id": null,
            "cat_2.description": "A group of devices that is designed to maintain and protect the environment.",
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
            "cat_2.description": "An irrigation control system is a device used to operate automatic watering systems such as drip irrigation systems or lawn sprinklers.",
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
        
    title: Example 3
    language: javascript

  - code_block: |-
      MATCH (n:HARDWARE_PRODUCT)-[a:BELONGS_TO]->(m:CATEGORY_2)-[e:BELONGS_TO]->(w:VERTICAL) RETURN n, m, w


      RESPONSE SAMPLE
      {
          
        }
    title: Example 4
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
              "cat_2.description": "A common type of computer printer that rapidly produces high quality text and graphics on plain paper. It employs a xerographic printing process, where image is produced by the direct scanning of a laser beam across the printer's photoreceptor",
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
          },
            
          }
    title: Example 5
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
      
      (HARDWARE_PRODUCT)-[:HAS_A]->(CERTIFICATION)


      
      
    title: Relationships
    language: bash
---