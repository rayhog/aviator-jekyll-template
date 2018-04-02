---
title: /TQL
position: 1.1
type: get
description: Create Query for example query
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
                          "approved_by": null,
                          "avg_price": null,
                          "cat_currency_id": null,
                          "cat_sw_edition_desupported_flag": false,
                          "cat_sw_edition_id": null,
                          "cat_sw_edition_url": null,
                          "cat_sw_major_release_id": 18143816,
                          "cat_sw_major_version_id": 18143559,
                          "cat_sw_pricing_id": null,
                          "cat_sw_product_link_id": null,
                          "cat_sw_rel_lifecycle_id": 317053450,
                          "cat_sw_rel_platform_desupported_flag": false,
                          "cat_sw_rel_platform_discontinued_flag": false,
                          "cat_sw_rel_platform_id": null,
                          "cat_sw_rel_supp_stage_id": null,
    title: Sample Response
    language: json
---


