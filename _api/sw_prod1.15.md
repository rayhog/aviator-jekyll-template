---
title: Software Product
position: 1.15
type:
description: >-
  In the following query example, you get data from Technopedia that contains PDF Converter in the name of the software product name.
content_markdown: >-
  `MATCH (n:SOFTWARE_PRODUCT) WHERE n.name = "PDF Converter" RETURN n` 
  
  {: .success} 
  
  The following diagram shows the software nodes and relationships.

   ![API Image](/images/NodeAndRel.png){: .img-responsive}<br>&nbsp;
  
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
      curl -G -H "Authorization: Bearer b93477a9-057b-4878-a16b93477a9-057b-4878-a16f-d7f7d1f27a7af-d7f7d1f27a7a" "https://v6.technopedia.com/tql" --data-urlencode' "q=MATCH (h:CPU) RETURN h.cores"

      
    title: cURL
    language: bash
    
right_code_blocks:
  - code_block: |2
      technopedia_id
      product
      family
      component
      is_suite
      product_desupported_flag
      product_discontinued_flag
      product_url
      created_at
      modified_at
      "alias"



      

      
    title: Software Product Attributes
    language: bash
  - code_block: |2-
      (SOFTWARE_PRODUCT)<-[:HAS_A]-(SOFTWARE_EDITION)

      (SOFTWARE_PRODUCT)-[:HAS_A]->(MANUFACTURER)

      (SOFTWARE_PRODUCT)-[:HAS_A]->(SOFTWARE_VERSION)
      
      (SOFTWARE_PRODUCT)-[:BELONGS_TO]->(CATEGORY_2)
      

    title: Relationships
    language: bash
---

