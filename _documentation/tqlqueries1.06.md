---
title: TQL Queries
position: 1.06
type:
description:
  
content_markdown: |-
  TQL queries can be based on a single node, or multiple nodes where you need to include relationships to get data from multiple nodes in one  query. For many TQL queries, you have to use relationships to query several Technopedia nodes. Relationships might seem complex but one of their main functions is to connect nodes. <br>
  <br>
  Because TQL is a declarative query language, you can build your query with multiple nodes, relationships, attributes, and add multiple conditions to refine your query.<br>
  

  Like nodes, relationships can have attributes. Add an alias to the relationship when you want to return data for those relationship attributes. TQL binds the alias that you specify to the relationship, which you can refer to in the `RETURN` clause of the `MATCH` statement to retrieve your queried data.
  {: .warning}

  #### Building relationships to connect nodes in a query<br>

  
  Relationships provide connections to other nodes, which enables you to get data from multiple nodes in one query. You connect the nodes by using the relationship that's shown in the database graph. <br>
  
  {: .warning}

  Note the direction of the relationship in the graph. If you specify an incorrect direction, you might not get data from the nodes that you want to connect with.

  
  <br>

  The following image shows examples of types of relationships and their directions.
  <br>
   
  ![API Image](/images/relat.png)<br>&nbsp;
  <br>  
  

  #### Examples of building relationships<br>   

  <br>
  To incoporate multiple nodes in a MATCH statement you must use relationships to connect the nodes and then use the `RETURN` clause to get data from the nodes in the query. Use the following guide to help you to build your query:

   1.	Select the Nodes that you want to use in your query.<br>
   2.	Identify the node attributes that store the information you require.<br>
   3.	Identify any relationships that are required to connect nodes that hold your targeted data.<br>
   4.	Write your MATCH statement.

  <br>
  
  The following diagram shows the nodes and relationships that are used in the query examples that follow:
  <br>
  ![API Image](/images/sw_relat.png)<br>&nbsp;
  <br>  

  <b>Query Intent:</b> Get software that is manufactured by Oracle and return data for the manufactuer, product name, version, release, and edition.<br>
  The first node that you reference is the `MANUFACTURER` node, and then you use relationships to connect the other nodes.<br>
    1. Write the first part your query by using `MATCH` to select the `MANUFACTURER` node, and add an alias to the node. <br>
      `MATCH (m:MANUFACTURER)`<br>
    2. You must add the following relationships to connect with the product, version, release, and edtion nodes.<br>
       For each node, you must add an alias so that you can get data from that node by using the `RETURN` clause.
    * `(m:MANUFACTURER)<-[:HAS_A]-(sp:SOFTWARE_PRODUCT)` <br>
    * `(sp:SOFTWARE_PRODUCT)<-[:HAS_A]-(sv:SOFTWARE_VERSION)` <br>
    * `(sv:SOFTWARE_VERSION)<-[:HAS_A]-(sr:SOFTWARE_RELEASE)` <br>
    * `(sr:SOFTWARE_RELEASE)-[:HAS_A]->(se:SOFTWARE_EDITION)` <br>
         
       `MATCH (m:MANUFACTURER)<-[:HAS_A]-(sp:SOFTWARE_PRODUCT)<-[:HAS_A]-(sv:SOFTWARE_VERSION)<-[:HAS_A]-(sr:SOFTWARE_RELEASE)-[:HAS_A]->(se:SOFTWARE_EDITION)` <br>

    3. Add the `WHERE` clause to filter the manufacturer attribute for "Oracle".<br>
      `WHERE m.manufacturer = "Oracle"` <br>
    4. Return data by using the aliases that are assigned to the nodes in the `MATCH` statement.<br>
       `RETURN m.manufacturer, sp.product, sv.version, sr.release, se.edition` <br>
    5. Limit the number of results that are returned by using the `LIMIT` clause. <br>
       `LIMIT 2` <br>

    Here's the complete query: <br>
    <br>
     `MATCH (m:MANUFACTURER)<-[:HAS_A]-(sp:SOFTWARE_PRODUCT)<-[:HAS_A]-(sv:SOFTWARE_VERSION)<-[:HAS_A]-(sr:SOFTWARE_RELEASE)-[:HAS_A]->(se:SOFTWARE_EDITION) <br>
      WHERE m.manufacturer = "Oracle"` <br>
     `RETURN m.manufacturer, sp.product, sv.version, sr.release, se.edition` <br>
     `LIMIT 2` <br>  <br>

    
    Note the relationship direction in the Technopedia graph that shows the nodes and relationships. <br>
    ![API Image](/images/relat_overview.png)<br>&nbsp; <br>
   

    The following result sample represents output from the query:<br>
    <br>
    ![API Image](/images/manu_to_se.png) <br> &nbsp;
   
  <br>  

   When you include relationships in  MATCH statements, you must use the relationship direction in the graph diagram.
   {: .warning}

  <br>
  <b>Query Intent:</b> To get data for software editions, and include the release, verison, and product information.<br>

  1. To get the required information, you start with the software edition and then add relationships to the software release, software version,     and software product nodes.<br>
  2. Use MATCH to select the software edtion node and then create relationships to the other nodes.<br>
      `MATCH (e:SOFTWARE_EDITION)`
  3. Add the release, version, and product nodes by adding relationships.<br>
      `MATCH (e:SOFTWARE_EDITION)<-[:HAS_A]-(r:SOFTWARE_RELEASE)-[:HAS_A]->(v:SOFTWARE_VERSION)-[:HAS_A]->(p:SOFTWARE_PRODUCT)`  
  4. Add an alias to each node in the query that you want to get data from.<br>
  5. To return the data that you need, use the Return clause to refer to the specific aliases.<br>
      `RETURN r,e,v,p`
  <br>
  In this query example, you return software editions in Technopedia that include release, verison, and product information. <br>

  `MATCH (e:SOFTWARE_EDITION)<-[:HAS_A]-(r:SOFTWARE_RELEASE)-[:HAS_A]->(v:SOFTWARE_VERSION)-[:HAS_A]->(p:SOFTWARE_PRODUCT) RETURN r,e,v,p LIMIT 1`<br>

  <br>
  The following image shows a single result that shows all attributes for edition, release, version and product:<br>
  <br>
  ![API Image](/images/4byattrib.png) <br> &nbsp;
  



  <br>
   
  <b>Query Intent:</b> Get software editions and include the release, verison, product, and manufacturer.<br>
  <br>
  In this query example, you get data for software editions in Technopedia, and include the release, version, product, and manufacturer data for each edition that is listed. This example is an extension of the previous example where we add manufacturer data but we only return one attribute from each of the five nodes. You return a single attribute by appending the alias to that attribute folloiwng the `RETURN` clause, for example, `RETURN e.edition` to return the edition attribute only.  <br>

  `MATCH (e:SOFTWARE_EDITION)<-[:HAS_A]-(r:SOFTWARE_RELEASE)-[:HAS_A]->(v:SOFTWARE_VERSION)-[:HAS_A]->(p:SOFTWARE_PRODUCT)-[:HAS_A]->(m:MANUFACTURER) 
  RETURN e.edition,r.release,v.version,p.product, m.manufacturer LIMIT 3`<br>
  <br>
  The following results are a sample of the output from the query:<br>
  <br>
  ![API Image](/images/edtomanu.png) <br> &nbsp;
  
  To get information about a relationship that has attributes, we can assign it an alias for later reference. 
  The  alias is placed in front of the colon that precedes the relationship:<br>
  `-[anyAlias:Relationship_name]->(node)` <br>
  <br>
  Here's an example: <br>
  `MATCH (:SOFTWARE_RELEASE)-[h:HAS_A {end_date: "2013-12-10 00:00:00"}]->(:SUPPORT_STAGE) RETURN h`  

  <br>
  <b>Query Intent:</b> To get product name for a software edition named "Black".<br>

  1. To get the required information, you start with the software edition and then add a relationship to the software product because you want to return the product name.<br>
  2. Use `MATCH` to select the software edtion node, and then you specify the edition attribute inside the curly braces. <br>
     `MATCH (SOFTWARE_EDITION {edition:\ 'Black'})`     
  3. Add a relationship from software editon to the software product node, and add an alias to the software product node. <br>
     `-[:HAS_A]->(sfw_prod:SOFTWARE_PRODUCT)` 
  4. Add an alias to each node in the query that you want to get data from.<br>
  5. To return the product name data that you need, use the Return clause to refer the alias that you assigned to the product node.<br>
      `RETURN sv.product`
  <br>
  Here's the complete query:\
  `MATCH (:SOFTWARE_EDITION {edition:\ 'Black'})-[:HAS_A]-(sv:SOFTWARE_PRODUCT) RETURN sv.product`
  In this query example, you return the product name for the software edition named 'Black'. <br>

 `"results": [ `<br>
       ` {`<br>
           ` "sv.product": "Need for Speed Most Wanted"` <br>
       ` }`<br>
  
 
  The following `MATCH` query examples show variations in constructions that use relationships and other conditions. To try out a query example, you append the `MATCH` statement to the following `/tql` endpoint and make a GET request from a API client or use cURL. <br>
  <br>
  `https://v6-1.technopedia.com/tql?q=<MATCH Statement>`
  
left_code_blocks:
  - code_block: |-
      MATCH (n:SOFTWARE_RELEASE)-[:HAS_A]->(:SOFTWARE_VERSION)-[:HAS_A]->(sp:SOFTWARE_PRODUCT)-[:HAS_A]->(m:MANUFACTURER)<-[:HAS_A]-(:CPU_MODEL) 
      WHERE m.manufacturer CONTAINS "TEL" 
      RETURN n.release, sp.product, m.manufacturer 
      LIMIT 5
      
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
    
  - code_block: |-
      MATCH (m:MANUFACTURER)<-[:HAS_A]-(sp:SOFTWARE_PRODUCT)<-[:HAS_A]-(sv:SOFTWARE_VERSION)<-[:HAS_A]-(sr:SOFTWARE_RELEASE)-[:HAS_A]->(se:SOFTWARE_EDITION) 
      WHERE m.manufacturer = "Oracle" 
      RETURN m.manufacturer, sp.product, sv.version, sr.release, se.edition 
      LIMIT 5

      RESPONSE SAMPLE

      {
        "results": [
            {
                    
                "m.manufacturer": "Oracle",
                "se.edition": "Web",
                "sp.product": "AutoVue",
                "sr.release": "AutoVue",
                "sv.version": "21.0"
            },
            {
                "m.manufacturer": "Oracle",
                "se.edition": "Desktop",
                "sp.product": "AutoVue",
                "sr.release": "AutoVue",
                "sv.version": "21.0"
            },
            {
                "m.manufacturer": "Oracle",
                "se.edition": "Web",
                "sp.product": "AutoVue",
                "sr.release": "AutoVue",
                "sv.version": "15.0"
            },
            {
                "m.manufacturer": "Oracle",
                "se.edition": "Desktop",
                "sp.product": "AutoVue",
                "sr.release": "AutoVue",
                "sv.version": "15.0"
            },
            {
                "m.manufacturer": "Oracle",
                "se.edition": "Web",
                "sp.product": "AutoVue",
                "sr.release": "AutoVue",
                "sv.version": "15.1"
            }
        ]
      {  
    title: Example two
    language: javascript

  - code_block: |-
      MATCH (s:SOFTWARE_PRODUCT) 
      WHERE s.product = "Office" OR s.product="HealthMatics" 
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
      RETURN n.release, sp.product LIMIT 5

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
      curl -G -H "Authorization: Bearer b93477a9-057b-4878-a16b93477a9-057b-4878-a16f-d7f7d1f27a7af-d7f7d1f27a7a" "https://v6-1.technopedia.com/tql" --data-urlencode' "q=MATCH (n:SOFTWARE_RELEASE) WHERE n.modified_at = "2017-05-26 13:59:45" RETURN n LIMIT 5

            
    title: cURL
    language: bash

    

right_code_blocks:
  - code_block: |2
      
      MATCH Node and Attribute Examples:
      __________________________________
      
      MATCH (alias1.NODE) RETURN alias1 
      MATCH (s:SOFTWARE_PRODUCT) RETURN s
      
      MATCH (alias.NODE) RETURN alias.attribute
      MATCH (s:SOFTWARE_PRODUCT) RETURN s.product 
      MATCH (s:SOFTWARE_PRODUCT) RETURN s.technopedia_id
      MATCH (s:SOFTWARE_PRODUCT) RETURN s.technopedia_id, s.product

      MATCH (s:SOFTWARE_PRODUCT) RETURN s.technopedia_id, s.is_suite    
 
      MATCH Relationship Examples:
      ____________________________
       
      MATCH (s:NODEx)-[:PART_OF]->(t:NODEy) RETURN s, t

      MATCH (sp:SOFTWARE_PRODUCT)<-[:HAS_A]-(sv:SOFTWARE_VERSION) RETURN sp, sv

      MATCH (s:SOFTWARE_EDITION)-[:HAS_A]->(p:SOFTWARE_PRODUCT) RETURN s, p

      MATCH (e:SOFTWARE_EDITION)<-[x:HAS_A]-(r:SOFTWARE_RELEASE) RETURN e, r

      MATCH (e:SOFTWARE_EDITION)<-[x:HAS_A]-(r:SOFTWARE_PRODUCT)-[HAS_A]->(m:MANUFACTURER) RETURN e, r, m





      
           
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
      Return distinct records only, which do not show duplicates.

      MATCH (s:SOFTWARE_PRODUCT) WHERE s.product = "Microsoft Exchange Server Monitor" RETURN DISTINCT s 
      
      CONTAINS
      Use the CONTAINS clause to return results when an attribute word value is matched. 

      MATCH (s:SOFTWARE_PRODUCT) WHERE s.product CONTAINS "Microsoft" RETURN s 

      AS
      Return output parameter as another name. 

      MATCH (n:SOFTWARE_EDITION) RETURN n.edition as ED, n.modified_at as MOD

      ORDER BY ascending (ASC) or decending (DESC) order
      Return list of products in descending order.
      
      MATCH (n:SOFTWARE_PRODUCT) RETURN n.product ORDER BY n.product DESC 

      Operators =, <>, >, <, >=, <=
    title: TQL Clauses and examples
    language: text
---