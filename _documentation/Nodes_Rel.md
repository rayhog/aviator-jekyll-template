---
title: Nodes 
position: 1.03
type:
description: >-
content_markdown: >-
  
  #### About Nodes in Technopedia
  
  ######
  Nodes are the entities in the Technopedia graph where each nodes stores specific data. Nodes can have any
  number of attributes, which are represented by key-value-pairs.<br> 
   * Nodes are entities that store the Technopedia data.
   * Node names are surrounded by parentheses in a query, for example, (Node).
   * Nodes have different attributes that show data in key-value pairs.
   
  To get data from multiple nodes in one query, you use defined relationships to other nodes in your queries to connect the nodes and their attributes. 

  #### Relationships between Nodes in Technopedia 

  ######
  Relationships provide semantically relevant connections between the Technopedia nodes. Relationships might have a
  type,such as `friend\_of` and a direction such as Joe (node) `friend_of` Bob
  (node), where an arrow in a query determines the direction of the relationship.
  To get Technopedia data by connecting Nodes, You use relationships to traverse nodes and define the criteria for the data that you want to extract from the database.

   * Relationships are represented by an arrow `->` between two nodes, which represent the direction of the relationship.   Relationships often exist only in a single direction, but they can be bidirectional.

   * Relationships provide semantically relevant connections between the Technopedia database nodes, for example, the manufacturer node has the relationship: `[vendor_of]->` software product node.

   * Relationships allow you to traverse the Technopedia Nodes and by using the Technopedia query language, and to get data from the specified nodes.

   * Like nodes, relationships can also have attributes. Typically, relationships have quantitative attributes, such as time intervals.


  ###### The following diagram represents a simple representation of nodes and relationships:


  ![API Image](/images/node_ex.png)<br>&nbsp;
  
  In a query, nodes are surrounded by parenthesis and relationships are surrounded by square brackets as shown in the following example:
  
  `Match (node)-[:RELATIONSHIP]-> (node)`
  
  <br>
 

  {: .success}

  To get data from a specific node or relationship, you use an alias or variable that you append to the node or relationship. That alias is bound to that node or relationship so you can use that alias in the Return clause of the MATCH query to get specific data from that node or alias.
  `Match (myalias:node)-[another_alias:RELATIONSHIP]`
  

  The query returns software that includes 'Excel'. This is query is case
  sensitive.
  
  The following diagagram shows the data nodes and relationships in the Technopedia database:
  ![API Image](/images/graph.png)<br>&nbsp;


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
  - code_block: |-
      {
        "id": 3,
        "status": "deleted"
      }
    title: Response
    language: json
  - code_block: |-
      {
        "error": true,
        "message": "Book doesn't exist"
      }
    title: Error
    language: json
---

