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
    
  
  ![API Image](/images/graph.PNG){:class="img-responsive"} <br>
  
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
      edition
      edition_desupported_flag
      edition_order
      URL
      created_at
      modified_at
    title: Software Product Attributes
    language: bash
  - code_block: |2-
    (:)<->(MANUFACTURER)
    title: Relationships
    language: bash
---