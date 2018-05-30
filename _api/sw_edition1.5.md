---
title: Software Edition
position: 1.5
type: 
description: Matches the software edition from the Technopedia database.
content_markdown: |-
  Software edition represents the version of the product, such as Standard, Premium, or other version name for the product.
  <br>


  `MATCH (e:SOFTWARE_EDITION {cat_sw_edition_id: '24853332'})-[*1..3]->(b) RETURN b LIMIT 10`
  {: .success}

  <br>
  Here's an example of querying the release title "Advanced Partitioning Option" that is a release of a software version.<br>
  <br>
  `MATCH (SOFTWARE_PRODUCT)<-[:EDITION_OF]-(SOFTWARE_EDITION) WHERE n.release_title = "Advanced Partitioning Option" RETURN n`
  <br>

  ![API Image](/images/sw_edition.png){:class="img-responsive"} <br>

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
      cat_sw_edition_id
      edition
      edition_desupported_flag
      edition_order
      url
      created_at
      modified_at

    title: Software Edition Attributes
    language: bash
  - code_block: |2-
      (SOFTWARE_EDITION)<-[:EDITION_OF]-(SOFTWARE_EDITION)
      (SOFTWARE_EDITION)-[:EDITION_OF]->(SOFTWARE_PRODUCT) 
    title: Relationships
    language: bash
---

