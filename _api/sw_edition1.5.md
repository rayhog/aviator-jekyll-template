---
title: Software Edition
position: 1.5
type: 
description: Matches the software edition from the Technopedia database.
content_markdown: |-
  Software edition represents the version of the product, such as Standard, Premium, or other version name for the product.
  <br>


  `MATCH (e:SOFTWARE_EDITION {cat_sw_edition_id: '24853332'})-[*1..3]->(b) RETURN b LIMIT 10`
  {: .success}

  <br>
  Here's an example of querying the release title "Advanced Partitioning Option" that is a release of a software version.<br>
  <br>
  `MATCH (SOFTWARE_PRODUCT)<-[:EDITION_OF]-(SOFTWARE_EDITION) WHERE n.release_title = "Advanced Partitioning Option" RETURN n`
  <br>

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
      cat_sw_edition_id
      edition
      edition_desupported_flag
      edition_order
      url
      technopedia_id
      created_at
      modified_at
      deleted_at
      load_id
    title: Software Edition Attributes
    language: bash
  - code_block: |2-
      (SOFTWARE_EDITION)<-[:EDITION_OF]-(SOFTWARE_EDITION)
      (SOFTWARE_EDITION)-[:EDITION_OF]->(SOFTWARE_PRODUCT) 
    title: Relationships
    language: bash
---

