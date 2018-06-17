---
image: /images/NodeAndRel.png
title: Getting Started
position: 1.02
description: 
content_markdown: >-
  ###### Access Technopedia data by using the Technopedia API.
  You retrieve data from the Technopedia database by using the TQL endpoint or the TID endpoint:<br>

  Use the Technopedia ID (`/tid`) endpoint to get information about an entity in the graph, such as product information or a node attribute by specifying the Technopedia ID.<br>
  <br>
  Use the Technopedia query language (TQL) with the TQL endpoint (`/tql`) to create custom queries that you use to query the Technopedia database.<br>
  <br>

  Your Technopedia subscription determines your level of access to Technopedia data outside of the core Technopedia data.
  
    {: .info}
  
  #### Get an API key<br>
     
  Before you can get data from data from the Technopedia database, you must get an API key from Flexera Technopedia support.
  The API key authorizes you to access the data that you are permitted to access with your subscription.

    
    
  #### Making API Requests to Technopedia<br>

  You can use cURL or a third-party API client to get data from the Technopedia database.<br>
  The base URL for all API queries is <br>
  `https://v6-1.technopedia.com/`
  <br>
  
    Typically, cURL is preinstalled on Mac and Linux computers, and Windows users must install cURL. <br>
    {: .info}

  For example, the following example is a cURL query: <br>
  `curl -G -H "Authorization: Bearer <API_KEY>" https://v6-1.technopedia.com/tql" --data-urlencode "q=MATCH (s:SOFTWARE_PRODUCT) RETURN s.product"`<br>
  
   
  You can also use a third-party API client, such as Postman to make API requests as shown in the following image.<br>
  <br>
  ![API Image](/images/bearer_token.png){: .img-responsive}<br>
    
 
  #### Methods<br>

  You can only make API GET requests to the Technopedia database.<br>

  #### Parameters<br>

  For the Technopedia-id endpoint, you provide the Technopedia ID parameter.<br>
  For example; `https://v6-1.technopedia.com/technopedia-id/<Technopedia ID>`<br>
  <br>
  For the TQL endpoint, you provide MATCH statements with parameters that specify nodes, attributes, and relationships between nodes which are optional. <br>
  `https://v6-1.technopedia.com/tql?q=<TQL_query>`

  
  #### Authentication<br>
  
  ###### The Technopedia Version 6.1 API uses OAuth for authentication. To authenticate in a new session, you pass the API key in the request header. <br> 
  The API key is provided by Flexera Technopedia support.

  In the following examples, an API key example is used with cURL and in the Postman API client. <br>
  The key `Bearer b93477a9-054b-4878-a16f-d7f5d1f27a7a` is used in both examples.
  <br>
  <br>
  The following example shows the API key in a cURL request:<br>
  <br>
  `curl -G -H "Authorization: Bearer b93477a9-054b-4878-a16f-d7f5d1f27a7a" "https://v6.technopedia.com/tql" --data-urlencode "q=MATCH (s:SOFTWARE_PRODUCT) RETURN s.product"`<br>
  
   {: .success}

  Use the `--data-urlencode` option in the cURL command to encode spaces.<br>
  
  
  The following example shows where you add the API key to the header of a GET request in the Postman API client:<br>
  <br>
  ![API Image](/images/bearer_token.png){: .img-responsive}<br>



left_code_blocks:
  - code_block: |-
      curl -G -H "Authorization: Bearer <API_KEY>" https://v6-1.technopedia.com/tql" --data-urlencode "q=MATCH (s:SOFTWARE_PRODUCT) RETURN s.product"

      curl -G -H "Authorization: Bearer b93477a9-054b-4878-a16f-d7fdd1f27a7a" "https://v6-1.technopedia.com/tql" --data-urlencode "q=MATCH (s:SOFTWARE_PRODUCT) RETURN s.product"
        
    title: cURL authentication examples
    language: bash
    
right_code_blocks:
  - code_block: |2-
      curl -G -H "Authorization: Bearer <API_KEY>" https://v6-1.technopedia.com/<endpoint>

      Example:
      curl -G -H "Authorization: Bearer b93477a9-054b-4878-a16f-d7f5d17a7a" "https://v6-1.technopedia.com/<endpoint>
        
    title: Authentication
    language: bash
---