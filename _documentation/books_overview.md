---
title: Overview
position: 1.01
type: 
description: ### Version 6 API and the Technopedia Query Language
content_markdown: |-

  ####### The Techopedia version 6 API provides enhanced, cloud-based access to asset data in Technopedia. Technopedia uses the API with the graph-based query language to provide a cloud-first, high-performance resource for customers. <br>
  #### What’s new in Technopedia V6 API
  - Graph store organization model, which enables Technopedia to include assets from any industry.
  - TQL (Technopedia Query Language) endpoint that is used for graph-based querying of the Technopedia database.
  - Technopedia-id endpoint that you use to look any Technopedia product by ID.
  #### TQL graph concepts
  The following concepts are involved in the storage of data is stored in Technopedia
  - Nodes are Graph data records, such as software version or hardware.
  - A relationship is a connection between nodes, such as the grows_in relationship; in this example, the node     apple grows_in node orchard.
    Attributes are properties of  a node and they store data in key-value pairs, such as '{name Joe}'
 
  ![API Image](/images/logo.png){:class="img-responsive"} <br>
  
left_code_blocks:
  - code_block: |-
      $.get("http://api.myapp.com/books/3", {
        token: "YOUR_APP_KEY",
      }, function(data) {
        alert(data);
      });
    title: jQuery
    language: javascript
right_code_blocks:
  - code_block: |2-
      {
        "id": 3,
        "title": "The Book Thief",
        "score": 4.3,
        "dateAdded": "5/1/2015"
      }
    title: Response
    language: json
  - code_block: |2-
      {
        "error": true,
        "message": "Book doesn't exist"
      }
    title: Error
    language: json
---