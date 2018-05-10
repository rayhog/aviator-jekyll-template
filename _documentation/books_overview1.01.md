---
title: Overview
position: 1.01
type:
description:
content_markdown: >-
  ###### The Techopedia version 6 API provides enhanced, cloud-based access to
  asset data in Technopedia. Technopedia uses the API with the graph-based query
  language to provide a cloud-first, high-performance resource for customers.


  #### What’s in Technopedia V6 API


  * Graph store organization model that enables Technopedia to store asset data
  from any industry.

  * TQL (Technopedia Query Language) endpoint that is used for graph-based
  querying of the Technopedia database.

  * Technopedia-id endpoint that you use to look any Technopedia product by ID.


  ### V6 API Endpoints


  ###### To query the Technopedia database you use the following endpoints:


  * `https://v6.technopedia.com/tql?q=MATCH [Query Parameters]`

    ###### You provide query parameters to the MATCH statement to generate the criteria for your query, as in the following example:

    ![API Image](/images/get_tql.png){: .img-responsive}

  * `https://v6.technopedia.com/technopedia-id/[Technopedia ID]`

    ###### You provide the Technopedia ID for the product that you're querying to return data for that specific product, as in the following example:

    ![API Image](/images/tid.png){: .img-responsive}

  #### TQL graph concepts


  ###### The following concepts are involved in the storage of data is stored in
  Technopedia


  * Nodes are Graph data records that are entities in the graph, such as
  software version or hardware. Nodes contain attributes, which are key-value
  pairs.

  * Attributes are properties of a node and they store data in key-value pairs,
  such as '{name Joe}'

  * Relationships provide a connection between nodes. Relationships have a start
  node, end node, a type, and a direction. For example, the nodes apple and an
  orchard have a relationship in the graph which is named 'grows\_in'. Apple is
  the start node; orchard is the end node; 'grows\_in' is the relationship and
  the direction is apple to orchard.


  ###### The following diagram is an example of how Nodes and Relationships are
  connected:


  ![API Image](/images/NodeAndRel.png){: .img-responsive}<br>&nbsp;
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
  - code_block: |-
      QUERY RESPONSE

      {
        "id": 3,
        "title": "The Book Thief",
        "score": 4.3,
        "dateAdded": "5/1/2015"
      }
    title: Response
    language: html
  - code_block: |-
      QUERY RESPONSE 2

      {
        "error": true,
        "message": "Book doesn't exist"
      }
    title: Error
    language: html
---