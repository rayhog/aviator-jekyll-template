---
title: Software Version
position: 1.2
type: 
description: >-
  Software versions are represented by three nodes. The Software Version Group node represents the group version attributes. 
  The software version node represents the attributes that are associated with child versions of the parent major version or version group.

  The relationship bewtween the nodes is `HAS_A` which points from `SOFTWARE_VERSION` to `SOFTWARE_VERSION_GROUP` and `SOFTWARE_MAJOR_VERSION.
content_markdown: >-
  The highlighted query returns version information for software versions.
  <br>
  
  

  `MATCH (a:SOFTWARE_VERSION) RETURN a.version`

  {: .success} 
  
  <br>
  The following diagram shows the nodes, attributes, and relationships that feature software nodes and their relationships.
  <br>
  ![API Image](/images/sw_rel_to_ver.png){:class="img-responsive"} <br>

  ### Software Version Group
  
  ######
  The node that represents the major version of software is `SOFTWARE_MAJOR_VERSION`.
  Software versioning is used to categorize the unique states of software as it is developed and released. 
  The version identifier might be a word, or a number, or inlcude both. For example, version 1.0 is often used to represent the initial release of a software product.

  Gets software version information <br>

  `MATCH (a:SOFTWARE_MAJOR_VERSION) RETURN a.version`

  {: .success} <br>

  ### Software Major Group
  
  ######
  The node that represents the major version of software is `SOFTWARE_VERSION_GROUP`.
  Software version group is used to categorize the software when the version is part of version group that may or may not have a major version.

  Gets software version group information

  `MATCH (a:SOFTWARE_VERSION_GROUP) RETURN a.version`

  {: .success} 


  <br>


  
left_code_blocks:
  - code_block: |
      MATCH (n:SOFTWARE_RELEASE) RETURN n.cat_sw_release_id, n.ga_date

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
    title: Example two
    language: javascript
  - code_block: |-
      MATCH (n:SOFTWARE_RELEASE) -[:HAS_A]->(SOFTWARE_PRODUCT) RETURN n.cat_sw_release_id LIMIT 1

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
        }

    title: Example 3
    language: javascript

  - code_block: |-
      MATCH
      
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

    title: Example 4
    language: bash


  - code_block: |-

      MATCH
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
        
    title: Example 5
    language: bash

  - code_block: |-
    title: cURL
    language: bash

right_code_blocks:
  - code_block: |2
      VERSION ATTRIBUTES
      technopedia_id
      version
      order
      created_at
      modified_at


      SOFTWARE VERSION GROUP
      technopedia_id
      version_group
      modified_at
      

      SOFTWARE MAJOR VERSION 
      technopedia_id
      version
      

    title: Software Version Attributes
    language: bash
  - code_block: |2-
      (SOFTWARE_VERSION)<-[:HAS_A)]-(SOFTWARE_RELEASE)

      (SOFTWARE_VERSION)-[:HAS_A)]->(SOFTWARE_PRODUCT)

      (SOFTWARE_VERSION)-[:HAS_A]->(SOFTWARE_VERSION_GROUP)

      (SOFTWARE_VERSION)-[:HAS_A]->(SOFTWARE_MAJOR_VERSION)


    title: Relationships
    language: bash
---

