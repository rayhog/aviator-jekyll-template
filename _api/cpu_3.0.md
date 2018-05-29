---
title: CPU
position: 3.2
type: 
description: 
content_markdown: |-
  ###### The CPU node in the Technopedia database stores information that relates to the CPU, such as the model ID, number or cores, and model information. 

  The CPU node is connected to the MANUFACTURER node by the `VENDOR_OF` relationship, which points toward the CPU node.
  Here's a simple query to return 25 results for CPU models:

  `MATCH (n:CPU_MODEL) RETURN n LIMIT 25`
  {: .info}
  
  <br>
    
  
  ![API Image](/images/graph.png){:class="img-responsive"} <br>
  
 


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
  - code_block: 
      curl -G -H "Authorization: Bearer b93477a9-057b-4878-a16b93477a9-057b-4878-a16f-d7f7d1f27a7af-d7f7d1f27a7a" "https://v6.technopedia.com/tql" --data-urlencode' "q=MATCH (h:CPU) RETURN h.cores"
    title: cURL
    language: bash
    

right_code_blocks:
  - code_block: |2
      cat_cpu_model_id
      technopedia_id
      model
      url
      cores
      clockrate
      isa_bitmode
      num_threads
      created_at
      modified_at

    title: CPU Attributes
    language: bash
  - code_block: |2-
      (MANUFACTURER)-[:VENDOR_OF]->(CPU)
    title: Relationships
    language: bash
---