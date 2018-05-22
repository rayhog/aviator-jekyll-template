---
title: Software Release
position: 1.6
type:
description: Get software release data from Technopedia

content_markdown: >-
  MATCH (SOFTWARE\_VERSION:a) RETURN a

  {: .info}


  &nbsp;


  ###### You can paginate by using the parameters listed above.


  Lists all the photos you have access to. You can paginate by using the
  parameters listed above.<br>![API Image](/images/apiEcon.PNG){:
  .img-responsive}<br>The Technopedia Version 6.0 API uses OAuth for
  authentication. To authenticate a session, pass your key in the request
  header. Your API key should have been provided to you by Flexera support. If
  you do not have a key please contact support.
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
      MATCH (n:SOFTWARE_RELEASE) RETURN n.cat_sw_release_id, n.release_url,
      n.ga_date LIMIT 1


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
      MATCH (n:SOFTWARE_RELEASE) -[:RELEASE_OF]->(SOFTWARE_PRODUCT) RETURN n.cat_sw_release_id LIMIT 5

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
      Edition
      Edition_Desupported_Flag
      Edition_Order
      URL
      Created_At
      Modified_At
    title: Software Product Attributes
    language: bash
  - code_block: |2-
      [:VENDOR_OF]->(Manufacturer)
    title: Relationships
    language: bash
---

