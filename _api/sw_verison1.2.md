---
title: Software Version
position: 1.2
type: 
description: >-
  Software versions are represented by two nodes. The Software Group Version represents the major or group version attributes and the software version represents the attributes that are associated with child versions of the parent major version. The relationship bewtween the nodes is `HAS_A` which points from `SOFTWARE_VERSION` towards `SOFTWARE_MAJOR_VERSION`.
content_markdown: >-
  Gets software version information
  <br>
  <br>
  

  `MATCH (a:SOFTWARE_VERSION) RETURN a.version`

  {: .success} 
  
  <br>
  The following diagaram shows the nodes, attributes, and relationships that feature software nodes and their relationships.
  <br>
  ![API Image](/images/sw_rel_to_ver.png){:class="img-responsive"} <br>
  ### Software Version Group
  
  ######
  The node that represents the major version of software is `SOFTWARE_GROUP_VERSION`.
  Software versioning is used to categorize the unique states of software as it is developed and released. The version identifier might be a word, or a number, or inlcude both. For example, version 1.0 is often used to represent the initial release of a software product.

  Gets software version information

  `MATCH (a:SOFTWARE_GROUP_VERSION) RETURN a.version`

  {: .success} 


  <br>
  


  
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
      MATCH (n:SOFTWARE_RELEASE) -[:HAS_A]->(SOFTWARE_PRODUCT) RETURN n.cat_sw_release_id LIMIT 1

      RESPONSE SAMPLE
      {
          
        }
    title: Example 3
    language: javascript

  - code_block: |-
    title: Example 4
    language: bash

  - code_block: |-
    title: Example 5
    language: bash

  - code_block: |-
    title: cURL
    language: bash

right_code_blocks:
  - code_block: |2
      VERSION ATTRIBUTES
      technopedia_id
      cat_sw_version_id
      version
      version_patchlevel
      is_major
      version_order
      created_at


      MAJOR VERSION GROUP
      technopedia_id
      version
      cat_sw_major_version_id

    title: Software Version Attributes
    language: bash
  - code_block: |2-
      (SOFTWARE_VERSION)<-[:HAS_A)]-(SOFTWARE_RELEASE)

      (SOFTWARE_VERSION)-[:HAS_A)]->(SOFTWARE_PRODUCT)

      (SOFTWARE_VERSION)-[:BELONGS_TO]->(SOFTWARE_GROUP_VERSION)
    title: Relationships
    language: bash
---

