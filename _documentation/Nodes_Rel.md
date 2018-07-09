---
title: Data Overview
position: 1.02
type:
description: >-  
content_markdown: >-
  The Technopedia database is a graph database that uses graph structures for semantic queries with nodes, relationships, and attributes.
  You access Technopedia data by querying nodes, attributes, or relationships in the Technopedia graph.<br>
  <br>
  
  Before you start using the Technopedia query language (TQL), you must be familiar with nodes, attributes, and relationships in the Technopedia graph database.
  

  #### Nodes in Technopedia
  
  Nodes represent entities that are equivalent to a data category such as hardware or software, and they are the main entity that you target when you query the Technopedia database. <br>
  For example, you might query the manufacturer node to get manufacturer data, or the software product node to get software product data. <br>
  <br>
  The following list describes node charactertistics:

  <br> 
   * Represent data categories in Technopedia.
   * Have attributes that store data in key-value pairs, for example, `{"edition" : "server"}`.
   * Connect with other nodes through defined relationships.

   Here's some examples of nodes and relationships:

   ![API Image](/images/nodes_few.png)<br>&nbsp;
  <br>
   
  
  #### About Attributes 
  
  An attribute is an named value that is stored under a node.  <br>
  For example, `{"product" : "Excel"}` <br> 
  Relationships can also have attributes.

  <br>
  The following list is an example that shows some manufacturer node attibutes: <br>

   * technopedia_id
   * manufacturer
   * symbol

  #### Relationships connect nodes  

  Relationships connect nodes in the graph database, which enables you to include multiple nodes in one query by adding a node-to-node relationship. <br>
  For example, you might want to retrieve data for manufacturer, software edtion, and software product by making one query.
  <br>

  The following diagram shows a basic overview of some nodes and relationships in Technopedia:
  <br>

  ![API Image](/images/nodes_simple.png)<br>&nbsp;
  <br>
    
  <br>
  <br>
  
  The following diagram shows all of the nodes and relationships in the Technopedia database. <br>
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
      HARDWARE_PRODUCT
      HARDWARE_MODEL
      CATEGORY_2
      CATEGORY_1
      CATEGORY_GROUP
      VERTICAL
      SUPPORT_STAGE
      SUPPORT_POLICY
      CERTIFICATION
      COMPATIBLE PLATFORM



           
    title: Nodes
    language: tex
  - code_block: |2-

      SOFTWARE_PRODUCT Attributes

      alias
      component
      created_at
      desupported_flag
      discontinued_flag
      family
      is_suite
      modified_at
      product
      technopedia_id
      url

      

           
    title: Attributes
    language: bas
---

