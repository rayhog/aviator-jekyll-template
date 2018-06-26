---
title: Technopedia Data
position: 1.04
type:
description: >-  
content_markdown: >-
  The Technopedia database is a graph database that is based on nodes, and relationships that connect those nodes.
  Graph databases use graph structures for semantic qeuries with nodes, relationships, and attributes to represent the data.
  You access Technopedia data by querying nodes, attributes, relationships, or Technopedia IDs in the Technopedia graph.<br>
  <br>
  The graph database stores connections between nodes as first-class citizens so it doesn’t have to compute relationships at query time, which makes it more efficient than a relational database.
  

  #### About Nodes in Technopedia
  
  
  Nodes are the entities in the Technopedia graph that store specific categories of data. <br>
  Nodes can have any number of attributes that store data as key-value-pairs, <br>
  for example, `{"edition" : "server"}`<br> 
   * Nodes are entities that store categories of data in Technopedia.
   * Nodes have attributes that store data in key-value pairs.
   * Nodes are connected to other nodes by relationships.
   * Node names are surrounded by parentheses in a query, for example, (Node).

   Here's some examples of nodes in Technopedia:

   ![API Image](/images/nodes_few.png)<br>&nbsp;
  <br>
   
  To get data from multiple nodes in one query, you use defined relationships to other nodes. 
  <br>
  
  #### About Attributes in Technopedia graph database
  
  Attributes belong to nodes and they represent and store data.<br>
  Attributes store data as (key-value-pairs). <br>
  for example, `{"product" : "Excel"}`<br> 

  The following list shows some attributes that belong to the manufacturer node: <br>

   * technopedia_id
   * manufacturer
   * symbol

  #### Relationships connect nodes in Technopedia 

  ######
  Relationships provide semantically relevant connections between the Technopedia nodes. <br>
  
  To get Technopedia data from multiple nodes in one query, you must use relationships in the query to connect the nodes that you want to retrieve data from.
  For example, you might want data for manufacturer, software edtion, and software product in a single query.

  The following information provides an overview of relationships in the Technopedia database:

   * Relationships have a type, such as `BELONGS_TO` and a direction, such as node x to node y. <br>
     An arrow determines the direction of the relationship. <br>
     For example `(node x)-[BELONGS_TO]->(node y)` but node y does not belong to node s. <br>
   * Relationships often exist in a single direction but they can be bidirectional, in which case, there's no arrow.
     For example `(node x)-[BELONGS_TO]-(node y)` <br>    
   * Relationships connect the Technopedia database nodes, for example, the software product node has the relationship: `[HAS_A]->` to the manufacturer node.
   * Relationships allow you to traverse the Technopedia nodes and retreive data from multiple nodes in one query by using the Technopedia query language.
   * Like nodes, relationships can also have attributes. 
     Typically, relationships have quantitative attributes, such as time intervals.


  The following diagram is a simple overview of nodes and relationships:
  <br>

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

