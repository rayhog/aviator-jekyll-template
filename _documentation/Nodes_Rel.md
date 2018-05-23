---
title: Nodes and Relationships
position: 1.03
type:
description: >-
content_markdown: >-
  ###### Nodes are the entities in the Technopedia graph where each nodes stores specific data. Nodes can have any
  number of attributes, which are represented by key-value-pairs. 
  
  To get data from multiple nodes in one query, you use defined relationships in your queries to connect the nodes and their attributes. 
  Relationships provide semantically relevant connections between the Technopedia nodes. Relationships might have a
  type,such as 'friend\_of' and a direction such as Joe (node) friend\_of Bob
  (node), where an arrow in a query determines the direction of the relationship.
  To get Technopedia data, You use relationships to traverse nodes and define the criteria for the data that you want to extract from the database.


  ###### In the following example, you match the relationship is descriped as
  Joe is a friend of Bob. This relationship connection 

  `Match (Joe)-[:FRIEND_OF]-> (Bob)`

  `Match (node)-[:RELATIONSHIP]-> (node)`


  

  The following diagram represents an image that is to be removed:


  ![API Image](/images/NodeAndRel.png)<br>&nbsp;
  
  <br>
 

  {: .success}

  The query returns software that includes 'Excel'. This is query is case
  sensitive.
  
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

