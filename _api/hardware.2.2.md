---
title: Hardware
position: 2.2
type: 
description: Write a MATCH statement to query the Hardware Node.
content_markdown: |-
  Returns a specific book from your collection.<br> 
  ![API Image](/images/apiEcon.PNG){:class="img-responsive"} <br>
  This is a very precise query.
  
  Update an existing object in your collection.  
  ###### Returns a specific object from your collection.<br> 
  ![API Image](/images/tid.png){:class="img-responsive"} <br>

left_code_blocks:
  - code_block: |-
      $.ajax({
        "url": "http://api.myapp.com/books/3",
        "type": "PUT",
        "data": {
          "token": "YOUR_APP_KEY",
          "score": 5.0,
          "title": "The Book Stealer"
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