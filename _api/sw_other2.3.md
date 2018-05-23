---
title: Other CAT
position: 2.3
type: 
description: >-
  Create Query for example query. In this example, we will pull data from
  Technopedia that contains 'excel'.

content_markdown: >-
 ###### The query returns software that includes 'Excel'. This is query is case
  sensitive.
  {: .success}

  Adds an object to your collection.



  ###### Temp Info
  Cypher queries that use
  Key words MATCH, WHERE, AND, OR, COUNT, DISTINCT, CONTAINS
  Operators =, <>, >, <, >=, <=
  Case insensitivity

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
      Technopedia_id
      Edition
      Edition_Desupported_Flag
      Edition_Order
      URL
      Created_At
      Modified_At
    title: Software Edition Attributes
    language: bash
  - code_block: |2-
      Edition_of Software Release
      Edition of Software Product 
    title: Relationships
    language: bash
---


