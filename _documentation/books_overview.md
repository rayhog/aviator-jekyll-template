---
title: Overview
position: 1.01
type: 
description: ### Version 6 API and the Technopedia Query Language
content_markdown: |-
  ###### The Techopedia version 6 API provides enhanced, cloud-based access to asset data in Technopedia. Technopedia uses the API with the graph-based query language to provide a cloud-first, high-performance resource for customers. <br>
  #### What’s in Technopedia V6 API
  - Graph store organization model that enables Technopedia to store asset data from any industry.
  - TQL (Technopedia Query Language) endpoint that is used for graph-based querying of the Technopedia database.
  - Technopedia-id endpoint that you use to look any Technopedia product by ID.
  <br>
  #### TQL graph concepts
  <br>
  ###### The following concepts are involved in the storage of data is stored in Technopedia
  - Nodes are Graph data records that are entities in the graph, such as software version or hardware. Nodes contain attributes, which are key-value pairs.
  - Attributes are properties of  a node and they store data in key-value pairs, such as '{name Joe}' <br>
  - Relationship provide a connection between nodes. Relationships have a start node, end node, a type, and a direction. For example, the nodes apple and an orchard have a relationship in the graph which is named 'grows_in'. Apple is the start node; orchard is the end node; 'grows_in' is the relationship and the direction is apple to orchard.
  
  ###### Here's a diagram of how Nodes and Relationships work:

  ![API Image](/images/NodeAndRel.png){: .img-responsive}<br>
  <br>
 
  
  
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