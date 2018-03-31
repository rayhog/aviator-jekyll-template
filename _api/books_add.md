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
  - code_block: |-
      $.post("http://api.myapp.com/books/", {
        "token": "YOUR_APP_KEY",
        "title": "The Book Thief",
        "score": 4.3
      }, function(data) {
        alert(data);
      });
    title: jQuery
    language: javascript
right_code_blocks:
  - code_block:
    title:
    language: json
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
    title: Response Example
    language: json
---


