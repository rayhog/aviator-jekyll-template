---
title: Hardware Model
position: 2.5
type: 
description: The hardware model node defines information about the model, such as dimensions and other general specifications 
content_markdown: |-

  `MATCH (a:HW_MODEL) RETURN a.model`
  {: .info}
  
  <br>

  <br> 
    
  
  ![API Image](/images/apiEcon.PNG){:class="img-responsive"} <br>
  
  ###### Returns a specific hardware item from the Technopedia database.<br> 
  ![API Image](/images/tid.png){:class="img-responsive"} <br>

left_code_blocks:
  - code_block: |-
      curl -G -H "Authorization: Bearer b93477a9-057b-4878-a16b93477a9-057b-4878-a16f-d7f7d1f27a7af-d7f7d1f27a7a" "https://v6.technopedia.com/tql" --data-urlencode' "q=MATCH (h:MANUFACTURER) RETURN h.manufacturer"
    title: cURL Examples
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
      [:MODEL_OF]->(HARDWARE_PRODUCT)
      [:POWER]->(POWER_PROFILE)
      [:SUPPORT_STAGE]->(SUPPORT_STAGE)
    title: Relationships
    language: bash
  - code_block: |2-
      [:MODEL_OF]->(HARDWARE_PRODUCT)
        no attributes

      [:POWER]->(POWER_PROFILE)
        power_max
        power_max_unit
        power_average
        power_average_unit
        created_at
        modified_at


      [:SUPPORT_STAGE]->(SUPPORT_STAGE)
        created_at
        modified_at
        end date


    title: Relationship Attributes
    language: bash
---