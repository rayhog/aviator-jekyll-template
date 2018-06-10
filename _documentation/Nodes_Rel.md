---
title: Data
position: 1.04
type:
description: >-  
content_markdown: >-
  ###### You access data in Technopedia by referencing nodes, relationships, or Technopedia IDs in the Technopedia graph.

  #### GET request with the Technopedia ID

  ######
  You can use an API GET request for product information in Technopedia by referencing the Technopedia ID.
  You specify the Technopedia ID as a parameter for the Technopedia-id TQL endpoint. <br>
  For example:
  GET  `https://v6.technopedia.com/technopedia-id/4d35ec28-0f16-4787-acca-885679265b59`

  #### GET request by using the Technopedia query language (TQL)

  ######
  The main method for acessing information in Technopedia is by using the API with the Technopedia query language (TQL) to query nodes and relationships in the Technopedia grpahcan use an API GET request for product information in Technopedia by referencing the Technopedia ID.
  You specify the Technopedia ID as a parameter for the Technopedia-id TQL endpoint. <br>
  For example:
  GET  `https://v6.technopedia.com/technopedia-id/4d35ec28-0f16-4787-acca-885679265b59`
  
  #### About Nodes in Technopedia
  
  
  ###### Nodes are the entities in the Technopedia graph that store specific categories of data. Nodes can have any
  number of attributes, which are represented by key-value-pairs.<br> 
   * Nodes are entities that store the Technopedia data.
   * Node names are surrounded by parentheses in a query, for example, (Node).
   * Nodes have attributes that show data in key-value pairs.
   * Nodes are connected to other nodes by relationships.
   
  To get data from multiple nodes in one query, you use defined relationships to other nodes in your queries to connect the nodes and their attributes. 

  #### Relationships between Nodes in Technopedia 

  ######
  Relationships provide semantically relevant connections between the Technopedia nodes. Relationships might have a
  type, such as `BELONGS_TO` and a direction from node x to node y. An arrow determines the direction of the relationship. For example `(node x)-[BELONGS_TO]->(node y)`
  To get Technopedia data by connecting Nodes, You use relationships to traverse nodes and define the criteria for the data that you want to extract from the database.

   * Relationships are represented by an arrow `->` between two nodes, which represent the direction of the relationship.   Relationships often exist in a single direction, but they can be bidirectional.

   * Relationships provide semantically relevant connections between the Technopedia database nodes, for example, the software product node has the relationship: `[HAS_A]->` to the manufacturer node.

   * Relationships allow you to traverse the Technopedia Nodes and by using the Technopedia query language, and to get data from the specified nodes.

   * Like nodes, relationships can also have attributes. Typically, relationship have quantitative attributes, such as time intervals.
   * To get information about a relationship that has attributes, we can assign it an alias for later reference. The alias is placed in front of the colon `-[anyAlias:Relationship_name]->(node)`


  ###### The following diagram is a basic representation of nodes and relationships:


  ![API Image](/images/node_ex.png)<br>&nbsp;
  <br>

  In a query, nodes are surrounded by parenthesis and relationships are surrounded by square brackets as shown in the following example:
  <br>
  `Match (node)-[:RELATIONSHIP]-> (node)`
  
  <br>
 

  

  To get data from a specific node or relationship, you use an alias or variable that you append to the node or relationship. TQL binds the alias that you specify to that node or relationship so you can use that alias in the Return clause of the MATCH query to get your specific data.
  <br>
  `Match (myalias:node1)-[another_alias:RELATIONSHIP]->(other_alias:node2)`
  <br>
  `MATCH (aliasX:MANUFACTURER)-[aliasV:VENDOR_OF]->(aliasY:SOFTWARE_PRODUCT) RETURN aliasX, aliasY`
  

  
  
  The following diagram shows the nodes and relationships in the Technopedia database. <br>
  <br>
  ![API Image](/images/graph.png)<br>&nbsp;
  <br>

  
   Note: You can only access data from Technopedia nodes that your subscription allows.
    {: .warning} 

  #### Query Examples <br>
    
  To use the MATCH statements in the following examples, you append the MATCH statement to the following tql endpoint and make a GET request from a API client or use cURL. <br>
  <br>
  `https://v6-1.technopedia.com/tql?q=<MATCH Statement>`




right_code_blocks:
  - code_block: |
      
      MANUFACTURER

      SOFTWARE_PRODUCT
      SOFTWARE_VERSION
      SOFTWARE_VERSION_GROUP
      SOFTWARE_MAJOR_VERSION
      SOFTWARE_RELEASE
      SOFTWARE_EDITION
      CPU
      HARDWARE PRODUCT
      HARDWARE MODEL

      CATEGORY_2
      CATEGORY_1
      CATEGORY_GROUP
      VERTICAL
      SUPPORT_STAGE
      SUPPORT_POLICY
      CERTIFICATION
      COMPATIBLE PLATFORM



           
    title: Nodes in Technopedia
    language: bash
---

