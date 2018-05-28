---
title: TQL
position: 1.05
type:
description: >-
  The Technopedia query language (TQL) is used with the TQL endpoint to query data in the Technopedia database. TQL is the graph-query language that you use to query the database. The graph database stores connections between nodes as first-class citizens so it doesn't have to compute relationships at query time, which makes it more efficient than a relational database.
content_markdown: >-
  ###### TQL is a declarative query language that allows you to specify what data you want to retrieve by using the query language to query nodes and relationships in the Technopedia database.


  #### Get started with TQL<br>

  To make a query with TQL, you must use a MATCH statement, which is like Select statement in SQL. You add the MATCH statement as a query parameter to the TQL endpoint.<br>
  For example, `https://v6.technopedia.com/tql?q=MATCH <query_parameters>`
  <br>
  
  The TQL MATCH statement returns results from one or more nodes and relationships that are specified in the query. Typically, the data results are returned in key-value pairs, in a format that resembles the format in the following key-pair value:
  <br>
   
  {"Manufacturer": "Microsoft"}
   
  <br>

  The following diagram is an example of how Nodes and Relationships are connected:
  <br>
  

  ![API Image](/images/NodeAndRel.png)<br>&nbsp;
  <br>  
  To get data from a specific node or relationship, you use an alias or variable that you append to the node or relationship. That alias is bound to that node or relationship so you can use that alias in the Return clause of the MATCH query to get specific data from that node or alias.
  `Match (myalias:node)-[another_alias:RELATIONSHIP]`
  <br>

  #### Building a MATCH query<br>
  <br>
  
  To create a MATCH statement you must identify the location of your information and use the following guide to help you to build your query:

   1	Select the Nodes that you want to use in your query.<br>
   2	Identify the node attributes that store the information you require.<br>
   3	Select relationships to connect nodes that hold the data that you require.<br>
   4	Write your MATCH statement<br>
  <br>
  ##### 
  Here’s some examples:
  <br>
  <b>Objective:</b> To find software that is manufactured by Adobe

left_code_blocks:
  - code_block: |
      MATCH (n:SOFTWARE_RELEASE) RETURN n.cat_sw_release_id, n.ga_date

      RESPONSE SAMPLE
      {
          "keys": [
            "n.cat_sw_release_id",
            "n.ga_date"
          ],
          "length": 2,
          "_fields": [
            {
              "low": 55725913,
              "high": 0
            },
            "Not Available"
          ],
          "_fieldLookup": {
            "n.cat_sw_release_id": 0,
            "n.ga_date": 1
          }

    title: Example 1
    language: javascript
  - code_block: >-
      MATCH (n:SOFTWARE_RELEASE) RETURN n.cat_sw_release_id, n.release_url n.ga_date


      RESPONSE SAMPLE

      {
          "keys": [
            "n.cat_sw_release_id",
            "n.release_url",
            "n.ga_date"
          ],
          "length": 3,
          "_fields": [
            {
              "low": 10427852,
              "high": 0
            },
            "www.nntest.com/files/import/Solutions%20Catalog%20Data.xls",
            "Not Available"
          ],
          "_fieldLookup": {
            "n.cat_sw_release_id": 0,
            "n.release_url": 1,
            "n.ga_date": 2
          }
    title: Example 2
    language: javascript
  - code_block: |-
      MATCH (n:SOFTWARE_RELEASE) -[:RELEASE_OF]->(SOFTWARE_PRODUCT) RETURN n.cat_sw_release_id LIMIT 1

      RESPONSE SAMPLE
      {
          "keys": [
            "n.cat_sw_release_id"
          ],
          "length": 1,
          "_fields": [
            {
              "low": 55725913,
              "high": 0
            }
          ],
          "_fieldLookup": {
            "n.cat_sw_release_id": 0
          }
        }
    title: Example 3
    language: javascript
  - code_block: 'curl http://sampleapi.readme.com/orders?key=YOUR_APP_KEY'
    title: Example 4
    language: bash
  - code_block: 'curl http://sampleapi.readme.com/orders?key=YOUR_APP_KEY'
    title: Example 5
    language: bash
  - code_block: 'curl http://sampleapi.readme.com/orders?key=YOUR_APP_KEY'
    title: cURL
    language: bash
    
right_code_blocks:
  - code_block: |-
      [
        {
          "id": 1,
          "title": "The Hunger Games",
          "score": 4.5,
          "dateAdded": "12/12/2013"
        },
        {
          "id": 1,
          "title": "The Hunger Games",
          "score": 4.7,
          "dateAdded": "15/12/2013"
        },
      ]
    title: Response
    language: json
  - code_block: |-
      {
        "error": true,
        "message": "Invalid offset"
      }
    title: Error
    language: json
right_code_blocks:
  - code_block: |2
      
      MATCH (alias1.NODE) RETURN alias1 
      MATCH (n:SOFTWARE_PRODUCT) RETURN n 

      MATCH (alias.NODE) RETURN alias.attribute 
      MATCH (n:SOFTWARE_PRODUCT) RETURN n.name 

      MATCH (alias2.NODE) RETURN alias2 
      MATCH (s:SOFTWARE_RELEASE) RETURN s 

      MATCH (alias.NODE) RETURN alias.attribute 
      MATCH (s:SOFTWARE_RELEASE) RETURN s.version 
      
      MATCH (alias3.NODE) RETURN alias3 
      MATCH (n:MANUFACTURER) RETURN n

      MATCH (alias4.NODE) RETURN alias4.attribute
      MATCH (n:MANUFACTURER) RETURN n.manufactuer 

           
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
      Operators =, <>, >, <, >=, <=
    title: TQL Keywords
    language: bash
---