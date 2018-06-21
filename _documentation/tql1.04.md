---
title: TQL Overview
position: 1.05
type:
description:
  
content_markdown: |-
  You create queries by using the Technopedia query language (TQL), which you use with the TQL endpoint to retrieve data from the Technopedia database. <br>
  <br>
  TQL is the graph-query language that you use to query the Technopedia database. 
  TQL is a declarative query language that allows you to specify the data you want to retrieve by using the query language to query nodes, relationships, and attributes in the Technopedia database.


  #### Get started with TQL<br>

  To create a query by using TQL, you must create a MATCH statement, which is similar to a Select statement in SQL.<br>
  For example, `MATCH (software:SOFTWARE_RELEASE) RETURN software`<br>
  
  You add the MATCH query statement as a query parameter to the TQL endpoint.<br>
  For example, `https://v6-1.technopedia.com/tql?q=<MATCH statement>`
  <br>
  
  The TQL MATCH statement returns results from one or more nodes and relationships that you specify in the query. Typically, the query results are returned in key-value pairs, which resembles the format in the following image: <br>
   <br>
  
  ![API Image](/images/results.png)<br>&nbsp;
  <br>  
  
  #### Components of a TQL MATCH query<br>

  To create a TQL MATCH statement, you need some or all of the following components:
  
  * MATCH <br>
    The MATCH clause introduces the statement like SELECT in SQL and is the first part of any query.<br> 
    You use MATCH to select a node in Technopedia.<br>
    `MATCH` <br>
  * Node <br>
    Typically, you refer to a node or nodes in the graph as your source of data for the query.<br> 
    Nodes in a query are predeced by a (:) colon. <br>
    `MATCH (:node)` <br>
  * Alias <br>
    To enable the `RETURN` clause to return data from a node, you append an alias to the node, for example, 'MATCH (alias:node)'. <br>
    TQL binds the unique alias to the node so that you can refer to that alias in the Return clause of <br>
    the MATCH query to request specific data. <br>
    `MATCH (alias:node) RETURN alias` <br>
    You can also use the alias to specify specific node attributes that you want to return. <br>
    `MATCH (alias:node) RETURN alias.attribute1, alias.attribute2` <br>
  * Relationship <br>
    To get data from more than one node in a query, you must use a relationship to connect the nodes. <br>
    You don't need to append an alias to the relationship, unless, you want to get data back from that relationship. <br>
    `MATCH (aliasx:node1)-[:RELATED_TO]->(aliasy:node2), RETURN aliasx, aliasy` <br>
  * Relationship direction <br>
    The direction of the relationship shows the relationship from node to node. <br> 
    An arrow in the query shows a unidirectional relationship, and no arrows indicate a birdirectional relationship. <br>
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
  The following query examples are based on the nodes and relationship in the diagram:
  <br>
  
  ![API Image](/images/simple_match.png)<br>&nbsp;
  <br>  
   *  `MATCH (alias:SOFTWARE_EDITON) RETURN alias` <br>
       Return all software editions and attributes <br>

   *  `MATCH (x:SOFTWARE_EDITON) RETURN x.edition` <br>
       Return all software editions with only the edition attribute <br>

   *  `MATCH (y:SOFTWARE_PRODUCT) RETURN y` <br>
       Return all software products and attributes <br>

   *  `MATCH (sp:SOFTWARE_PRODUCT) RETURN sp.product` <br>
       Return all software products with only the product attribute <br>

   *  `MATCH (z:SOFTWARE_EDITON)-[HAS_A]->(k:SOFTWARE_PRODUCT) RETURN z, k.product` <br>
       Returns all attributes for software editon and related products by product name. <br>    

    
  <br>
  The following TQL query shows the most common components of a MATCH statement:
  <br>
  
  ![API Image](/images/tql_query.png)<br>&nbsp;
  <br>  
    
  <br>
  
  #### Overview of creating a TQL query<br>


  The following diagram shows a basic overview of the initial steps you take to create a query with TQL:
  <br>
  
  ![API Image](/images/match.png)<br>&nbsp;
  <br>  
  

  <br>
  Use the following guidelines to help you get started with building a basic query:

   1.	Identify the relevant node or nodes that store the data you want to retrieve.<br>
   2.	Identify any node attributes that you want to target for your data, for example, you use the product
        attribute of the software product node to get names of software products. <br>   
   3.	For queries that involve more than one node, identify any relationships that connect the nodes.<br>
   4.   Note any conditions that you want to apply to filter the data.
   5.	Write your MATCH statement

  To view a list of attributes for any node, you use the 
  `MATCH (alias:NODE) RETURN alias` query with the TQL endpoint.
  For example, `https://v6-1.technopedia.com/tql?q=MATCH (n:SOFTWARE_PRODUCT) RETURN n LIMIT 1`
  {: .warning}

  <br>
  Here’s some query examples:

  <br>
  <b>Query Intent:</b> To find software products that contain Adobe in their product name.<br>

  The Software Product node has an attribute named product that lists the product name.<br>
  View the list of attributes that you can use on the Software Product page, or you can use the query: <br>
  `MATCH(x:SOFTWARE_PRODUCT) RETURN x` to get a list of attributes. <br>

    1. Use the MATCH clause to select the `SOFTWARE_PRODUCT` because it
       has the `product` attribute with a product (name) field.<br>
       `MATCH (:SOFTWARE_PRODUCT)`
    2. Add an alias to the node, so that you can use it with the RETURN clause to get data from that node. <br>
       You place the alias before the colon.
       `MATCH (s:SOFTWARE_PRODUCT)`  
    3. Use the `WHERE` clause with the `CONTAINS` clause to specify the condition `product CONTAINS "Adobe"`.<br>
       `WHERE s.product CONTAINS "Adobe"`
    4. Refer to the alias in the RETURN clause to list software products that contain Adobe in the product name.  <br>
       `Return s`

    The following query is the complete query:<br>
    `MATCH (s:SOFTWARE_PRODUCT) WHERE s.product CONTAINS "Adobe" Return s`<br>

  <br>
  In this example, software products that have Adobe in the product field are returned. <br>
  The following sample return shows two results for software products that have Adobe in their product name.<br>
  <br>
  ![API Image](/images/adobe_contains.png)<br>&nbsp;
  <br>  
  
 
   You must add an alias before the colon for nodes that you reference with the RETURN clause in the MATCH statement. The return clause references the alias to generate the query ouput.
   {: .warning}

  <br>

  The following diagram shows the software nodes and the relationships directions.
  <br>
  
  ![API Image](/images/sw_graph.png)<br>&nbsp;
  <br>  
  
  
   For any queries that use relationships, follow the relationship direction that's shown in the node graph.
   {: .warning}

  <br>
  <b>Query Intent:</b> To get software editions named "Enterprise Developer" where the edition order is equal to two.  <br>
  In this query, you query the software edition node.
    
    1. Use `MATCH` to select the software edtion node, and add the alias `se` or any other alias to the node that you refer to in the `RETURN` clause.<br>
      `MATCH (se:SOFTWARE_EDITION)`
    2. Use the `WHERE` and `AND` clauses to add conditions that filter the output.<br>
      `MATCH (alias:SOFTWARE_EDITION) WHERE s.order = 2 AND s.edition = "Enterprise Developer"`<br>
    3. You use the `RETURN` clause to select the query output by referring to the alias and attributes.<br>
      `RETURN s.edition, s.order, s.technopedia_id`  

  <br>
  In this query example, you return software editions in Technopedia by edition, order, and Technopedia ID: <br>
  
  `MATCH (s:SOFTWARE_EDITION) WHERE s.order = 2 AND s.edition = "Enterprise Developer" RETURN s.edition, s.order, s.technopedia_id`<br>
  <br>
  The following image shows the data that is returned for the query:<br>
  <br>
  ![API Image](/images/edition_query.png)<br>&nbsp;
  <br>  

  <b>Query Intent:</b> To get any five software editions and product names that are associated with those editions.<br>
  You must query the software product and software edition nodes.<br>

    1. Use `MATCH` to select the software edtion node, and add node aliases to use in the `RETURN` clause.<br>
       `MATCH (s:SOFTWARE_EDITION)`
    2. Add the `HAS_A` relationship from edition to product and note the direction of the relationship in the diagram.<br>
      `MATCH (s:SOFTWARE_EDITION)-[:HAS_A]->(p:SOFTWARE_PRODUCT)`<br>
       You must add an alias for software product becuause you use the alias (p) in the return clause to return the product name.  
    3. You use the `RETURN` clause to select the query output by referring to the alias and attributes.<br>
       You use the attributes `edition` from software edition and `product` from the software product node.<br> 
       `RETURN s.edition, p.product` or you can return all attributes by using `RETURN s, p` <br>  
    4. To limit the number of results, you use the `LIMIT` clause to limit the results to five or any number that you want.<br>   

        
   ![API Image](/images/ed_to_prod.png)<br>&nbsp;
  <br>
  In this query example, you use a relationship to connect nodes, and you return five software editions and corresponding product names: <br>
  The `HAS_A` relationship connects the software edtiion and software product nodes, which allows you to get data from both nodes.

  `MATCH (s:SOFTWARE_EDITION)-[:HAS_A]->(p:SOFTWARE_PRODUCT) RETURN s.edition, p.product LIMIT 5`<br>
  <br>
  The following image shows the data that is returned by the query:<br>
  <br>

  ![API Image](/images/prod_ed.png)<br>&nbsp;
  <br>  
    
  #### TQL Clauses and Operators<br>

  Use the following clauses and operators in your MATCH statements to filter Technopedia data:

  * WHERE, <br>
  Use the `WHERE` clause to filter results. <br>
  `MATCH (s:SOFTWARE_PRODUCT) WHERE s.product = "Office"  RETURN s` <br>
  Return software products where the product field is equal to 'Office'. <br>

  * AND <br>
  Use the AND clause to add an addtional filter.<br>
  `MATCH (s:SOFTWARE_PRODUCT) WHERE s.product = "Office" AND s.family = "HealthMatics"  RETURN s` <br>
  Return software products where product name is Office and the family is HealthMatics. <br>

  * OR <br>
  Use the OR clause to  return either one of two condtions. <br>
  `MATCH (s:SOFTWARE_PRODUCT) WHERE s.product = "Office" OR s.product = "HealthMatics" RETURN s ` <br>
  Return software products where product name is Office or HealthMatics. <br>
  
  * LIMIT <br>
  Limit the number of results that are returned by specifiying a number with the LIMIT clause. <br>
  `MATCH (s:SOFTWARE_PRODUCT) RETURN s LIMIT 5` <br>

  * CONTAINS <br>
  Use the CONTAINS clause to match words that are contained within an attribute field. <br>
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

  * ORDER BY in DESC or ASC order <br>
  Return list of products in ascending or descending order.<br>
   `MATCH (n:SOFTWARE_PRODUCT) RETURN n.product ORDER BY n.product DESC`   

  * Operators <br>
  `=` equals <br>
  `<>` not equal to <br>
  `>` greater than <br>
  `<` less than <br>
  `>=` greater than or equals <br>
  `<=` less than or equals <br>



  #### Query Examples <br>
    
  To use the `MATCH` statements in the following examples, you append the `MATCH` statement to the following `/tql` endpoint and make a GET request from a API client or use cURL. <br>
  <br>
  `https://v6-1.technopedia.com/tql?q=<MATCH Statement>`
  

left_code_blocks:
  - code_block: |-
      MATCH (n:MANUFACTURER) RETURN n 
      LIMIT 1
      
      RESPONSE SAMPLE

      {
        "results": [
            {
                
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
                "n.revenue": null,
                "n.revenue_date": null,
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
      MATCH (aliasx:HARDWARE_PRODUCT) 
      RETURN aliasx.product, aliasx.modified_at 
      LIMIT 10

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
      MATCH (s:SOFTWARE_PRODUCT) WHERE s.product = "Office" OR s.product="HealthMatics" 
      RETURN s 
      LIMIT 2 

      RESPONSE SAMPLE

      {
        "results": [
            {                
                "s.alias": null,
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
                "s.component": null,
                "s.created_at": "2013-01-09 10:00:34",
                "s.desupported_flag": null,
                "s.discontinued_flag": null,
                "s.family": null,
                "s.is_suite": "FALSE",
                "s.modified_at": "2014-02-13 21:43:30",
                "s.product": "Office",
                "s.technopedia_id": "35785f94-d5e2-4e0b-b2f1-b7e59ecde968",
                "s.url": "http://www.corel.com/corel/product/index.jsp?
                 pid=prod3430104&cid=catalog50008&segid=692&storeKey=ca&languageCode=en"
            }
        ]
      {  

    title: Example three
    language: javascript
  - code_block: |-
      MATCH (n:SOFTWARE_VERSION) WHERE n.version CONTAINS "1.4.2_05" 
      RETURN n.version, n.order 
      LIMIT 5

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
      MATCH (n:SOFTWARE_RELEASE)-[:HAS_A]->(:SOFTWARE_VERSION)-[:HAS_A]->(sp:SOFTWARE_PRODUCT) 
      WHERE n.release CONTAINS "23" 
      RETURN n.release, sp.product 
      LIMIT 5

      RESPONSE SAMPLE

      {
        "results": [
            {
                "n.release": "123 Audio MP3 Converter",
                "sp.product": "123 Audio MP3 Converter"
            },
            {
                "n.release": "5523 ADSL Work Station (AWS)",
                "sp.product": "5523 ADSL Work Station (AWS)"
            },
            {
                "n.release": "123Scan",
                "sp.product": "123Scan"
            },
            {
                "n.release": "123Scan",
                "sp.product": "123Scan"
            },
            {
                "n.release": "123Scan",
                "sp.product": "123Scan"
            }
        ]
      {  
    title: Example five
    language: javascript
  - code_block: |-
      MATCH (n:SOFTWARE_RELEASE)-[:HAS_A]->(:SOFTWARE_VERSION)-[:HAS_A]->(sp:SOFTWARE_PRODUCT)-[:HAS_A]->(m:MANUFACTURER) 
      WHERE m.manufacturer CONTAINS "people" 
      RETURN n.release, sp.product, m.manufacturer 
      LIMIT 5

      RESPONSE SAMPLE

      {
        "results": [
            {
                "m.manufacturer": "Peoplefluent",
                "n.release": "AAPlanner",
                "sp.product": "AAPlanner"
            },
            {
                "m.manufacturer": "Peoplefluent",
                "n.release": "AAPlanner",
                "sp.product": "AAPlanner"
            },
            {
                "m.manufacturer": "Peoplefluent",
                "n.release": "AAPlanner",
                "sp.product": "AAPlanner"
            },
            {
                "m.manufacturer": "Peoplefluent",
                "n.release": "AAPlanner",
                "sp.product": "AAPlanner"
            },
            {
                "m.manufacturer": "PeopleCube",
                "n.release": "Scheduler Plus",
                "sp.product": "Scheduler Plus"
            }
        ]
      {  
    

    title: Example six
    language: javascript

  - code_block: |-
      MATCH (a:SOFTWARE_PRODUCT{product:"e1ns.output"}) 
      RETURN a

      RESPONSE SAMPLE

      {
        "results": [
            {
                "a.alias": null,
                "a.component": null,
                "a.created_at": "2017-05-19 10:24:33",
                "a.desupported_flag": null,
                "a.discontinued_flag": null,
                "a.family": null,
                "a.is_suite": "FALSE",
                "a.modified_at": "2017-06-01 13:50:16",
                "a.product": "e1ns.output",
                "a.technopedia_id": "408dd3bb-c935-444e-b756-c7d431a589f7",
                "a.url": "http://www.plato.de/e1nsoutput-687.html"
            }
        ]
      {  
    

    title: Example seven
    language: javascript  

  title: Example six
    language: javascript

  - code_block: |-
      MATCH (:HARDWARE_PRODUCT)-[H:HAS_A]-(m:MANUFACTURER {symbol:'NTAP'}) 
      RETURN 
      m.manufacturer AS manu_name, 
      m.description AS desc 
      LIMIT 1

      RESPONSE SAMPLE

      {
        "results": [
            {
                "desc": "NetApp, Inc. (NetApp), formerly Network Appliance, Inc., 
                is a provider of storage and data management solutions. 
                (Google Finance: http://www.google.com/finance?q=netapp)",
                "manu_name": "NetApp"
            }
        ]
      {  
    

    title: Example eight
    language: javascript    
  - code_block: |-
      curl -G -H "Authorization: Bearer b93477a9-057b-4878-a16b93477a9-057b-4878-a16f-d7f7d1f27a7af-d7f7d1f27a7a" "https://v6-1.technopedia.com/tql" --data-urlencode' "q=MATCH (n:SOFTWARE_RELEASE) RETURN n.release

      
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
      ORDER BY
      Operators =, <>, >, <, >=, <=
    title: TQL Clauses and Operators
    language: bash
---