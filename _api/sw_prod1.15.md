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
      Title
      Family
      Component
      Alias
      Nfamily
      Product_Desupported_Flag
      Product_Discontinued_Flag
      Created_at
      Modified_At
    title: Software Product Attributes
    language: bash
  - code_block: |2-
      (SOFTWARE_PRODUCT)<-[:EDITION_OF]-(SOFTWARE_EDITION)
      (SOFTWARE_PRODUCT)<-[:VENDOR_OF]-(MANUFACTURER)
      

    title: Relationships
    language: bash
---

