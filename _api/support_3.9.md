---
title: Support
position: 3.9
type: 
description: >-
  You can access support data from the SUPPORT_STAGE and SUPPORT_POLICY nodes, which are connected to Software and Hardware.

content_markdown: >-
  Typically, software and hardware are supported by the vendor or manufacturer. In Technopedia, this support is identified in the `SUPPORT_STAGE` node, which refers to the type of support. The definition attribute provides more detailed information about applicability and timelines.
 
  Many support stages have a `SUPPORT_POLICY` that defines the type of policy, such as standard or Open Source. 
  <br>


  `MATCH (a:SUPPORT_STAGE)-[:HAS_A]-(SUPPORT_POLICY) RETURN a`
  {: .info}
   

  The following diagram shows the support nodes and relationships.
  <br>
  ![API Image](/images/support.png){:class="img-responsive"} <br> 
  <br>
    
 
  #### Query Examples <br>
    
  To use the MATCH statements in the following examples, you append the MATCH statement to the following tql endpoint and make a GET request from a API client or use cURL. <br>
  <br>
  `https://v6-1.technopedia.com/tql?q=<MATCH Statement>`

left_code_blocks:
  - code_block: |-
      MATCH (n:SUPPORT_STAGE) RETURN n LIMIT 1
        
      RESPONSE SAMPLE

      {
        "results": [
            {
                "technopedia_id": "6a48269d-3f7b-41c5-964f-54a6b28e9882",
                "created_at": "2007-03-11 23:45:17",
                "modified_at": "2009-02-28 07:43:36",
                "stage": "Technical Guidance (VI)",
                "order": 3
            }
        ]
      {      
          
    title: Example 1
    language: javascript
  - code_block: |-
      MATCH (n:SUPPORT_POLICY) RETURN n LIMIT 2
      
      RESPONSE SAMPLE

      {
        "results": [
            {
                "policy": "Standard",
                "n.created_at": "2010-01-22 15:52:48",
                "n.modified_at": "2010-01-22 15:52:48",
                "n.technopedia_id": "4ea21ae6-ba0c-4888-b18b-7e05c8a7ce52"
            },
            {
                "policy": "Open Source Policy",
                "n.created_at": "2010-05-26 09:58:44",
                "n.modified_at": "2010-05-26 09:58:44",
                "n.technopedia_id": "4ff06db9-7456-4f91-a7b9-ca189301079c"
            }
        ]
      {  

    title: Example two
    language: javascript

  - code_block: |-
      MATCH (n:SOFTWARE_RELEASE)<-[:HAS_A]-(w:SUPPORT_STAGE) RETURN n, w LIMIT 2

      RESPONSE SAMPLE

      {
        "results": [
            {
                "n.created_at": "2008-09-18 22:19:41",
                "n.desupported_flag": true,
                "n.discontinued_flag": null,
                "n.modified_at": "2018-05-03 18:27:17",
                "n.technopedia_id": "503c2828-0f48-4b79-aaae-6795fb959230",
                "n.url": null,
                "w.created_at": "2007-03-11 23:45:17",
                "w.definition": null,
                "w.modified_at": "2009-02-28 07:43:36",
                "w.order": 3,
                "w.support_stage": null,
                "w.technopedia_id": "6a48269d-3f7b-41c5-964f-54a6b28e9882"
            },
            {
                "n.created_at": "2008-09-18 22:41:31",
                "n.desupported_flag": null,
                "n.discontinued_flag": null,
                "n.modified_at": "2013-02-22 17:20:30",
                "n.technopedia_id": "8627dc42-74b4-4f9e-9f36-33691250d484",
                "n.url": null,
                "w.created_at": "2007-03-11 23:45:17",
                "w.definition": null,
                "w.modified_at": "2009-02-28 07:43:36",
                "w.order": 3,
                "w.support_stage": null,
                "w.technopedia_id": "6a48269d-3f7b-41c5-964f-54a6b28e9882"
            }
        ]
      {  

    title: Example three
    language: javascript

  - code_block: |-
      MATCH (n:SOFTWARE_RELEASE)-[:HAS_A]->(w:SUPPORT_STAGE)-[:HAS_A]->(sp:SUPPORT_POLICY) RETURN n, w, sp LIMIT 2

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
      curl -G -H "Authorization: Bearer b93477a9-057b-4878-a16b93477a9-057b-4878-a16f-d7f7d1f27a7af-d7f7d1f27a7a" "https://v6.technopedia.com/tql" --data-urlencode' "q=MATCH (h:MANUFACTURER) RETURN h.manufacturer"

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
    language: bash
  - code_block: |-
      curl -G -H "Authorization: Bearer b93477a9-057b-4878-a16b93477a9-057b-4878-a16f-d7f7d1f27a7af-d7f7d1f27a7a" "https://v6.technopedia.com/tql" --data-urlencode' "q=MATCH (h:SUPPORT_STAGE) RETURN h.stage"










    title: cURL 
    language: bash

right_code_blocks:
  - code_block: |2
      SUPPORT_STAGE
      technopedia_id
      support_stage
      order
      created_at
      modified_at
      
      SUPPORT_POLICY
      technopedia_id
      support_policy
      created_at
      modified_at

    title: Support Attributes
    language: bash
  - code_block: |2-
      (SUPPORT_STAGE)-[HAS_A]->[SUPPORT_POLICY]
      
    title: Relationships
    language: bash
---


