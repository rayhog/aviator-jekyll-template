---
title: Software Product
position: 1.15
type:
description: >-
  In the following qeury example, we get data from Technopedia that contains PDF Converter in the title of the software product title.
content_markdown: >-
  `MATCH (n:SOFTWARE_PRODUCT) WHERE n.title = "PDF Converter" RETURN n` 
  
  {: .success} 
  
  
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

