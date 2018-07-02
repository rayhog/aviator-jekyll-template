---
image: /![API Image](/images/logo.png){:class="img-responsive"}
title: Overview
position: 1.01
description: 
content_markdown: |-
  Technopedia version 6.1 API enables access to asset data in Technopedia, which you use to manage your IT assets with respect to risk, control, governance, costs and business compliance. <br>
  <br>
  Technopedia is the world’s largest and most comprehensive repository of enterprise software and hardware data.
  <br>   
 

  #### Retrieve asset data by making HTTP GET requests
  <br>
  The Technopedia version 6.1 API provides you with read access to the Technopedia database by using an HTTP GET request to retreive asset data.
    * To get access to the Technopedia database, all you require is an API key that you get from Flexera technical support.<br>
    * You make an HTTP GET request to the `/tql` endpoint, which requires a TQL query statement to describe the data that you want to retrieve.<br>
    * Data is returned as key-value pairs in JSON format. <br>

  The following query example is an HTTP GET request that uses the `/tql` endpoint to retrieve software product names from Technopedia. <br>
  <br>
  `GET:` `https://v6-1.technopedia.com/tql?=MATCH (n:SOFTWARE_PRODUCT) RETURN n.product` <br>

  
  The following image shows data that is returned for one software product.
  <br>
  
  ![API Image](/images/ov_ex.png){: .img-responsive}
  <br>  
  <br>
    
  #### Technopedia Graph Database
  <br>
  The Technopedia graph database is a data model that consists of <br>
  
   * Nodes represent data categories such as software product or hardware.
  <br>
   * Attributes belong to nodes and they store data as key-value pairs.<br>
  <br>
   * Relationships are used to define connections between nodes that you use when you query multiple nodes.<br>
  <br>
  * The following diagram shows the endpoint that is used to query nodes in the Technopedia database.
  
  <br>
  
  ![API Image](/images/V6api.png){: .img-responsive}

  #### How to use this documentation

  <br>
  The objective of this API documentation is to enable you use the API and Technopedia query language (TQL) to retrieve data from the Technopedia database. 

  Do the following tasks to start retrieveing the data you need from Technopedia:
  
   1. Get an API key and try out some TQL query examples. <br>
     [Get started](../#documentationgetting_started102)
   2. Learn about the nodes and relationships that you use in Technopedia queries. <br>
     [Technopedia data](../#documentationNodes_Rel)
   3. Learn to write queries with TQL. <br>
     [Technopedia queries](../#documentationtql104)
  
 

left_code_blocks:
  - code_block: |-
      GET:  https://v6-1.technopedia.com/tql?q=MATCH <Query Parameters>

      EXAMPLE:

      GET:  https://v6-1.technopedia.com/tql?q=MATCH (sft_prod:SOFTWARE_PRODUCT) RETURN sft_prod LIMIT 2

      This query example returns data for two software products in Technopedia.


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