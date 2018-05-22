---
title: Software
position: 1.1
type: 
description: Get software data by creating relationships between software nodes
parameters:
  - name:
    content:
content_markdown: |-
  ###### Software is a general classification that can be broken into the following classifications:
  - Software Product
  - Software Version
  - Software Edition
  - Software Release
  
  You can use a combination of the software nodes with relationships to get the data that you specify in your query.
  <br>
  ![API Image](/images/gears.PNG){:class="img-responsive"} <br>
  
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