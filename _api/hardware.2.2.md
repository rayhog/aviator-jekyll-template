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
      MATCH (n:SOFTWARE_RELEASE) RETURN n.cat_sw_release_id, n.ga_date

      RESPONSE SAMPLE
      {
          
          }

    title: Example 1
    language: javascript

    
  - code_block: >-
      MATCH (n:SOFTWARE_RELEASE) RETURN n.cat_sw_release_id, n.release_url n.ga_date


      RESPONSE SAMPLE

      {
          
          }
    title: Example 2
    language: javascript
  - code_block: |-
      MATCH (n:SOFTWARE_RELEASE) -[:RELEASE_OF]->(SOFTWARE_PRODUCT) RETURN n.cat_sw_release_id LIMIT 1

      RESPONSE SAMPLE
      {
          
        }
    title: Example 3
    language: javascript

  - code_block: |-
      MATCH (n:SOFTWARE_RELEASE) -[:RELEASE_OF]->(SOFTWARE_PRODUCT) RETURN n.cat_sw_release_id LIMIT 1

      RESPONSE SAMPLE
      {
          
        }
    title: Example 4
    language: javascript

  - code_block: |-
      MATCH (n:SOFTWARE_RELEASE) -[:RELEASE_OF]->(SOFTWARE_PRODUCT) RETURN n.cat_sw_release_id LIMIT 1

      RESPONSE SAMPLE
      {
          
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
      [:HAS_A]<-(MANUFACTURER)
      [:HAS_A]->(CERTIFICATION)
      [:BELONGS_TO]->(CATEGORY_2)

      
      
    title: Relationships
    language: bash
---