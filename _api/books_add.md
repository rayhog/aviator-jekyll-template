---
title: /TQL
position: 1.1
type: get
description: >-
  Create Query for example query. In this example, we will pull data from
  Technopedia that contains 'excel'.
parameters:
  - name: title
    content: The title for the book
  - name: score
    content: The book's score between 0 and 5
content_markdown: >-
  The query returns software that includes 'Excel'. This is query is case
  sensitive.

  {: .success}


  Adds a book to your collection.
left_code_blocks:
  - code_block: >-

      https://v6.technopedia.com/tql?q=MATCH(SOFTWARE:s) WHERE s.title CONTAINS
      "excel" RETURN s


      Return software that contains excel in the title
    title: GET
    language: json
right_code_blocks:
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
              },
              {
                  "s": {
                      "attributes": {
                          "title": "Total Access 900e Series IP Business Gateway"
                      },
                      "created_at": "2017-11-17T13:29:54.555Z",
                      "created_by": "00000000-0000-0000-0000-000000000000",
                      "label": "HARDWARE",
                      "owner": "00000000-0000-0000-0000-000000000000",
                      "quality_grade": 3,
                      "technopedia_id": "f620a8b5-c928-4adb-8047-6ca2d1375d7a"
                  }
              },
    title: Sample Response
    language: json
---


