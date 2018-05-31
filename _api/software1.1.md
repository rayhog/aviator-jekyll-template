---
title: Software Nodes
position: 1.1
type: 
description: Get software data by using relationships between software nodes
content_markdown: |-
  The following query returns software releases by title:  
    
  `MATCH (a:SOFTWARE_RELEASE) RETURN a.release.title`
  {: .info}

  <br>
  Software is a general classification that can be broken into the following classifications
    * Software Product
    * Software Version
    * Software Group Version
    * Software Edition
    * Software Release
  
  
  Use a combination of the software nodes with relationships to get the data that you specify in your query.
  <br>
  ![API Image](/images/node_ex.png){:class="img-responsive"} <br> 
 
  
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
      Software consists of the following five nodes:

      * SOFTWARE_PRODUCT
      * SOFTWARE_VERSION
      * SOFTWARE_VERSION_GROUP
      * SOFTWARE_EDITION
      * SOFTWARE_RELEASE

      Query specific software data by using the individual nodes, or use relationships to connect nodes.










      

    title: Software Nodes
    language: bash
  - code_block: |2-
      SOFTWARE NODES RELATIONSHIPS

      (SOFTWARE_PRODUCT)<-[:HAS_A]-(SOFTWARE_EDITION)

      (MANUFACTURER)-[:HAS_A]->(SOFTWARE_PRODUCT)

      (SOFTWARE_VERSION)<-[:HAS_A]-(SOFTWARE_RELEASE)

      (SOFTWARE_VERSION)<-[:BELONGS_TO]-(SOFTWARE_VERSION_GROUP)
    title: Software Nodes Relationships
    language: bash
---