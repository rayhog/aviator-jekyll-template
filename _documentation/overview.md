---
image: /![API Image](/images/logo.png){:class="img-responsive"}
title: Overview
position: 1.01
description: 
content_markdown: |-
  Technopedia version 6.1 API enables access to asset data in Technopedia, which you use to manage your IT assets with respect to risk, control, governance, costs and business compliance. 
  <br>
  Technopedia's database catalog categorizes more than 170,000 software releases and 200,000 hardware models, and includes data from mulitiple business categories.
  <br>   
  
  #### How to use this documentation
  <br>
  The objective of this API documentation is to enable you use the API and Technopedia query language (TQL) to retrieve data from the Technopedia database.
  The first section of this documentation is about getting started with the API and creating queries by using TQL.
  The API section references several nodes in Technopedia and provides mulitiple examples about retrieving data.

  To learn about using the API and TQL, read this overview, and then take the following steps:
  
   1. Get an API key and try out some queries. <br>
     [Get started](../#documentationgetting_started102)
   2. Learn about Technopedia nodes and graph database. <br>
     [Technopedia data](../#documentationNodes_Rel)
   3. Learn about writng queries with TQL. <br>
     [Technopedia queries](../#documentationtql104)
  
  To retrieve data from Technopedia, the most common practice you'll undertake is to write TQL queries to use with the API.
  

  #### Making API GET requests to retrieve asset data 
  <br>
  The Technopedia version 6.1 API provides you with read access to the Technopedia database by using an API GET request to retreive asset data.
    * To get access to the Technopedia database, all you require is an API key that you get from Flexera technical support.<br>
    * You make an API GET request to the `/tql` endpoint, which requires a TQL query statement to describe the data that you want to retrieve.<br>
    * Data is returned as key-value pairs in JSON format. <br>

  The following query example is an API GET request that uses the `/tql` endpoint to retrieve software product names from Technopedia. <br>
  <br>
  `GET:` `https://v6-1.technopedia.com/tql?=MATCH (n:SOFTWARE_PRODUCT) RETURN n.product` <br>

  The query returns software product names.<br>
  The following image shows data for one software product.
  <br>
  
  ![API Image](/images/ov_ex.png){: .img-responsive}
  <br>  
  <br>
    
  #### Technopedia Graph Database
  <br>
  The Technopedia graph database is a data model that consists of a collection of nodes that are connected by relationships.
  <br>

   * Nodes represent entities that are equivalent to a records classification, which store a specific data category such as hardware or software. 
   * Nodes have attributes that represent and store data as key-value pairs.
   * Nodes connect to other nodes by relationships.
 
  The following diagram shows the `/tql` endpoint that is used to query nodes in the Technopedia database.
  
  <br>
  
  ![API Image](/images/V6api.png){: .img-responsive}
  
 

left_code_blocks:
  - code_block: |-
      GET:  https://v6-1.technopedia.com/tql?q=MATCH <Query Parameters>

      EXAMPLE:

      GET:  https://v6-1.technopedia.com/tql?q=MATCH (sft_prod:SOFTWARE_PRODUCT) RETURN sft_prod LIMIT 2

      Returns data based on the Technopedia query language that starts with MATCH


      RESPONSE SAMPLE

      {
      "results": [
          {
              "sft_prod.alias": null,
              "sft_prod.component": null,
              "sft_prod.created_at": "2017-05-19 10:24:33",
              "sft_prod.desupported_flag": null,
              "sft_prod.discontinued_flag": null,
              "sft_prod.family": null,
              "sft_prod.is_suite": "FALSE",
              "sft_prod.modified_at": "2017-06-01 13:50:16",
              "sft_prod.product": "e1ns.output",
              "sft_prod.technopedia_id": "408dd3bb-c935-444e-b756-c7d431a589f7",
              "sft_prod.url": "http://www.plato.de/e1nsoutput-687.html"
          },
          {
              "sft_prod.alias": null,
              "sft_prod.component": null,
              "sft_prod.created_at": "2008-03-25 22:07:06",
              "sft_prod.desupported_flag": null,
              "sft_prod.discontinued_flag": null,
              "sft_prod.family": "Windows Live",
              "sft_prod.is_suite": "FALSE",
              "sft_prod.modified_at": "2011-03-21 17:47:50",
              "sft_prod.product": "ID Web Authentication Software Development Kit (SDK)",
              "sft_prod.technopedia_id": "359e53c0-6cda-4e3b-aaa1-2b05537ca718",
              "sft_prod.url": "http://www.microsoft.com/Downloads/details.aspx?
               familyid=E565FC92-D5F6-4F5F-8713-4DD1C90DE19F&displaylang=en" 
          }
        ]
      {  

    title: TQL Endpoint
    language: text
    
right_code_blocks:
  - code_block: |2
      Technopedia query language (tql) endpoint

      https://v6-1.technopedia.com/tql


            
      


    title: Technopedia Endpoints
    language: text
  
---