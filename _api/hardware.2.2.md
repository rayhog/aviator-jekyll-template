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
      MATCH (n:HARDWARE_PRODUCT)-[a:BELONGS_TO]->(m:CATEGORY_2)-[e:BELONGS_TO]->(w:CATEGORY_1)-[y:BELONGS_TO]->(c:CATEGORY_GROUP) RETURN n, m, w, c

      RESPONSE SAMPLE
      {
          
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
      MATCH (n:HARDWARE_PRODUCT)-[a:BELONGS_TO]->(m:CATEGORY_2)-[e:BELONGS_TO]->(w:VERTICAL) RETURN n, m, w
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
      (HARDWARE_PRODUCT)-[:HAS_A]<-(MANUFACTURER)
                
      (HARDWARE_PRODUCT)-[:BELONGS_TO]->(CATEGORY_2)

      (HARDWARE_PRODUCT)-[:HAS_A]->(SUPPORT_STAGE)
      
      (HARDWARE_PRODUCT)-[:HAS_A]->(CERTIFICATION)


      
      
    title: Relationships
    language: bash
---