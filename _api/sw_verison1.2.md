---
title: Software Version
position: 1.2
type: 
description: >-
  Software versions are represented by two nodes. The Software major version represents the major version attributes and the software version represents the attributes that are associated with child versions of the parent major version. The relationship bewtween the nodes is `MAJOR_VERSION_OF` which point to `SOFTWARE_VERSION` from `SOFTWARE_MAJOR_VERSION`
content_markdown: >-
  Gets software version information
  <br>
  <br>
  

  `MATCH (a:SOFTWARE_VERSION) RETURN a.version`

  {: .success} 
  
  <br>

  ### Software Version Group
  
  ######
  The node that represents the major version of software is `SOFTWARE_GROUP_VERSION`.
  Software versioning is used to categorize the unique states of software as it is developed and released. The version identifier might be a word, or a number, or inlcude both. For example, version 1.0 is often used to represent the initial release of a software product.


  `MATCH (a:SOFTWARE_GROUP_VERSION) RETURN a.version`

  {: .success} 


  <br>
  


  
left_code_blocks:
  - code_block: |
      MATCH (n:SOFTWARE_RELEASE) RETURN n.cat_sw_release_id, n.ga_date

      RESPONSE SAMPLE
      {
          "keys": [
            "n.cat_sw_release_id",
            "n.ga_date"
          ],
          "length": 2,
          "_fields": [
            {
              "low": 55725913,
              "high": 0
            },
            "Not Available"
          ],
          "_fieldLookup": {
            "n.cat_sw_release_id": 0,
            "n.ga_date": 1
          }

    title: Example 1
    language: javascript
  - code_block: >-
      MATCH (n:SOFTWARE_RELEASE) RETURN n.cat_sw_release_id, n.release_url n.ga_date


      RESPONSE SAMPLE

      {
          "keys": [
            "n.cat_sw_release_id",
            "n.release_url",
            "n.ga_date"
          ],
          "length": 3,
          "_fields": [
            {
              "low": 10427852,
              "high": 0
            },
            "www.nntest.com/files/import/Solutions%20Catalog%20Data.xls",
            "Not Available"
          ],
          "_fieldLookup": {
            "n.cat_sw_release_id": 0,
            "n.release_url": 1,
            "n.ga_date": 2
          }
    title: Example 2
    language: javascript
  - code_block: |-
      MATCH (n:SOFTWARE_RELEASE) -[:RELEASE_OF]->(SOFTWARE_PRODUCT) RETURN n.cat_sw_release_id LIMIT 1

      RESPONSE SAMPLE
      {
          "keys": [
            "n.cat_sw_release_id"
          ],
          "length": 1,
          "_fields": [
            {
              "low": 55725913,
              "high": 0
            }
          ],
          "_fieldLookup": {
            "n.cat_sw_release_id": 0
          }
        }
    title: Example 3
    language: javascript
  - code_block: 'curl http://sampleapi.readme.com/orders?key=YOUR_APP_KEY'
    title: Example 4
    language: bash
  - code_block: 'curl http://sampleapi.readme.com/orders?key=YOUR_APP_KEY'
    title: Example 5
    language: bash
  - code_block: 'curl http://sampleapi.readme.com/orders?key=YOUR_APP_KEY'
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
      version_desupported_flag
      version_order
      created_at


      MAJOR VERSION GROUP
      technopedia_id
      version
      cat_sw_version_group_id

    title: Software Version Attributes
    language: bash
  - code_block: |2-
      (SOFTWARE_VERSION)<-[:RELEASE_OF]-(SOFTWARE_RELEASE)
      (SOFTWARE_VERSION)<-[:MAJOR_VERSION_OF]-(to be determined)
    title: Relationships
    language: bash
---

