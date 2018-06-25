---
image: /![API Image](/images/logo.png){:class="img-responsive"}
title: Overview
position: 1.01
description: 
content_markdown: |-
  Technopedia version 6.1 API enables cloud-based access to asset data in Technopedia, which you use to manage your IT assets with respect to risk, control, governance, costs and business compliance. Technopedia's structured database catalog categorizes more than 170,000 software releases and 200,000 hardware models, and includes data from mulitiple business categories.
  <br>   
  
    
  #### You use the API to retrieve asset data in JSON format

  The Technopedia version 6.1 API provides you with read access to the Technopedia database by using an API GET request to retreive asset data.
    * To get access to the Technopedia database, all you require is an API key that you get from Flexera technial support.<br>
    * You make an API GET request by using cURL or an API client to the `/tql` or `/technopedia-id` endpoint. <br>
      The `/tql` endpoint requires a Technopedia query languge query statement to describe the data that you want to retrieve.<br>
    * Data is returned in JSON format. <br>

  The following query example is an API GET request that uses the TQL endpoint to retrieve software product names from Technopedia. <br>
  <br>
  `GET:` `https://v6-1.technopedia.com/tql?=MATCH (n:SOFTWARE_PRODUCT) RETURN n.product` <br>

  The query returns software product names.<br>

  The following image shows a result for one software product.
  <br>
  
  ![API Image](/images/ov_ex.png){: .img-responsive}
  <br>  
    
  #### Technopedia data structure

  In the Technopedia graph database, data categories are represented by nodes and the node attributes contain more specific data.
  Nodes represent entities such as software or hardware, which are somewhat equivalent to a records classification that stores a specific data category. 
  <br>
  <br>
 
  The following diagram shows an overview of the Technopedia API endpoints, and some nodes and relationships in the Technopedia database.
  
  <br>
  
  ![API Image](/images/V6api.png){: .img-responsive}
  
 

left_code_blocks:
  - code_block: |-
      GET:  https://v6-1.technopedia.com/tql?q=MATCH <Query Parameters>
      GET:  https://v6-1.technopedia.com/tql?MATCH (sft_prod:SOFTWARE_PRODUCT) RETURN sft_prod LIMIT 2

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
              "sft_prod.url": "http://www.microsoft.com/Downloads/details.aspx?familyid=E565FC92-D5F6-4F5F-8713-4DD1C90DE19F&displaylang=en"
          }
        ]
      {  

      GET:  https://v6-1.technopedia.com/technopedia-id/<technopedia_id>
      GET:  https://v6-1.technopedia.com/technopedia-id/4d35ec28-0f16-4787-acca-885679265b59
      
    title: API Query Examples
    language: text
right_code_blocks:
  - code_block: |2
      https://v6-1.technopedia.com/tql
      https://v6-1.technopedia.com/technopedia-id/
      
      


    title: Technopedia Endpoints
    language: text
  
---