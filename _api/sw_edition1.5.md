---
title: Software Edition
position: 1.5
type: 
description: Matches the software edition from the Technopedia database.
content_markdown: |-
  Software edition represents the version of the product, such as Standard, Premium, or other version name for the product.
  <br>


  `MATCH (e:SOFTWARE_EDITION {edition: '24853332'}) RETURN e`
  {: .success}

  <br>
  Here's an example of querying the release title "Advanced Partitioning Option" that is a release of a software version.<br>
  <br>
  `MATCH (s.SOFTWARE_PRODUCT)<-[:HAS_A]-(n:SOFTWARE_EDITION) WHERE n.release_title = "Advanced Partitioning Option" RETURN n`
  <br>

  ![API Image](/images/sw_edition.png){:class="img-responsive"} <br>

  #### Query Examples <br>
    
  Run any of the MATCH query statements in the examples with the TQL enpoint <br> `https://v6.technopedia.com/tql` in an API client, or use cURL.

left_code_blocks:
  - code_block: |
      MATCH (n:SOFTWARE_RELEASE) RETURN n.release, n.modified_at

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

    title: Example one
    language: javascript
  - code_block: >-
      MATCH (n:SOFTWARE_RELEASE) RETURN n.release, n.url, n.technopedia_id

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
    title: Example two
    language: javascript
  - code_block: |-
      MATCH (n:SOFTWARE_RELEASE)-[p:HAS_A]->(a:SOFTWARE_VERSION)-[o:HAS_A]->(g:SOFTWARE_PRODUCT) RETURN n.name LIMIT 5

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
      MATCH (n:SOFTWARE_RELEASE)-[:HAS_A]->(x:SOFTWARE_VERSION) RETURN x.version LIMIT 10

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
      MATCH (n:SOFTWARE_EDITION) -[:HAS_A]->(u:SOFTWARE_PRODUCT) RETURN n, u LIMIT 10

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
      curl -G -H "Authorization: Bearer b93477a9-057b-4878-a16b93477a9-057b-4878-a16f-d7f7d1f27a7af-d7f7d1f27a7a" "https://v6.technopedia.com/tql" --data-urlencode' "q=MATCH (h:SOFTWARE_EDITION) RETURN h.edition"

      
    title: cURL
    language: bash
right_code_blocks:
  - code_block: |2
      technopedia_id
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

      (SOFTWARE_EDITION)-[:HAS_A]->(SOFTWARE_RELEASE)

      (SOFTWARE_EDITION)-[:HAS_A]->(SOFTWARE_PRODUCT)
      
      (SOFTWARE_EDITION)<-[:HAS_A]->(SOFTWARE_RELEASE)-[:HAS_A]->(SUPPORT_STAGE)

      (SOFTWARE_EDITION)<-[:HAS_A]->(SOFTWARE_RELEASE)-[:HAS_A]->(COMPATIBLE_PLATFORM)

      

      



    title: Relationships
    language: bash
---

