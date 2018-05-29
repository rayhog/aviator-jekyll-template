---
title: Power Profile
position: 2.7
type: 
description: The power profile node represents harware power attributes.
content_markdown: |-

  `MATCH (a:POWER_PROFILE) RETURN a.label`
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
      Technopedia_id
      Edition
      Edition_Desupported_Flag
      Edition_Order
      URL
      Created_At
      Modified_At
    title: Software Product Attributes
    language: bash
  - code_block: |2-
      [:VENDOR_OF]->(MANUFACTURER)
    title: Relationships
    language: bash
---