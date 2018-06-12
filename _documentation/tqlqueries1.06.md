---
title: More TQL
position: 1.06
type:
description:
  TQL queries can be based on a single node or multiple nodes where you need to include relationships to get data from multiple nodes. For many TQL queries, you have to use relationships to query several Technopedia nodes. Relationships might seem complex but their function is mainly to connect nodes.
content_markdown: |-
  ###### Because TQL is a declarative query language, you can build your query with multiple nodes, relationships, attributes, and add multiple conditions to refine your query.<br>
  

  You can use an alias or variable with a realtionship that has attributes when you want to return data for those attributes. TQL binds the alias that you specify to that relationship, which you can use with the Return clause of the MATCH query to get specific data.
  {: .info}

  #### Building relationships in a query<br>

  
  ###### Relationships provide a way of getting related data from multiple nodes in one query. You connect the nodes by using the relationship that's shown in the database graph. <br>
  
  {: .info}

  Note the direction of the relationship in the graph. If you specify an incorrect direction, you might not get data from the nodes that you want to connect with.

  
  

  The following image shows examples of types of relationships and their directions.
   
  ![API Image](/images/relat.png)<br>&nbsp;
  <br>  
 

  
  <br>
  

  #### Overview............. query<br>

  `MATCH (hw_mod:HARDWARE_MODEL)-[:HAS_A]->(hw_prod:HARDWARE_PRODUCT)<-[:HAS_A]-(manu:MANUFACTURER) RETURN hw_mod, hw_prod, manu`


  `MATCH (node)-[My_alias:relationship {relationship_attribute : value}]->(:node) Return My_alias


      MATCH (:SOFTWARE_RELEASE)-[h:HAS_A {end_date: "2013-12-10 00:00:00"}]->(:SUPPORT_STAGE) RETURN h
      

      RESPONSE SAMPLE

      {
        "results": [
            {
                "end_date": "2013-12-10 00:00:00",
                "modified_at": "2018-05-04 20:01:57",
                "created_at": "2018-05-03 17:29:30"
            }
        ]
      {  `
  
  
  
  QUERY INTENT
  Return release name, software version, software product name, and manufacturer name for 2 software releases
  `MATCH (srelease:SOFTWARE_RELEASE) -[:HAS_A]->(sver:SOFTWARE_VERSION)-[:HAS_A]->(sprod:SOFTWARE_PRODUCT)-[:HAS_A]->(manu:MANUFACTURER) RETURN srelease.release, sver.version, sprod.product, manu.manufacturer LIMIT 2`

  

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

  The following diagram identifies the software nodes and the relationship directions.
  <br>
  
  ![API Image](/images/sw_graph.png)<br>&nbsp;
  <br>  
  <br>  
  <br>

   When you write MATCH statements that use relationships, you must follow the relationship direction in the diagram.
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

  #### TQL extended relationships<br>


  Here are some examples of extended relationships that connect multiple nodes:

  <b>Query Intent:</b> 

 
 
  The following MATCH query examples show variations in constructions that use relationships and other conditions. To try out a query example, you append the MATCH statement to the following tql endpoint and make a GET request from a API client or use cURL. <br>
  <br>
  `https://v6-1.technopedia.com/tql?q=<MATCH Statement>`
  
left_code_blocks:
  - code_block: |-
      MATCH (n:SOFTWARE_RELEASE)-[:HAS_A]->(:SOFTWARE_VERSION)-[:HAS_A]->(sp:SOFTWARE_PRODUCT)-[:HAS_A]->(m:MANUFACTURER)<-[:HAS_A]-(:CPU_MODEL) WHERE m.manufacturer CONTAINS "TEL" RETURN n.release, sp.product, m.manufacturer LIMIT 5
      
      RESPONSE SAMPLE

      {
        "results": [
            {
                "m.manufacturer": "Intel",
                "n.release": "C++ Composer XE",
                "sp.product": "C++ Composer XE"
            },
            {
                "m.manufacturer": "Intel",
                "n.release": "C++ Composer XE",
                "sp.product": "C++ Composer XE"
            },
            {
                "m.manufacturer": "Intel",
                "n.release": "C++ Composer XE",
                "sp.product": "C++ Composer XE"
            },
            {
                "m.manufacturer": "Intel",
                "n.release": "C++ Composer XE",
                "sp.product": "C++ Composer XE"
            },
            {
                "m.manufacturer": "Intel",
                "n.release": "C++ Composer XE",
                "sp.product": "C++ Composer XE"
            }
        ]
      {  

    title: Example one
    language: javascript
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
      MATCH (n:SOFTWARE_RELEASE)-[:HAS_A]->(:SOFTWARE_VERSION)-[:HAS_A]->(sp:SOFTWARE_PRODUCT) WHERE n.release CONTAINS "23" RETURN n.release, sp.product LIMIT 5

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
    language: bash
  - code_block: |-
      MATCH (n:SOFTWARE_RELEASE)-[:HAS_A]->(:SOFTWARE_VERSION)-[:HAS_A]->(sp:SOFTWARE_PRODUCT)-[:HAS_A]->(m:MANUFACTURER) WHERE m.manufacturer CONTAINS "people" RETURN n.release, sp.product, m.manufacturer LIMIT 5

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
      Return distinct records only, which don't show duplicates.
      MATCH (s:SOFTWARE_PRODUCT) WHERE s.product = "Microsoft Exchange Server Monitor" RETURN DISTINCT s 
      
      CONTAINS
      Use the CONTAINS clause to return results when an attribute word value is matched. 
      MATCH (s:SOFTWARE_PRODUCT) WHERE s.product CONTAINS "Microsoft" RETURN s 

      AS
      Return output parameter as another name. 
      MATCH (n:SOFTWARE_EDITION) RETURN n.edition as ED, n.modified_at as MOD

      Operators =, <>, >, <, >=, <=
    title: TQL Clauses and examples
    language: bash
---