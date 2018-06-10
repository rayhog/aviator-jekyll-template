---
title: TQL Queries
position: 1.06
type:
description:
  The Technopedia query language (TQL) is used with the TQL endpoint to query data in the Technopedia database. <br>
  TQL is the graph-query language that you use to query the database. The graph database stores connections between nodes as first-class citizens so it doesn't have to compute relationships at query time, which makes it more efficient than a relational database.
content_markdown: |-
  ###### TQL is a declarative query language that allows you to specify what data you want to retrieve by using the query language to query nodes and relationships in the Technopedia database.


  #### Get started with TQL<br>

  To make a query with TQL, you must use a MATCH statement, which is like Select statement in SQL. You add the MATCH statement as a query parameter to the TQL endpoint `https://v6.technopedia.com/tql` <br>
  For example, `https://v6.technopedia.com/tql?q=MATCH <query_parameters>`
  <br>
  
  The TQL MATCH statement returns results from one or more nodes and relationships that are specified in the query. Typically, the query results are returned in key-value pairs, which resembles the following format: <br>
   <br>
  
  ![API Image](/images/results.png)<br>&nbsp;
  <br>  

  <br>
  The following examples show some simple MATCH statements that you use to query the database:
  <br>
  
  ![API Image](/images/simple_match.png)<br>&nbsp;
  <br>  
  The following TQL query shows the parts of a MATCH statement that you use to query the database:
  <br>
  
  ![API Image](/images/tql_query.png)<br>&nbsp;
  <br>  
 

  To get data from a specific node or relationship, you use an alias or variable that you append to the node or relationship. TQL binds the alias that you specify to that node or relationship so you can use that alias in the Return clause of the MATCH query to get your specific data.
  <br>
  `Match (myalias:node1)-[another_alias:RELATIONSHIP]->(other_alias:node2)`
  <br>
  `MATCH (aliasX:MANUFACTURER)-[aliasV:VENDOR_OF]->(aliasY:SOFTWARE_PRODUCT) RETURN aliasX, aliasY`
  
  <br>
  

  #### Overview of creating a MATCH query<br>


  The following diagram shows a basic overview of creating a query:
  <br>
  
  ![API Image](/images/match.png)<br>&nbsp;
  <br>  
  

  <br>
  To create a MATCH statement you must identify the nodes that store the infromaiton you require, and use the following guide to help you to build your query:

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
  <br>
  <br>

  The following diagram identifies the software nodes and the relationship directions.
  <br>
  
  ![API Image](/images/sw_graph.png)<br>&nbsp;
  <br>  
  <br>  
  <br>

   Follow the relationship direction in the diagram.
   {: .warning}

  <br>
  <b>Objective:</b> To get software editions that have a release, verison, and product.<br>

    * To get the required information, you have to add relationships to the software release, software version, and software product nodes.<br>
    * We use MATCH to select the software edtion node and then create relationships to the other nodes.<br>
    * Add an alias to each node and relationship in the  query.<br>
    * To return the data that you need, use the Return clause to refer to the specific aliases.<br>
  <br>
  In this query example, you return software editions in Technopedia with release, verison, and product information. <br>

  `MATCH (e:SOFTWARE_EDITION)<-[x:HAS_A]-(r:SOFTWARE_RELEASE)-[y:HAS_A]->(v:SOFTWARE_VERSION)-[z:HAS_A]->(p:SOFTWARE_PRODUCT) RETURN r,e,v,p`<br>

  <br>
  
  <br>
   
  <b>Objective:</b> To get software editions that have a release, verison, product, and manufacturer.<br>
  <br>
  In this query example, you get data for software editions in Technopedia, with release, version, product, and manufacturer data for each edition that is listed. <br>

  `MATCH (e:SOFTWARE_EDITION)<-[:HAS_A]-(r:SOFTWARE_RELEASE)-[:HAS_A]->(v:SOFTWARE_VERSION)-[:HAS_A]->(p:SOFTWARE_PRODUCT)<-[:HAS_A]-(m:MANUFACTURER) RETURN e,r,v,p,m LIMIT 10`<br>

  
  <br>

  #### TQL Keywords<br>

  You use the following keywords in your MATCH statements to filter data that is returned from your TQL query:

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
  Use the CONTAINS clause to search for works that are contained within attribues. <br>
  `MATCH (s:SOFTWARE_PRODUCT) WHERE s.name CONTAINS "Microsoft" RETURN s` <br>

  * DISTINCT <br>
  Return distinct records only. <br>
  `MATCH (s:SOFTWARE_PRODUCT) WHERE s.name = "Microsoft Exchange Server Monitor" RETURN DISTINCT s` <br>

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
      
      MATCH (alias1.NODE) RETURN alias1 

      MATCH (s:SOFTWARE_PRODUCT) RETURN s
      

      MATCH (alias.NODE) RETURN alias.attribute
      
      MATCH (s:SOFTWARE_PRODUCT) RETURN s.product 
      MATCH (s:SOFTWARE_PRODUCT) RETURN s.technopedia_id
      MATCH (s:SOFTWARE_PRODUCT) RETURN s.technopedia_id, s.product
      MATCH (s:SOFTWARE_PRODUCT) RETURN s.technopedia_id, s.is_suite    
 


      MATCH (alias2.NODE) RETURN alias2

      MATCH (s:SOFTWARE_RELEASE) RETURN s 


      MATCH (alias.NODE) RETURN alias.attribute 
      MATCH (s:SOFTWARE_RELEASE) RETURN s.version 
      

      MATCH (alias3.NODE) RETURN alias3 
      MATCH (n:MANUFACTURER) RETURN n


      MATCH (alias4.NODE) RETURN alias4.attribute
      MATCH (n:MANUFACTURER) RETURN n.manufactuer 

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