---
title: TQL
position: 1.05
type:
description: >-
  You use the Technopedia query language (TQL) with the TQL endpoint to query data in the Technopedia database. TQL is the graph query language that you use to query the database. The graph database stores connections between nodes as first-class citizens so it doesn't have to compute relationships at query time, which makes it more efficient than a relational database.
content_markdown: >-
  ###### TQL is a declarative query language that allows you to state what actions you want by using the query language to query Nodes and Relationships in the Technopedia database.


  ###### In the following example, you match the relationship is descriped as
  employee is employee of organization. The folllowing example shows a relationship connection format:


  `Match (node)-[:RELATIONSHIP]-> (node)`


  `Match (Joe)-[:Is_Employee_of]-> (organization)`
  If Joe is an employee of the organization then this relationship might be expressed in the following way:<br>

  The start node is employee; organization is the end node; `Is_Employee_of` is the relationship and
  the direction is employee to organization, which is determined by the arrow. The syntax of the query that defines the relationship might be expressed in the following way: <br>

  `MATCH (e:employee)-[Is_Employee_of]->(organization) WHERE e.person = "Joe" RETURN e`


  Here's a diagram of how Nodes and Relationships work:


  ![API Image](/images/NodeAndRel.png)<br>&nbsp;

  
  
  The query returns software that includes 'Excel'. This is query is case
  sensitive.

  {: .success}



  To get data from a specific node or relationship, you use an alias or variable that you append to the node or relationship. That alias is bound to that node or relationship so you can use that alias in the Return clause of the MATCH query to get specific data from that node or alias.
  `Match (myalias:node)-[another_alias:RELATIONSHIP]`

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

