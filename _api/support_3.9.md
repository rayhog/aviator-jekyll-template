---
title: Support
position: 3.9
type: 
description: >-
 You can access Support data from the SUPPORT_STAGE and SUPPORT_POLICY nodes, which are connected to Software and Hardware.

content_markdown: >-
 ###### The CAT is  about CATS
  <br>

  `MATCH (a:SUPPORT_STAGE)-[:HAS_A]-(SUPPORT_POLICY) RETURN a
  {: .info}
  {: .success}

  The following diagram shows the support nodes and relationships.
  <br>
  ![API Image](/images/support.png){:class="img-responsive"} <br> 

  <br>

  
 
  

left_code_blocks:
  - code_block: |-
      {
          "results": [
              {
                  "s": {
                      "attributes": {
                          "title": "Total Access 900 Series IP Business Gateway"
                      },
                      "created_at": "2017-11-17T13:29:54.555Z",
                      "created_by": "00000000-0000-0000-0000-000000000000",
                      "label": "HARDWARE",
                      "owner": "00000000-0000-0000-0000-000000000000",
                      "quality_grade": 3,
                      "technopedia_id": "7f4f7044-e0de-4da9-87b1-817266df9684"
                  }
              },
              {
                  "s": {
                      "attributes": {
                          "title": "Total Access 900 Series IP Business Gateway"
                      },
                      "created_at": "2017-11-17T13:29:54.555Z",
                      "created_by": "00000000-0000-0000-0000-000000000000",
                      "label": "HARDWARE",
                      "owner": "00000000-0000-0000-0000-000000000000",
                      "quality_grade": 3,
                      "technopedia_id": "f35c4a08-785e-4b3b-93c6-3588b298e976"
                  }
             
    title: GET
    language: json
  - code_block: >
      MATCH (<Node_Type>:<alias> {<attribute>: '<attribute_value>'}) RETURN
      <alias>

      MATCH (SOFTWARE:s {category: 'Web Browsers'}) RETURN s.title


      SAMPLE RESPONSE

      {
          "version": "1.0.0",
          "request-id": "a3505e21-8d91-40ff-b587-3f6731a1086b",
          "results": [
              {
                  "s": {
                      "attributes": {
                          "end_of_life_str": "1/9/2007",
                          "title": "Excel for Mac",
                          "version": "10.0"
                      },
                      "created_at": "2017-11-17T12:15:47.158Z",
                      "created_by": "00000000-0000-0000-0000-000000000000",
                      "label": "SOFTWARE",
                      "owner": "00000000-0000-0000-0000-000000000000",
                      "quality_grade": 3,
                      "technopedia_id": "2b0e74ee-b8c0-4a6d-a096-a892fbaed1fc"
                  }
              },
    title: QUERY EXAMPLE
    language: bash
  - code_block:
    title:
    language:
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


