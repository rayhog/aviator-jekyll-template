---
title: Software Nodes
position: 1.1
type: 
description: Get software data by using relationships between software nodes
content_markdown: |-
  The following query returns software releases by title:  
    
  `MATCH (a:SOFTWARE_RELEASE) RETURN a.release.title`

  <br>
  <br>

  Software is a general classification that can be broken into the following classifications
    * Software Product
    * Software Version
    * Software Major Version
    * Software Edition
    * Software Release
  
  
  Use a combination of the software nodes with relationships to get the data that you specify in your query.
  <br>
  ![API Image](/images/node_ex.png){:class="img-responsive"} <br> 
 
  
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
      Software consists of the following five nodes:

      * SOFTWARE_PRODUCT
      * SOFTWARE_VERSION
      * SOFTWARE_MAJOR_VERSION
      * SOFTWARE_EDITION
      * SOFTWARE RELEASE
      Query specific software data by using the individual nodes, or use relationships to connect nodes.

    title: Software Nodes
    language: bash
  - code_block: |2-
      SOFTWARE NODES RELATIONSHIPS

      (SOFTWARE_PRODUCT)<-[:EDITION_OF]-(SOFTWARE_EDITION)

      (MANUFACTURER)-[:VENDOR_OF]->(SOFTWARE_PRODUCT)

      (SOFTWARE_VERSION)<-[:RELEASE_OF]-(SOFTWARE_RELEASE)

      (SOFTWARE_VERSION)<-[:MAJOR_VERSION_OF]-(SOFTWARE_MAJOR_VERSION)
    title: Software Nodes Relationships
    language: bash
---