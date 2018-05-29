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

