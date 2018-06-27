---
image: /images/NodeAndRel.png
title: Getting Started
position: 1.02
description: 
content_markdown: >-
  You retrieve data from the Technopedia database by using the `/tql` endpoint.<br>
  
  
  Your Technopedia subscription determines your level of access to Technopedia data outside of the core Technopedia data.
    {: .warning}
  
  #### Get an API key<br>
     
  Before you can get data from data from the Technopedia database, you must get an API key from Flexera Technopedia support.
  The API key authorizes you to access the data that you are permitted to access with your subscription.

    
    
  #### Making API Requests to Technopedia<br>

  You can use cURL or a third-party API client to get data from the Technopedia database.<br>
  <br>
  The base URL for all API queries is <br>
  `https://v6-1.technopedia.com/`
  <br>
  
    Typically, cURL is preinstalled on Mac and Linux computers, and Windows users must install cURL. <br>
    {: .warning}

  For example, the following example is a cURL query: <br>
  `curl -G -H "Authorization: Bearer <API_KEY>" https://v6-1.technopedia.com/tql" --data-urlencode "q=MATCH (s:SOFTWARE_PRODUCT) RETURN s.product"`<br>
  
   
  You can also use a third-party API client, such as Postman to make API requests as shown in the following image.<br>
  <br>
  ![API Image](/images/bearer_token.png){: .img-responsive}<br>
    
 

  #### Parameters<br>

  For the TQL endpoint, you provide a TQL MATCH statements that specifies at least one node in the query. Attributes and relationships between nodes are optional parameters in the query. <br>

  `https://v6-1.technopedia.com/tql?q=<TQL_query>`<br>

  For example, `https://v6-1.technopedia.com/tql?q=MATCH (a:HARDWARE_MODEL) RETURN a.model`

  
  #### Authentication<br>
  
  ###### The Technopedia Version 6.1 API uses OAuth for authentication. To authenticate in a new session, you pass the API key in the request header. <br> 
  The API key is provided by Flexera Technopedia support.

  In the following examples, an API key example is used with cURL and in the Postman API client. <br>
  <br>
  The key `Bearer b93477a9-054b-4878-a16f-d7f5d1f27a7a` is used in both of the following examples.
  <br>
  The following example shows the API key in a cURL request:<br>
  <br>
  `curl -G -H "Authorization: Bearer b93477a9-054b-4878-a16f-d7f5d1f27a7a" "https://v6.technopedia.com/tql" --data-urlencode "q=MATCH (s:SOFTWARE_PRODUCT) RETURN s.product"`<br>
  
   {: .success}

  Use the `--data-urlencode` option in the cURL command to encode spaces.<br>
  
  
  The following example shows where you add the API key to the header of a GET request in the Postman API client:<br>
  <br>
  ![API Image](/images/bearer_token.png){: .img-responsive}<br>


  #### 
  GET request by using the Technopedia query language (TQL)

  ######
  The main method for acessing information in Technopedia is by using the API with the Technopedia query language (TQL) to query nodes, relationships, and attributes in the Technopedia database.<br>
  <br>
  GET `https://v6-1.technopedia.com/tql?q=<TQL_query>`<br>
  <br>
  
  #### Try out some queries by making a GET request

  <br>
  Try the following query that returns 10 software products that contain Microsoft in their name. <br>
  <br>
  `https://v6-1.technopedia.com/tql?q=MATCH (s:SOFTWARE_PRODUCT) WHERE s.product  CONTAINS "Microsoft" Return s.product LIMIT 10` <br>
  <br>
  Try the following query that returns software editions named Enterprise Developer with their Technopedia IDs. <br>
  <br>
  `https://v6-1.technopedia.com/tql?q=MATCH (s:SOFTWARE_EDITION) WHERE s.edition = "Enterprise Developer" RETURN s.edition, s.technopedia_id LIMIT 3` <br>
  

  
  Tip: You can view Technopedia IDs by querying a node, for example, `MATCH (alias:NODE) RETURN alias`

  {: .warning}

  <br>
  To learn more about Technopedia nodes and writing TQL queries, take the following steps: <br>
   1. Learn about Technopedia nodes and graph database. <br>
      [Technopedia data structure](../#documentationNodes_Rel) <br>
   2. Learn about writing TQL queries. <br>
      [Technopedia query language](../#documentationtql104)




left_code_blocks:
  - code_block: |-
      curl -G -H "Authorization: Bearer <API_KEY>" https://v6-1.technopedia.com/tql" --data-urlencode "q=MATCH (s:SOFTWARE_PRODUCT) RETURN s.product"

      curl -G -H "Authorization: Bearer b93477a9-054b-4878-a16f-d7fdd1f27a7a" "https://v6-1.technopedia.com/tql" --data-urlencode "q=MATCH (s:SOFTWARE_PRODUCT) RETURN s.product"
        
    title: cURL authentication examples
    language: text
    
right_code_blocks:
  - code_block: |2-
      curl -G -H "Authorization: Bearer <API_KEY>" https://v6-1.technopedia.com/<endpoint>

      Example:
      curl -G -H "Authorization: Bearer b93477a9-054b-4878-a16f-d7f5d17a7a" "https://v6-1.technopedia.com/<endpoint>
        
    title: Authentication
    language: text
---