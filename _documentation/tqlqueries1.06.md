---
title: TQL Queries
position: 1.06
type:
description:
  TQL queries can be a simple query on a single node or you might need to add multiple relationships to get data from multiple nodes. For many TQL queries, you have to use relationships to query several Technopedia nodes. Relationships might seem complex but their function is mainly to connect nodes.
content_markdown: |-
  ###### Because TQL is a declarative query language, it allows you build your query with multiple nodes, relationships, and attributes.


  #### Building relationships in a query<br>

  To make a query with TQL, you must use a MATCH statement, which is like Select statement in SQL. You add the MATCH statement as a query parameter to the TQL endpoint `https://v6.technopedia.com/tql` <br>
  For example, `https://v6.technopedia.com/tql?q=MATCH <query_parameters>`
  <br>
  
  
  The following TQL query shows the parts of a MATCH statement that you use to query the database:
  <br>
  
  ![API Image](/images/tql_query.png)<br>&nbsp;
  <br>  
 

  
  <br>
  

  #### Overview of creating a MATCH query<br>


  
  

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

           
    title: MATCH Statements
    language: bash
  - code_block: |2-
      
      WHERE
      Return software products where the name field is equal to ‘Office’.
      MATCH (s:SOFTWARE_PRODUCT) WHERE s.product = "Office"  RETURN s

      AND
      Return software products where name is Office and the family is HealthMatics. 
      MATCH (s:SOFTWARE_PRODUCT) WHERE s.product = "Office" AND s.family = "HealthMatics" RETURN s 
           
      OR
      Return software products where product name is Office or HealthMatics. 
      MATCH (s:SOFTWARE_PRODUCT) WHERE s.product = "Office" OR s.product = "HealthMatics" RETURN s 
            
      COUNT
      Return count of records. 
      MATCH (s:SOFTWARE_PRODUCT) RETURN count(*) 

      DISTINCT
      Return distinct records only. 
      MATCH (s:SOFTWARE_PRODUCT) WHERE s.name = "Microsoft Exchange Server Monitor" RETURN DISTINCT s 
      
      CONTAINS
      Use the CONTAINS clause to search for works that are contained within attribues. 
      MATCH (s:SOFTWARE_PRODUCT) WHERE s.name CONTAINS "Microsoft" RETURN s 

      AS
      Return output as another name. 
      MATCH (n:SOFTWARE_EDITION) RETURN n.edition as ED, n.modified_at as MOD

      Operators =, <>, >, <, >=, <=
    title: TQL Clauses and examples
    language: bash
---