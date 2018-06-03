---
title: Software Nodes
position: 1.1
type: 
description: Get software data in Technopedia by using relationships between software nodes
content_markdown: |-
  The following query returns software releases by release name:  
    
  `MATCH (a:SOFTWARE_RELEASE) RETURN a.release`
  {: .info}

  
  Use a combination of the software nodes with relationships to get the data that you specify in your query. 
  The following diagram shows the software nodes, manufacturer node, and relationships.
  <br>
  ![API Image](/images/node_ex.png){:class="img-responsive"} <br> 

  <br>
  Software is a general classification that can be broken into the following classifications
    * Software Product
    * Software Version
    * Software Version Group
    * Software Major Version
    * Software Edition
    * Software Release
    <br>
 
  ![API Image](/images/query.ex.png){: .img-responsive}<br>&nbsp;

left_code_blocks:
  - code_block: |
      MATCH (n:SOFTWARE_PRODUCT)<-[w:HAS_A]-(b:SOFTWARE_VERSION)<-[w:HAS_A]-(z:SOFTWARE_EDITION) RETURN n, b, z

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
      MATCH (n:SOFTWARE_RELEASE) RETURN n.cat_sw_release_id, n.release_url n.ga_date

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

    title: Example 2
    language: javascript
  - code_block: |-
      MATCH (n:SOFTWARE_RELEASE) -[:RELEASE_OF]->(SOFTWARE_PRODUCT) RETURN n.cat_sw_release_id LIMIT 1

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
      MATCH (n:SOFTWARE_VERSION)-[:HAS_A]->(j:SOFTWARE_PRODUCT)-[:BELONGS_TO]->(g:CATEGORY_2) RETURN n, j, g

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
      MATCH (n:SOFTWARE_VERSION)-[:HAS_A]->(r:SOFTWARE_VERSION)-[:HAS_A]->(k:SOFTWARE_PRODUCT) RETURN n, r, k

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
      curl -G -H "Authorization: Bearer b93477a9-057b-4878-a16b93477a9-057b-4878-a16f-d7f7d1f27a7af-d7f7d1f27a7a" "https://v6.technopedia.com/tql" --data-urlencode' "q=MATCH (h:SOFTWARE_PRODUCT) RETURN h.name"

      
    title: cURL
    language: bash
right_code_blocks:
  - code_block: |2
      Software consists of the following nodes:

      * SOFTWARE_PRODUCT
      * SOFTWARE_VERSION
      * SOFTWARE_VERSION_GROUP
      * SOFTWARE_MAJOR_VERSION
      * SOFTWARE_EDITION
      * SOFTWARE_RELEASE

      Query specific software data by using the individual nodes, or use relationships to connect nodes.










      

    title: Software Nodes
    language: bash
  - code_block: |2-
      SOFTWARE NODES RELATIONSHIPS

      (SOFTWARE_PRODUCT)<-[:HAS_A]-(SOFTWARE_EDITION)

      (SOFTWARE_RELEASE)-[:HAS_A]->(SOFTWARE_EDITION)

      (MANUFACTURER)<-[:HAS_A]-(SOFTWARE_PRODUCT)

      (SOFTWARE_VERSION)<-[:HAS_A]-(SOFTWARE_RELEASE)

      (SOFTWARE_VERSION)-[:HAS_A]->(SOFTWARE_VERSION_GROUP)

      (SOFTWARE_VERSION)-[:HAS_A]->(SOFTWARE_MAJOR VERSION)

      (SOFTWARE_RELEASE)-[:HAS_A]->(SUPPORT_STAGE)

      (SOFTWARE_RELEASE)-[:HAS_A]->(SOFTWARE_EDITION)-[:HAS_A]->(SUPPORT_POLICY)

      (SOFTWARE_RELEASE)-[:HAS_A]->(COMPATIBLE_PLATFORM)

      (SOFTWARE_RELEASE)-[:HAS_A]->(CERTIFICATION)

      



    title: Software Nodes Relationships
    language: bash
---