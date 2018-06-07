---
image: /images/NodeAndRel.png
title: Getting Started
position: 1.02
description: 
content_markdown: >-
  ###### Access Technopedia data by using the Technopedia API.
  Technopedia endpoints enable to you to use the Technopedia ID endpoint to get product information for a specific product by specifying the Technopedia ID, and to use the Technopedia query language (TQL) with the TQL endpoint to form custom queries that query data from the Technopedia database.<br>
  <br>
  <br>
  
  #### Making API Requests to Technopedia<br>

  You can use cURL or a third-party API client to get data from the Technopedia database.
  The base URL for all API queries is `https://v6-1.technopedia.com/`
  <br>
  
    Note: Typically, cURL is preinstalled on Mac and Linux computers, and Windows users must install cURL. <br>
    {: .info}

  For example, the following example is a cURL query: <br>
  `curl -G -H "Authorization: Bearer <API_KEY>" https://v6-1.technopedia.com/tql" --data-urlencode "q=MATCH (s:SOFTWARE_PRODUCT) RETURN s.product"`<br>
  
  <br>
  Examples of API GET requests, and MATCH statements which are used to form the query statment are provided throughout this guide. 
  
  You can also use a third-party API client, such as Postman to send API requests as shown in the following image.<br>
  <br>
  ![API Image](/images/bearer_token.png){: .img-responsive}<br>
    
 
  #### Get your API key<br>

  Before you can get data from data from the Technopedia database, you must get an API key from Flexera Technopedia support.<br>

  #### Methods<br>

  You can only make API GET requests to the Technopedia database.<br>

  #### Parameters<br>

  For the Technopedia-id endpoint, you provide the Technopedia ID parameter.<br>
  For the TQL endpoint, you provide MATCH statements with parameters that specify nodes, attributes, and relationships between nodes which are optional.
  
  #### Authentication<br>
  
  ###### The Technopedia Version 6 API uses OAuth for authentication. To authenticate in a new session, you pass the API key in the request header. The API key is provided by Flexera Technopedia support.

  In the following examples, an API key example is used in a cURL example and in the Postman API client. The key `Bearer b93477a9-054b-4878-a16f-d7f5d1f27a7a` is used in both examples.
  <br>
  <br>
  The following example shows the API key in a cURL request:<br>
  <br>
  `curl -G -H "Authorization: Bearer b93477a9-054b-4878-a16f-d7f5d1f27a7a" "https://v6.technopedia.com/tql" --data-urlencode "q=MATCH (s:SOFTWARE_PRODUCT) RETURN s.name"`<br>
  
   {: .success}

  Use the `--data-urlencode` option in the cURL command to encode spaces.<br>
  
  
  The following example shows where you add the API key to the header of a GET request in the Postman API client:<br>
  <br>
  ![API Image](/images/bearer_token.png){: .img-responsive}<br>



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
        
    title: Authentication
    language: bash
---