---
title: Software Product
position: 1.15
type:
description: >-
  In the following query example, you get data from Technopedia that contains PDF Converter in the title of the software product title.
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
      cat_sw_product_id
      title
      family
      component
      is_suite
      plicsable
      nfamily
      vendor_category
      product_desupported_flag
      product_discontinued_flag
      product_url
      technopedia_id
      created_at
      modified_at
      deleted_at
      load_id

      MATCH QUERY EXAMPLES:
      
      MATCH (n:SOFTWARE_PRODUCT) RETURN n.title

      MATCH (n:SOFTWARE_PRODUCT) RETURN n.cat_sw_product_id

      MATCH (n:SOFTWARE_PRODUCT) RETURN n.vendor_category


    title: Software Product Attributes
    language: bash
  - code_block: |2-
      (SOFTWARE_PRODUCT)<-[:EDITION_OF]-(SOFTWARE_EDITION)
      (SOFTWARE_PRODUCT)<-[:VENDOR_OF]-(MANUFACTURER)
      

    title: Relationships
    language: bash
---

