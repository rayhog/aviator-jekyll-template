---
title: Data Overview
position: 1.04
type:
description: >-  
content_markdown: >-
  The Technopedia database is a graph database that uses graph structures for semantic queries with nodes, relationships, and attributes to represent the data.
  You access Technopedia data by querying nodes, attributes, or relationships in the Technopedia graph.<br>
  <br>
  The graph database stores connections between nodes as first-class citizens so it doesn’t have to compute relationships at query time, which makes it more efficient than a relational database.

  Before you start using the Technopedia query language (TQL), it's important to be familiar with the node and relationship infrastructure of the Technopedia database.
  

  #### About Nodes in Technopedia
  
  Nodes are the main entity or data category that you target when you query the Technopedia database. <br>
  For example, you query the manufacturer node to get manufacturer data, or the software product node to get software product data, which you can think of as a data category that stores specific data. <br>
  <br>
  The following list describes what nodes can do:

  <br> 
   * Represent and store categories of data in Technopedia.
   * Have attributes that store data in key-value pairs, for example, `{"edition" : "server"}`.
   * Connect to other nodes through relationships.

   Here's some examples of nodes and relationships:

   ![API Image](/images/nodes_few.png)<br>&nbsp;
  <br>
   
  
  #### About Attributes 
  
  An attribute is an named value that is stored in a node but can be also be in a relationship. <br>
  For example, `{"product" : "Excel"}`<br> 

  The node’s attributes, for example, the edition attribute that belongs to software edition node are represented as key-value pairs within a pair of braces, for example: {edition: "Server"}. 

  The following list shows some attributes that belong to the manufacturer node: <br>

   * technopedia_id
   * manufacturer
   * symbol

  #### Relationships connect nodes in Technopedia 

  ######
  Relationships provide semantically relevant connections between the Technopedia nodes.<br>
  The real power of TQL is its ability to create very specific queries that traverse nodes in the database by using relationships.<br>
  For example, you might want to retrieve data for manufacturer, software edtion, and software product by making one query.
  <br>
  The following information provides an overview of relationships in the Technopedia database:

   * Relationships connect nodes, for example, the software product node connects by the relationship: `HAS_A` to the manufacturer node.
   * Relationships have a type, such as `BELONGS_TO` and a direction, such as node x to node y. <br>
     An arrow determines the direction of the relationship. <br>
     For example `(node x)-[BELONGS_TO]->(node y)` but node y does not belong to node x. <br>
   * Typically, relationships  are unidirectional but they can be bidirectional, in which case, there's no arrow.
     For example `(node x)-[BELONGS_TO]-(node y)` <br>    
   * Relationships allow you to traverse the Technopedia nodes and retreive data from multiple nodes in one query by using TQL.
   * Like nodes, relationships can have attributes. 
     Typically, relationships have quantitative attributes, such as time intervals.


  The following diagram shows a basic overview of nodes and relationships:
  <br>

  ![API Image](/images/nodes_simple.png)<br>&nbsp;
  <br>
    
  <br>
  <br>
  
  The following diagram shows all the nodes and relationships in the Technopedia database. <br>
  <br>
  <br>
  ![API Image](/images/graph.png)<br>&nbsp;
  <br>

  
   Note: You can only access data from Technopedia nodes that your subscription allows.
    {: .warning} 

  




right_code_blocks:
  - code_block: |2
      Technopedia Nodes

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
    language: text
  - code_block: |2-

      SOFTWARE_PRODUCT Attribures Examples

      "s.alias": null,
      "s.component": null,
      "s.created_at": "2007-04-22 04:55:16",
      "s.desupported_flag": null,
      "s.discontinued_flag": null,
      "s.family": "HealthMatics",
      "s.is_suite": null,
      "s.modified_at": "2017-06-01 10:44:00",
      "s.product": "Office",
      "s.technopedia_id": "141d9f85-66b2-40a6-8...",
      "s.url": "http://investor.allscripts.com/"

      

           
    title: Attributes
    language: bash
---

