---
title: Software Release
position: 1.6
type:
description: Get software release data from the Technopedia database.

content_markdown: >-
  MATCH (a:SOFTWARE_RELEASE) RETURN a.Release_Title

  {: .success} 


  &nbsp;
  <br>
  Here's an example of querying the release title "Advanced Partitioning Option" that is a release of a software version.<br>
  <br>
  <br>
  `MATCH (SOFTWARE_PRODUCT)<-[:EDITION_OF]-(SOFTWARE_EDITION) WHERE n.release_title = "Advanced Partitioning Option" RETURN n`
  <br>
  <br>
  The folloiwng diagaram shows the nodes, attributes, and relationships that feature in the query example.
  ![API Image](/images/sw_rel_to_ver.png){:class="img-responsive"} <br>

  ###### You can paginate by using the parameters listed above.


  <br>The Technopedia Version 6.0 API uses OAuth for
  authentication. To authenticate a session, pass your key in the request
  header. Your API key should have been provided to you by Flexera support. If
  you do not have a key please contact support.
left_code_blocks:
  - code_block: |
      `MATCH (n:SOFTWARE_RELEASE) RETURN n.cat_sw_release_id, n.ga_date`

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
      `MATCH (n:SOFTWARE_RELEASE) RETURN n.cat_sw_release_id, n.release_url n.ga_date`


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
      `MATCH (n:SOFTWARE_RELEASE) -[:RELEASE_OF]->(SOFTWARE_PRODUCT) RETURN n.cat_sw_release_id LIMIT 1`

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
    title: Curl
    language: bash
right_code_blocks:
  - code_block: |-
      [
        {
          "id": 1,
          "title": "The Hunger Games",
          "score": 4.5,
          "dateAdded": "12/12/2013"
        },
        {
          "id": 1,
          "title": "The Hunger Games",
          "score": 4.7,
          "dateAdded": "15/12/2013"
        },
      ]
    title: Response
    language: json
  - code_block: |-
      {
        "error": true,
        "message": "Invalid offset"
      }
    title: Error
    language: json
right_code_blocks:
  - code_block: |2
      Technopedia_id
      Release_Title
      Release_Patchlevel
      GA_Date
      Release_Discontinued_Flag
      Release_Desupported_Flag
      Release_URL
      Created_At
      Modified_At
    title: Software Release Attributes
    language: bash
  - code_block: |2-
      (SOFTWARE_RELEASE)-[:RELEASE_OF]->(SOFTWARE_VERSION)
      (SOFTWARE_RELEASE)<-[:EDITION_OF]-(SOFTWARE_EDITION)
    title: Relationships
    language: bash
---
