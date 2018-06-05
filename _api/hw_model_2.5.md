---
title: Hardware Model
position: 2.3
type: 
description: The hardware model node defines information about the model, such as dimensions and other general specifications 
content_markdown: |-
  `MATCH (a:HARDWARE_MODEL) RETURN a.model`
  {: .info}
  
  <br>
  <br> 
  The following diagram shows hardware nodes and related software nodes.  
  
  ![API Image](/images/hard_soft.png){:class="img-responsive"} <br>
  
  #### Query Examples <br>
    
  To use the MATCH statements in the following examples, you append the MATCH statement to the following tql endpoint and run a GET request from a API client or use cURL. <br>
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
      MATCH (n:HARDWARE_MODEL)-[:HAS_A]->(m:HARDWARE_PRODUCT) RETURN n, m
         
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

    title: Example two
    language: javascript
  - code_block: |-
      MATCH (n:HARDWARE_MODEL)-[a:HAS_A]->(v:HARDWARE_PRODUCT)<-[a:HAS_A]-(m:MANUFACTURER) RETURN n, m, w, c

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
      MATCH (n:HARDWARE_MODEL)-[a:HAS_A]->(h:HARDWARE_PRODUCT)<-[HAS_A]-(y:MANUFACTURER RETURN n, h, y

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

    title: Example four
    language: javascript

  - code_block: |-
      MATCH (n:HARDWARE_MODEL)-[a:HAS_A]->(h:HARDWARE_PRODUCT)-[e:BELONGS_TO]->(m:CATEGORY_2)-[e:BELONGS_TO]->(w:VERTICAL) RETURN n, h, m, W
      
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

    title: Example five
    language: javascript

  - code_block: |-
      curl -G -H "Authorization: Bearer b93477a9-057b-4878-a16b93477a9-057b-4878-a16f-d7f7d1f27a7af-d7f7d1f27a7a" "https://v6.technopedia.com/tql"  --data-urlencode' "q=MATCH (h:HARDWARE_MODEL) RETURN h.model"
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