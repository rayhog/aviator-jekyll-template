---
title: Support
position: 3.9
type: 
description: >-
  

content_markdown: >-
  You can access support data from the `SUPPORT_STAGE` and `SUPPORT_POLICY` nodes, which are connected to software and hardware.<br>
  <br>
  Typically, software and hardware are supported by the vendor or manufacturer. In Technopedia, this support is identified in the `SUPPORT_STAGE` node, which refers to the type of support. The definition attribute provides more detailed information about applicability and timelines.
 
  Many support stages have a `SUPPORT_POLICY` that defines the type of policy, such as standard or Open Source. 
  <br>

  The following query returns one results for support stages with associated support policies.<br>
  `MATCH (a:SUPPORT_STAGE)-[:HAS_A]-(sp:SUPPORT_POLICY) RETURN a, sp LIMIT 1`
  The following result sample shows one result from this query:<br>
  <br>
  ![API Image](/images/sup_stage.png){:class="img-responsive"} <br> 
  <br>
   
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
      MATCH (n:SUPPORT_STAGE) 
      RETURN n 
      LIMIT 1
        
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
      MATCH (n:SUPPORT_POLICY) 
      RETURN n 
      LIMIT 2
      
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
      MATCH (n:SOFTWARE_RELEASE)<-[:HAS_A]-(w:SUPPORT_STAGE) 
      RETURN n, w 
      LIMIT 2

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
      MATCH (n:SOFTWARE_RELEASE)-[:HAS_A]->(w:SUPPORT_STAGE)-[:HAS_A]->(sp:SUPPORT_POLICY) 
      RETURN n, w, sp 
      LIMIT 2

      RESPONSE SAMPLE

      {
        "results": [
            {
                
                "n.created_at": "2012-02-23 16:23:35",
                "n.desupported_flag": null,
                "n.discontinued_flag": null,
                "n.modified_at": "2012-02-23 16:23:35",
                "n.release": "AxBase",
                "n.technopedia_id": "6af1422f-d82d-4a18-a63e-fa9d90b6c57a",
                "n.url": null,
                "sp.created_at": "2009-12-31 11:05:23",
                "sp.modified_at": "2009-12-31 11:05:23",
                "sp.support_policy": null,
                "sp.technopedia_id": "47f7f6c1-e6ae-4334-886b-f983f073af91",
                "w.created_at": "2009-12-31 11:06:56",
                "w.definition": "Download is provided. Cannot find any end date.\r\n\r\nSee http://axbase.sourceforge.net/",
                "w.modified_at": "2011-06-07 11:44:59",
                "w.order": 1,
                "w.support_stage": null,
                "w.technopedia_id": "c3510b06-2eed-4df4-a815-699424a7cefe"
            },
            {
                "n.created_at": "2010-01-11 16:31:42",
                "n.desupported_flag": null,
                "n.discontinued_flag": null,
                "n.modified_at": "2014-11-12 14:30:55",
                "n.release": "AxBase",
                "n.technopedia_id": "e439d6b8-fe4a-4ce5-b012-dd681d4fc7bf",
                "n.url": null,
                "sp.created_at": "2009-12-31 11:05:23",
                "sp.modified_at": "2009-12-31 11:05:23",
                "sp.support_policy": null,
                "sp.technopedia_id": "47f7f6c1-e6ae-4334-886b-f983f073af91",
                "w.created_at": "2009-12-31 11:06:56",
                "w.definition": "Download is provided. Cannot find any end date.\r\n\r\nSee http://axbase.sourceforge.net/",
                "w.modified_at": "2011-06-07 11:44:59",
                "w.order": 1,
                "w.support_stage": null,
                "w.technopedia_id": "c3510b06-2eed-4df4-a815-699424a7cefe"
            }
        ]
      {  

    title: Example four
    language: javascript

  - code_block: |-
      MATCH (n:SUPPORT_STAGE) 
      RETURN n 
      LIMIT 3

      RESPONSE SAMPLE

      {
        "results": [
            {
               
                "n.created_at": "2007-03-11 23:45:17",
                "n.definition": null,
                "n.modified_at": "2009-02-28 07:43:36",
                "n.order": 3,
                "n.support_stage": null,
                "n.technopedia_id": "6a48269d-3f7b-41c5-964f-54a6b28e9882"
            },
            {
                "n.created_at": "2010-08-12 15:07:29",
                "n.definition": "Customers can contact to get support via phone, fax and email. 
                 Cannot find any end date.\r\n\r\nSee http://icapp.ch/2.Ebene/3menue/ekontak.html",
                "n.modified_at": "2011-06-07 14:59:21",
                "n.order": 1,
                "n.support_stage": null,
                "n.technopedia_id": "b74083ec-a632-42e8-a9b8-dd17d5f5d5b5"
            },
            {
                "n.created_at": "2010-11-18 11:36:56",
                "n.definition": "FAQs and download are provided. Cannot find any support date.\r\n\r\n
                 See http://www.dicksondata.com/info/support.php",
                "n.modified_at": "2011-06-07 13:49:42",
                "n.order": 1,
                "n.support_stage": null,
                "n.technopedia_id": "1fe51238-3c45-42bd-845d-67cd44eb0e35"
            }
        ]
      {   

    title: Example five
    language: javascript
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


