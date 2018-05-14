---
title: Software Release
position: 1.6
type:
description: Get software release data from Technopedia
parameters:
  - name: Categories
    content: Category of class
  - name: Relationships
    content: Relationships to other Nodes
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
  - code_block: |+
      MATCH (n:SOFTWARE_RELEASE) 
      RETURN
      n.cat_sw_release_id, n.ga_date

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
  - code_block: "MATCH (n:SOFTWARE_RELEASE) \r\nRETURN \r\nn.cat_sw_release_id, \r\nn.release_url, \r\nn.ga_date LIMIT 1\r\n\r\nRESPONSE SAMPLE\r\n{\r\n    \"keys\": [\r\n      \"n.cat_sw_release_id\",\r\n      \"n.release_url\",\r\n      \"n.ga_date\"\r\n    ],\r\n    \"length\": 3,\r\n    \"_fields\": [\r\n      {\r\n        \"low\": 10427852,\r\n        \"high\": 0\r\n      },\r\n      \"www.nntest.com/files/import/Solutions%20Catalog%20Data.xls\",\r\n      \"Not Available\"\r\n    ],\r\n    \"_fieldLookup\": {\r\n      \"n.cat_sw_release_id\": 0,\r\n      \"n.release_url\": 1,\r\n      \"n.ga_date\": 2\r\n    }"
    title: Example 2
    language: javascript
  - code_block: |-
      MATCH (n:SOFTWARE_RELEASE)
      -[:RELEASE_OF]->
      (SOFTWARE_PRODUCT) 
      RETURN 
      n.cat_sw_release_id 
      LIMIT 5

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
---

