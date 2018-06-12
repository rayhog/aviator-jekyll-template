---
title: TQL Overview
position: 1.05
type:
description:
  The Technopedia query language (TQL) is used with the TQL endpoint to query data in the Technopedia database. <br>
  TQL is the graph-query language that you use to query the database. The graph database stores connections between nodes as first-class citizens so it doesn't have to compute relationships at query time, which makes it more efficient than a relational database.
content_markdown: |-
  ###### TQL is a declarative query language that allows you to specify what data you want to retrieve by using the query language to query nodes and relationships in the Technopedia database.



  #### Get started with TQL<br>

  To create a query by using TQL, you must create a MATCH statement, which is similar to a Select statement in SQL.<br>
  For example, `MATCH (software:SOFTWARE_RELEASE) RETURN software`<br>
  You append the MATCH query statement as a query parameter to the TQL endpoint.<br>
  For example, `https://v6.technopedia.com/tql?q=<MATCH query statement>`
  <br>
  
  The TQL MATCH statement returns results from one or more nodes and relationships that are specified in the query. Typically, the query results are returned in key-value pairs, which resembles the format in the following image: <br>
   <br>
  
  ![API Image](/images/results.png)<br>&nbsp;
  <br>  
  
  #### Parts of a TQL MATCH query<br>

  To create a MATCH statement, you need some or all of the following components:
  
  * MATCH <br>
    The MATCH clause introduces the statement like SELECT in SQL and is the first input. <br>
    `MATCH` <br>
  * Node <br>
    Typically, you refer to a node in the graph as your source of data for the query. Nodes in a query are predeced by a (:) colon. <br>
    `MATCH (:node)` <br>
  * Alias <br>
    You append an alias to the node, for example, 'MATCH (alias:node)', so you can call that alias with the RETURN clasue to return data.<br>
    TQL binds the unique alias to the node so that you can refer to that alias in the Return clause of <br>
    the MATCH query to request specific data. <br>
    `MATCH (alias:node) RETURN alias` <br>
    You can aslo use the alias to specify attributes to return. <br>
    `MATCH (alias:node) RETURN alias.attribute1, alias.attribute2` <br>
  * Relationship <br>
    To get data from more than one node in a query, you must use a relationship to connect the nodes. <br>
    You don't need to append an alias to the relationship, unless, you want to get data back from that relationship. <br>
    `MATCH (aliasx:node1)-[:RELATED_TO]->(aliasy:node2), RETURN aliasx, aliasy` <br>
  * Relationship direction <br>
    The direction of the relationship shows the relationship from one node to another; <br> 
    it is shown by the direction of the arrow in the query. <br>
    For example, node_software is manufactured_by node_manufacturer <br>
    `(:node_software)-[:MANUFACTURED_BY]->(:node_manufacturer)` <br>
    Typically, relationships are unidirectional but they can be bidirectional. <br>
    A bidirectional relationship is represented without an arrow, for example, <br>
    `(:node_software)-[:MANUFACTURED_BY]-(:node_manufacturer)`<br>
  * RETURN <br>
    The RETURN clause defines the data that you want to get back by referring to the alias. <br>
    `MATCH (aliasx:node1) RETURN aliasx` to return all attributes for that node <br>
    `MATCH (aliasx:node1) RETURN aliasx.attribute_xyz` to return only data for `attribute_xyz` from `node1` <br>




  
  <br>
  The following examples show some simple MATCH statements that you use to query the database:
  <br>
  
  ![API Image](/images/simple_match.png)<br>&nbsp;
  <br>  
  The following TQL query shows the most common parts of a MATCH statement:
  <br>
  
  ![API Image](/images/tql_query.png)<br>&nbsp;
  <br>  
    
  <br>
  
  #### Overview of creating a MATCH query<br>


  The following diagram shows a basic overview of creating a query:
  <br>
  
  ![API Image](/images/match.png)<br>&nbsp;
  <br>  
  

  <br>
  To create a MATCH statement you must identify the nodes that store the information you require, and use the following guidelines to help you to build your query:

   1.	Select the Nodes that you want to use in your query.<br>
   2.	Identify the node attributes that store the information you require.<br>
   3.	Select any relationships to connect to nodes that hold your required data.<br>
   4.	Write your MATCH statement

  <br>
  Here’s some examples:
  <br>
  <b>Objective:</b> To find software that is named Adobe.<br>

    * The Software Product node has an attribute called product.<br>
    * We use MATCH to select the `SOFTWARE_PRODUCT` node and the `product` attribute to filter for Adobe.<br>
    * View the list of attributes that you can use on the Software Product page, or you use the following MATCH statement 
      with the `/tql` endpoint to view a list of attributes for the `SOFTWARE_PRODUCT` node.
      `MATCH(x:SOFTWARE_PRODUCT) RETURN x`
      <br>
    * Use the WHERE clause with the equals operator to specify the condition `product = "Adobe"`.<br>
  <br>
  `MATCH (s:SOFTWARE_PRODUCT) WHERE s.product = "Adobe" Return s`

  <br>
  In this example, software products that have Adobe in the name fields are returned.<br>

  <br>
  <br>

   You must add an alias before the colon in nodes and relationships in the MATCH statement. You refer to this alias in the return clause to specify the query ouput.
   {: .warning}

  <br>

  The following diagram shows the software nodes and the relationship directions.
  <br>
  
  ![API Image](/images/sw_graph.png)<br>&nbsp;
  <br>  
  <br>  
  <br>

   For any queries that use relationships, follow the relationship direction in the node graph.
   {: .warning}

  <br>
  <b>Objective:</b> To get software editions that are called "Enterprise Developer" and the edition order is equal to two.  <br>

    * You only have to query the software edition node.<br>
    * You use the attributes edition, and order to filter the output.<br>
    * Use MATCH to select the software edtion node, and add an alias tto use in the RETURN clause.<br>
    * Use the WHERE and AND clauses to add conditions that filter the output.<br>
    
  <br>
  In this query example, you return software editions in Technopedia by edition and order: <br>

  ` MATCH (s:SOFTWARE_EDITION) WHERE s.order = 2 AND s.edition = "Enterprise Developer" RETURN s.edition, s.order`<br>

  <br>
   
  <b>Objective:</b> To get five software editions and product name .
    * You must query the software product and software edition nodes.<br>
    * You use the attributes edition from software edition, and product from the software product node.<br>
    * Use MATCH to select the software edtion node, and add an alias to use in the RETURN clause.<br>
    * Add the `HAS_A` relationship from edition to product and note the direction of the relationship in the diagram.<br>
    * Use the LIMIT clause to limit the results to five.<br>
    
   ![API Image](/images/ed_to_prod.png)<br>&nbsp;
  <br>
  In this query example, you return five software editions in Technopedia by edition and product name: <br>

  `MATCH (s:SOFTWARE_EDITION)-[:HAS_A]->(p:SOFTWARE_PRODUCT) RETURN s.edition, p.product LIMIT 5`<br>

  <br>

  
  <br>

  #### TQL Keywords<br>

  You use the following keywords in your MATCH statements to add conditions and filter data that is returned from your TQL query:

  * WHERE <br>
  Use the WHERE condition to filter results. <br>
  `MATCH (s:SOFTWARE_PRODUCT) WHERE s.product = "Office"  RETURN s` <br>
  Return software products where the name field is equal to 'Office'. <br>

  * AND <br>
  Use the AND clause to add an addtional filter.<br>
  `MATCH (s:SOFTWARE_PRODUCT) WHERE s.product = "Office" AND s.family = "HealthMatics"  RETURN s` <br>
  Return software products where name is Office and the family is HealthMatics. <br>

  * OR <br>
  Use the OR clause to  return either one of two condtions. <br>
  `MATCH (s:SOFTWARE_PRODUCT) WHERE s.product = "Office" OR s.product = "HealthMatics" RETURN s ` <br>
  Return software products where product name is Office or HealthMatics. <br>
  
  * LIMIT <br>
  Limit the number of results that are returned by specifiying a number with the LIMIT clause. <br>
  `MATCH (s:SOFTWARE_PRODUCT) RETURN s LIMIT 5` <br>

  * CONTAINS <br>
  Use the CONTAINS clause to search for words that are contained within an attribute field. <br>
  `MATCH (s:SOFTWARE_PRODUCT) WHERE s.product CONTAINS "Microsoft" RETURN s` <br>

  * DISTINCT <br>
  Return distinct records only. <br>
  `MATCH (s:SOFTWARE_PRODUCT) WHERE s.product = "Microsoft Exchange Server Monitor" RETURN DISTINCT s` <br>

  * COUNT <br>
  Return count of records. <br>
  `MATCH (s:SOFTWARE_PRODUCT) RETURN count(*)` <br>

  * AS <br>
  Return output as another name. <br>
  `MATCH (n:SOFTWARE_EDITION) RETURN n.edition as ED, n.modified_at as MOD` <br>

  * Operators <br>
  `=` equals <br>
  `<>` not equal to <br>
  `>` greater than <br>
  `<` less than <br>
  `>=` greater than or equals <br>
  `<=` less than or equals <br>






 
  To use the MATCH statements in the following examples, you append the MATCH statement to the following tql endpoint and make a GET request from a API client or use cURL. <br>
  <br>
  `https://v6-1.technopedia.com/tql?q=<MATCH Statement>`
  

left_code_blocks:
  - code_block: |-
      MATCH (n:MANUFACTURER) RETURN n LIMIT 1
      
      RESPONSE SAMPLE

      {
        "results": [
            {
                
                "n.cat_manufacturer_id": 594345,
                "n.city": null,
                "n.country": null,
                "n.created_at": null,
                "n.description": null,
                "n.email": null,
                "n.employees": null,
                "n.employees_date": null,
                "n.fax": null,
                "n.fiscal_end_date": null,
                "n.known_as": null,
                "n.legal": "Corporation",
                "n.manufacturer": "Go Ahead Web",
                "n.modified_at": null,
                "n.phone": null,
                "n.profits_date": null,
                "n.profits_per_year": null,
                "n.publicly_traded": null,
                "n.revene_date": null,
                "n.revenue": null,
                "n.state": null,
                "n.street": null,
                "n.symbol": "Private",
                "n.technopedia_id": "513a9c99-608f-4b36-b9b6-3b53dfa85625",
                "n.tier": 3,
                "n.website": "http://www.goaheadweb.co.uk/",
                "n.zip": null
            }
        ]
      {  

    title: Example one
    language: javascript
  - code_block: |-
      MATCH (aliasx:HARDWARE_PRODUCT) RETURN aliasx.product, aliasx.modified_at LIMIT 10
      
      RESPONSE SAMPLE

      {
        "results": [
            {
                "aliasx.modified_at": "2011-03-16 09:46:45",
                "aliasx.product": "Express5800/A1080a Series"
            },
            {
                "aliasx.modified_at": "2011-03-21 11:22:10",
                "aliasx.product": "Phaser 3125 (Networked)"
            },
            {
                "aliasx.modified_at": "2017-06-01 11:29:10",
                "aliasx.product": "Pro 3010 Desktop PC"
            },
            {
                "aliasx.modified_at": "2011-03-16 09:50:28",
                "aliasx.product": "Essentio Series"
            },
            {
                "aliasx.modified_at": "2011-03-16 09:50:30",
                "aliasx.product": "DX100 Series"
            },
            {
                "aliasx.modified_at": "2017-06-01 11:29:10",
                "aliasx.product": "500 Series Notebook PC"
            },
            {
                "aliasx.modified_at": "2011-03-16 09:50:28",
                "aliasx.product": "ThinkCentre A51"
            },
            {
                "aliasx.modified_at": "2017-06-01 11:29:10",
                "aliasx.product": "3Com OfficeConnect Cable/DSL Gateway"
            },
            {
                "aliasx.modified_at": "2011-03-16 13:27:17",
                "aliasx.product": "6000 Series"
            },
            {
                "aliasx.modified_at": "2011-03-16 11:04:11",
                "aliasx.product": "IdeaPad Z560"
            }
        ]
      {  
    title: Example two
    language: javascript
  - code_block: |-
      MATCH (s:SOFTWARE_PRODUCT) WHERE s.product = "Office" OR s.product="HealthMatics" RETURN s LIMIT 2 

      RESPONSE SAMPLE

      {
        "results": [
            {
                
                "s.alias": null,
                "s.cat_sw_product_id": 1074050,
                "s.component": null,
                "s.created_at": "2007-04-22 04:55:16",
                "s.desupported_flag": null,
                "s.discontinued_flag": null,
                "s.family": "HealthMatics",
                "s.is_suite": null,
                "s.modified_at": "2017-06-01 10:44:00",
                "s.product": "Office",
                "s.technopedia_id": "141d9f85-66b2-40a6-8efa-450038c2700c",
                "s.url": "http://investor.allscripts.com/phoenix.zhtml?c=112727&p=irol-newsArticle&ID=858912&highlight="
            },
            {
                "s.alias": null,
                "s.cat_sw_product_id": 38814600,
                "s.component": null,
                "s.created_at": "2013-01-09 10:00:34",
                "s.desupported_flag": null,
                "s.discontinued_flag": null,
                "s.family": null,
                "s.is_suite": "FALSE",
                "s.modified_at": "2014-02-13 21:43:30",
                "s.product": "Office",
                "s.technopedia_id": "35785f94-d5e2-4e0b-b2f1-b7e59ecde968",
                "s.url": "http://www.corel.com/corel/product/index.jsp?pid=prod3430104&cid=catalog50008&segid=692&storeKey=ca&languageCode=en"
            }
        ]
      {  

    title: Example three
    language: javascript
  - code_block: |-
      MATCH (n:SOFTWARE_VERSION) WHERE n.version CONTAINS "1.4.2_05" RETURN n.version, n.order LIMIT 5

      RESPONSE SAMPLE

      {
        "results": [
            {
                "n.order": "66",
                "n.version": "1.4.2_05"
            },
            {
                "n.order": "21",
                "n.version": "1.4.2_05"
            },
            {
                "n.order": "84",
                "n.version": "1.4.2_05"
            }
        ]
      {  

    title: Example four
    language: javascript
  - code_block: |-
      MATCH (n:SOFTWARE_RELEASE) RETURN n.cat_sw_release_id, n.ga_date

      RESPONSE SAMPLE

      {
        "results": [
            {
                "test",
                "s.test",
                "s.anything"
            }
        ]
      {  
    title: Example five
    language: bash
  - code_block: |-
      MATCH (n:SOFTWARE_RELEASE) RETURN n.cat_sw_release_id, n.ga_date

      
    title: cURL
    language: bash
    

right_code_blocks:
  - code_block: |2
      
      Query syntax:
      MATCH (alias_name.NODE) RETURN alias_name
      
      Example:
      MATCH (s:SOFTWARE_PRODUCT) RETURN s
      ___________________________________
      
      Query syntax:
      MATCH (alias.NODE) RETURN alias.attribute
      
      Examples:
      MATCH (s:SOFTWARE_PRODUCT) RETURN s.product 
      MATCH (s:SOFTWARE_PRODUCT) RETURN s.technopedia_id
      MATCH (s:SOFTWARE_PRODUCT) RETURN s.technopedia_id, s.product
      MATCH (s:SOFTWARE_PRODUCT) RETURN s.technopedia_id, s.is_suite  
      __________________________________________________  
 

      Query syntax:
      MATCH (alias.NODE) RETURN alias
      
      Example:
      MATCH (s:SOFTWARE_RELEASE) RETURN s
      ___________________________________ 

      Query syntax:
      MATCH (alias.NODE) RETURN alias.attribute 
      
      Example:
      MATCH (s:SOFTWARE_RELEASE) RETURN s.version 
      ___________________________________________
      
      Query syntax:
      MATCH (alias.NODE) RETURN alias
      
      Example:
      MATCH (n:CPU_MODEL) RETURN n
      ____________________________

      Query syntax:
      MATCH (alias.NODE) RETURN alias.attribute
      
      Example:
      MATCH (s:SOFTWARE_PRODUCT) RETURN s.technopedia_id, s.product

           
    title: MATCH statements
    language: bash
  - code_block: |2-
      MATCH
      WHERE
      AND
      OR
      COUNT
      DISTINCT 
      CONTAINS
      AS
      Operators =, <>, >, <, >=, <=
    title: TQL Clauses and Operators
    language: bash
---