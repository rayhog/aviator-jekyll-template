---
image: /images/NodeAndRel.png
title: Getting Started
position: 1.02
description: 
content_markdown: >-
  ###### Access Technopedia data by using the Technopedia API.
  Technopedia endpoints enable to you to use the Technopedia ID endpoint to get product information for a specific product by specifying the Technopedia ID, and to use the Technopedia query language (TQL) with the TQL endpoint to form custom queries that query data from the Technopedia database.<br>
  

  
  #### API Requests to Technopedia<br>

  You can use cURL or a third-party API client to get data from the Technopedia database.
  The base URL for all API queries is `https://v6-1.technopedia.com/`
  <br>
    Note: Typically, cURL is preinstalled on Mac and Linux computers, and Windows users most likely have to install cURL. <br>
    {: .info}
    
  For example, the following example is a cURL query: <br>
  `curl -G -H "Authorization: Bearer <API_KEY>" https://v6-1.technopedia.com/tql" --data-urlencode "q=MATCH (s:SOFTWARE_PRODUCT) RETURN s.title"`<br>
  
  <br>
  Examples of API GET requests, and MATCH statements which are used to form the query statment are provided throughout this guide. 
  
  You can also use a third-party API client, such as Postman to send API requests as shown in the following image.<br>
  <br>
  ![API Image](/images/bearer_token.png){: .img-responsive}<br>
    
 
  #### Get your API key<br>

  Before you can get data from data from the Technopedia database, you must get an API key from Flexera Technopedia support.<br>

  #### Method<br>

  You can only make API GET requests to the Technopedia database.<br>

  #### Parameters<br>

  For the Technopedia-id endpoint, you provide the Technopedia ID.<br>
  For the TQL endpoint, you provide MATCH statements with parameters that specify nodes, attributes, and relationships between nodes which are optional.


left_code_blocks:
  - code_block: |-
      curl -G -H "Authorization: Bearer <API_KEY>" https://v6-1.technopedia.com/tql" --data-urlencode "q=MATCH (s:SOFTWARE_PRODUCT) RETURN s.product"

      curl -G -H "Authorization: Bearer b93477a9-054b-4878-a16f-d7fdd1f27a7a" "https://v6-1.technopedia.com/tql" --data-urlencode "q=MATCH (s:SOFTWARE_PRODUCT) RETURN s.product"
        
    title: Authentication example
    language: bash
    
right_code_blocks:
  - code_block: |2-
      curl -G -H "Authorization: Bearer <API_KEY>" https://v6-1.technopedia.com/<endpoint>

      Example:

      curl -G -H "Authorization: Bearer b93477a9-054b-4878-a16f-d7f5d1f27a7a" "https://v6-1.technopedia.com/<endpoint>
        
    title: Authorization
    language: bash
---