---
title: Overview
position: 1.01
type:
description:
content_markdown: >-
 


  ###### The storage of data in Technopedia involves the following concepts:


  * Nodes are Graph data records that are entities in the graph, such as
  software version or hardware.                 
    
  * Nodes contain attributes, which are key-value
  pairs. Attributes are properties of a node and they store data in key-value pairs,
  such as `{title: Excel}` or `{manufacturer: Microsoft}`.

  * Relationships provide node to node connections. Relationships have a start
  node, end node, a type, and a direction. For example, the nodes organization and employee
  might have a relationship in the graph. An example of an relationship might be `Is_Employee_of`, which could be a relationship between employee and organization.

  If Joe is an employee of the organization then this relationship might be expressed in the following way:<br>

  The start node is employee; organization is the end node; `Is_Employee_of` is the relationship and
  the direction is employee to organization, which is determined by the arrow. The syntax of the query that defines the relationship might be expressed in the following way: <br>

  `MATCH (e:employee)-[Is_Employee_of]->(organization) WHERE e.person = "Joe" RETURN e`


  ###### The following diagram shows how Nodes and Relationships are
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
      Endpoints   
      
      https://v6.technopedia.com/tql?
      
      https://v6.technopedia.com/technopedia-id/

    title: Technopedia Endpoints
    language: html
  ---