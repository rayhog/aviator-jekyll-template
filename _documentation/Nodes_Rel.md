---
title: Technopedia Data
position: 1.04
type:
description: >-  
content_markdown: >-
  You access Technopedia data by referencing nodes, attributes, relationships, or Technopedia IDs in the Technopedia graph.<br>
  <br>
  
  #### GET request with the Technopedia ID
  <br>

  ######
  You can use an API GET request for product information in Technopedia by referencing the Technopedia ID.<br>
  You specify the Technopedia ID as a parameter for the Technopedia-id TQL endpoint. <br>
  <br>
  GET `https://v6-1.technopedia.com/technopedia-id/<technopedia-id>` <br>
  <br>
  
  #### 
  GET request by using the Technopedia query language (TQL)

  ######
  The main method for acessing information in Technopedia is by using the API with the Technopedia query language (TQL) to query nodes and relationships in the Technopedia database.<br>
  <br>
  GET `https://v6-1.technopedia.com/tql?q=<TQL_query>`<br>
  <br>

  #### About Nodes in Technopedia
  
  
  ###### Nodes are the entities in the Technopedia graph that store specific categories of data. <br>
  Nodes can have any number of attributes, which are represented by key-value-pairs.<br> 
   * Nodes are entities that store the Technopedia data.
   * Node names are surrounded by parentheses in a query, for example, (Node).
   * Nodes have attributes that show data in key-value pairs.
   * Nodes are connected to other nodes by relationships.

   Here's some examples of nodes in Technopedia:

   ![API Image](/images/nodes_few.png)<br>&nbsp;
  <br>
   
  To get data from multiple nodes in one query, you use defined relationships to other nodes. 
  <br>

  #### Relationships between Nodes in Technopedia 

  ######
  Relationships provide semantically relevant connections between the Technopedia nodes. <br>
  Relationships have a type, such as `BELONGS_TO` and a direction, such as node x to node y. <br>
  An arrow determines the direction of the relationship. <br>
  For example `(node x)-[BELONGS_TO]->(node y)` <br>
  To get Technopedia data from multiple nodes in one query, you use relationships to traverse nodes and define the criteria for the data that you want to extract from the database.

   * Relationships are represented by an arrow `->` between two nodes, which represents the direction of the relationship. 
     Relationships often exist in a single direction but they can be bidirectional.

   * Relationships provide semantically relevant connections between the Technopedia database nodes, for example, the software product node has the relationship: `[HAS_A]->` to the manufacturer node.

   * Relationships allow you to traverse the Technopedia Nodes and by using the Technopedia query language, and to get data from the specified nodes in one query.

   * Like nodes, relationships can also have attributes. Typically, relationship have quantitative attributes, such as time intervals.
   * To get information about a relationship that has attributes, we can assign it an alias for later reference. The alias is placed in front of the colon `-[anyAlias:Relationship_name]->(node)`


  ###### The following diagram is a simple overview of nodes and relationships:


  ![API Image](/images/nodes_simple.png)<br>&nbsp;
  <br>

  In a query, nodes are surrounded by parenthesis and relationships are surrounded by square brackets as shown in the following example:
  <br>
  `Match (:node)-[:RELATIONSHIP]-> (:node)`
  
  <br>
 
  
  The following diagram shows the nodes and relationships in the Technopedia database. <br>
  <br>
  ![API Image](/images/graph.png)<br>&nbsp;
  <br>

  
   Note: You can only access data from Technopedia nodes that your subscription allows.
    {: .warning} 

  




right_code_blocks:
  - code_block: |
      
      MANUFACTURER
      SOFTWARE_PRODUCT
      SOFTWARE_VERSION
      SOFTWARE_VERSION_GROUP
      SOFTWARE_MAJOR_VERSION
      SOFTWARE_RELEASE
      SOFTWARE_EDITION
      CPU_MODEL
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

