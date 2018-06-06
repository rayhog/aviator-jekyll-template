---
title: Software Release
position: 1.6
type:
description: Get software release data from the Technopedia database.

content_markdown: >-
  `MATCH (a:SOFTWARE_RELEASE) RETURN a.release`

  {: .success} 


  &nbsp;
  
  <br>
  The following diagram shows the software nodes,relatinships, and the software release attributes.
  <br>
  ![API Image](/images/sw_release.png){:class="img-responsive"} <br>

  The software release node connects to the software edtion, software nodes, and support stage nodes by the `HAS_A` relationship.
  The software release and support stage nodes are connected by the 'HAS_A' relationship, which has attributes.
  <br>
  To access information about a relationship, you assign it an alias, for later reference. 
  You place the alias in front of the colon `-[my_alias:HAS_A]->`

  The following query returns data for the end date of of the software release's support stage.
  <br>
  `MATCH (:SOFTWARE_RELEASE)-[my_alias:HAS_A {end_date: "2013-12-10 00:00:00"}]->(:SUPPORT_STAGE) RETURN my_alias`

  #### Query Examples <br>
    
  To use the MATCH statements in the following examples, you append the MATCH statement to the following tql endpoint and run a GET request from a API client or use cURL. <br>
  <br>
  `https://v6-1.technopedia.com/tql?q=<MATCH Statement>`
left_code_blocks:
  - code_block: |
      MATCH (n:SOFTWARE_RELEASE) RETURN n.release_id, n.created_at

      RESPONSE SAMPLE
      {
          
          }

    title: Example one
    language: javascript
  - code_block: >-
      MATCH (node)-[My_alias:relationship {relationship_attribute : value}]->(:node) Return My_alias


      MATCH (:SOFTWARE_RELEASE)-[h:HAS_A {end_date: "2013-12-10 00:00:00"}]->(:SUPPORT_STAGE) RETURN h
      

      RESPONSE SAMPLE

      {
        "results": [
            {
                "end_date": "2013-12-10 00:00:00",
                "modified_at": "2018-05-04 20:01:57",
                "created_at": "2018-05-03 17:29:30"
            }
        ]
      {  
    title: Example two
    language: javascript
  - code_block: |-
      MATCH (srelease:SOFTWARE_RELEASE) -[:HAS_A]->(sver:SOFTWARE_VERSION)-[:HAS_A]->(sprod:SOFTWARE_PRODUCT)-[:HAS_A]->(manu:MANUFACTURER) RETURN srelease.release, sver.version, sprod.product, manu.manufacturer LIMIT 2

      QUERY INTENT
      Return release name, software version, software product name, and manufacturer name for 2 software releases

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
      MATCH (srelease:SOFTWARE_RELEASE) -[:HAS_A]->(sver:SOFTWARE_VERSION)-[HAS_A]->(smajor:SOFTWARE_VERSION_GROUP) RETURN srelease.release, sver.version, smajor.version_group LIMIT 2
      
      QUERY INTENT
      Return release name, software version and software group version for 2 software releases.

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
      MATCH (srelease:SOFTWARE_RELEASE) -[:HAS_A]->(sver:SOFTWARE_VERSION)-[HAS_A]->(smajor:SOFTWARE_MAJOR_VERSION) RETURN srelease.release, sver.version, smajor.version LIMIT 2
      Return release name, software version and software major version for 2 software releases.

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
      curl -G -H "Authorization: Bearer b93477a9-057b-4878-a16b93477a9-057b-4878-a16f-d7f7d1f27a7af-d7f7d1f27a7a" "https://v6-1.technopedia.com/tql" --data-urlencode' "q=MATCH (n:SOFTWARE_RELEASE) WHERE n.release contains "studio" RETURN n

      
      
    title: cURL
    language: bash
right_code_blocks:
  - code_block: |-
      technopedia_id
      release
      discontinued_flag
      desupported_flag
      url
      created_at
      modified_at
      
    title: Software Release Attributes
    language: bash
  - code_block: |2-
      (SOFTWARE_RELEASE)-[:HAS_A]->(SOFTWARE_VERSION)

      (SOFTWARE_RELEASE)-[:HAS_A]->(SOFTWARE_EDITION)

      (SOFTWARE_RELEASE)-[:HAS_A]->(SUPPORT_STAGE)
      Relationship attributes: 
      created_at
      modified_at
      end_date

      (SOFTWARE_RELEASE)-[:HAS_A]->(COMPATIBLE_PLATFORM)
      Relationship attributes: 
      status                          
      description
      upgrade_path
      date
       
      (SOFTWARE_RELEASE)-[:HAS_A]->(CERTIFICATION)
      Relationship attributes: 
      certified
      title: Relationships
    language: bash
right_code_blocks:
  - code_block: |2
      technopedia_id
      cat_sw_release_id
      discontinued_flag
      desupported_flag
      url
      created_at
      modified_at
      
    title: Software Release Attributes
    language: bash
  - code_block: |2-
      (SOFTWARE_RELEASE)-[:HAS_A]->(SOFTWARE_VERSION)

      (SOFTWARE_RELEASE)-[:HAS_A]->(SOFTWARE_EDITION)

      (SOFTWARE_RELEASE)-[:HAS_A]->(SUPPORT_STAGE)
      Relationship attributes: 
      created_at
      modified_at
      end_date

      (SOFTWARE_RELEASE)-[:HAS_A]->(COMPATIBLE_PLATFORM)
      Relationship attributes: 
      status
      description
      upgrade_path
      date
       
      (SOFTWARE_RELEASE)-[:HAS_A]->(CERTIFICATION)
      Relationship attributes: 
      certified
    title: Relationships
    language: bash
---

