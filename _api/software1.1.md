---
title: Software
position: 1.1
type: 
description: Get software data by creating relationships between software nodes
parameters:
  - name:
    content:
content_markdown: |-

  MATCH (a:SOFTWARE_RELEASE) RETURN a.Release_Title

  {: .success} 
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
      Software consists of the follwoing 5 nodes:

      SOFTWARE_PRODUCT
      SOFTWARE_VERSION
      SOFTWARE_MAJOR_VERSION
      SOFTWARE_EDITION
      SOFTWARE RELEASE
    title: Software Nodes
    language: bash
  - code_block: |2-
      SOFTWARE NODES RELATIONSHIPS

      (SOFTWARE_PRODUCT)<-[:EDITION_OF]-(SOFTWARE_EDITION)
      (MANUFACTURER)-[:VENDOR_OF]->(SOFTWARE_PRODUCT)
      (SOFTWARE_VERSION)<-[:RELEASE_OF]-(SOFTWARE_RELEASE)
      (SOFTWARE_VERSION)<-[:MAJOR_VERSION_OF]-(SOFTWARE_MAJOR_VERSION)
    title:Software Nodes Relationships
    language: bash
---