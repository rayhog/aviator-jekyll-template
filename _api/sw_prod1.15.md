---
title: Software Product
position: 1.15
type:
description: >-
  Create Query for example query. In this example, we will pull data from
  Technopedia that contains 'excel'.
content_markdown: >-
  The query returns software that includes 'Excel'. This is query is case
  sensitive. 
  
  {: .success} 
  
  `MATCH (n:SOFTWARE\_PRODUCT) WHERE n.title = "PDF Converter" RETURN n`
left_code_blocks:
  - code_block: |-
      $.ajax({
        "url": "http://api.myapp.com/books/3",
        "type": "DELETE",
        "data": {
          "token": "YOUR_APP_KEY"
        },
        "success": function(data) {
          alert(data);
        }
      });
    title: jQuery
    language: javascript
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

