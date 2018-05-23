---
title: Software Edition
position: 1.5
type: 
description: Matches the software edition from the Technopedia database.
content_markdown: |-
  Software edition represents the version of the product, such as Standard, Premium, or other version name for the product.
  <br>

  `MATCH (e:SOFTWARE_EDITION {cat_sw_edition_id: '24853332'})-[*1..3]->(b) RETURN b LIMIT 10`
     

  The folloiwng diagaram shows the nodes, attributes, and relationships that feature in the query example.
  ![API Image](/images/sw_edition.png){:class="img-responsive"} <br>

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
    title: Software Edition Attributes
    language: bash
  - code_block: |2-
      (SOFTWARE_EDITION)<-[:EDITION_OF]-(SOFTWARE_EDITION)
      (SOFTWARE_EDITION)-[:EDITION_OF]->(SOFTWARE_PRODUCT) 
    title: Relationships
    language: bash
---

