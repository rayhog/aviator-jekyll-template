---
title: Support
position: 3.9
type: 
description: >-
 You can access Support data from the SUPPORT_STAGE and SUPPORT_POLICY nodes, which are connected to Software and Hardware.

content_markdown: >-
 ###### The CAT is  about CATS
  <br>

  `MATCH (a:SUPPORT_STAGE)-[:HAS_A]-(SUPPORT_POLICY) RETURN a
  {: .info}
  {: .success}

  The following diagram shows the support nodes and relationships.
  <br>
  ![API Image](/images/support.png){:class="img-responsive"} <br> 

  <br>

  
 
  

left_code_blocks:
  - code_block: |-
      curl -G -H "Authorization: Bearer b93477a9-057b-4878-a16b93477a9-057b-4878-a16f-d7f7d1f27a7af-d7f7d1f27a7a" "https://v6.technopedia.com/tql" --data-urlencode' "q=MATCH (h:SUPPORT_STAGE) RETURN h.stage"
    title: cURL Examples
    language: bash


  - code_block: >-
      MATCH (n:SUPPORT_STAGE) RETURN n LIMIT 25

      RESPONSE SAMPLE

      {
          
          }
    title: Example 1
    language: javascript
  - code_block: |-
      MATCH (n:SUPPORT_POLICY) RETURN n LIMIT 25
      
      RESPONSE SAMPLE
      {
          
        }
    title: Example 2
    language: javascript

  - code_block: |-
      MATCH (n:MANUFACTURER)<-[:HAS_A]-(w:SOFTWARE_PRODUCT)-[BELONGS_TO]->(v:CATEGORY_2) RETURN n, w, v

      RESPONSE SAMPLE
      {
          
        }
    title: Example 3
    language: javascript

  - code_block: |-
      MATCH (n:MANUFACTURER)-[:HAS_A]->(p:SOFTWARE_PRODUCT)-[:HAS_A]->(my_alias:SOFTWARE_VERSION) RETURN n, p, my_alias

      RESPONSE SAMPLE
      {
          
        }
    title: Example 4
    language: javascript

  - code_block: |-
      curl -G -H "Authorization: Bearer b93477a9-057b-4878-a16b93477a9-057b-4878-a16f-d7f7d1f27a7af-d7f7d1f27a7a" "https://v6.technopedia.com/tql" --data-urlencode' "q=MATCH (h:MANUFACTURER) RETURN h.manufacturer"

      
    title: Example 5
    language: bash
right_code_blocks:
  - code_block: |2
      SUPPORT_STAGE
      technopedia_id
      support_stage
      order
      created_at
      modified_at
      
      SUPPORT_POLICY
      technopedia_id
      support_policy
      created_at
      modified_at

    title: Support Attributes
    language: bash
  - code_block: |2-
      (SUPPORT_STAGE)-[HAS_A]->[SUPPORT_POLICY]
      
    title: Relationships
    language: bash
---


