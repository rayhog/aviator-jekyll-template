---
image: /images/NodeAndRel.png
title: Getting Started 
position: 1.04
description: 
content_markdown: >-
  You retrieve data from the Technopedia database by using the `/tql` endpoint.<br>
  Get set up with an API key, learn about the requirements to access data, and try some sample HTTP GET requests.
  
  
  Your Technopedia subscription determines your level of access to Technopedia data outside of the core Technopedia data.
    {: .warning}
  
  #### Get an API key<br>
     
  Before you can get data from data from the Technopedia database, you must get an API key from Flexera Technopedia support.
  The API key authorizes you to access the data that you are permitted to access with your subscription.

    
    
  #### Making HTTP Requests to Technopedia<br>

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

  For the TQL endpoint, you provide a TQL MATCH statement, which is a query that queries at least one node in Technopedia. Attributes and relationships are optional parameters in the query. <br>
  Here's an example of the syntax with a query example:<br>
  <br>
  `https://v6-1.technopedia.com/tql?q=<MATCH statement>`<br>

  `https://v6-1.technopedia.com/tql?q=MATCH (a:HARDWARE_MODEL) RETURN a.model` <br>

  
  #### Authentication<br>
  
  ###### The Technopedia Version 6.1 API uses OAuth for authentication. <br> 
  To authenticate in a new session, you pass the API key in the request header. The API key is provided by Flexera Technopedia support. <br>
  <br>
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
  
  #### Try out some of the following queries by making a HTTP GET request:

  <br>
   * Return twenty software products. <br>
  <br>
    `https://v6-1.technopedia.com/tql?q=MATCH (s:SOFTWARE_PRODUCT) RETURN s LIMIT 20` <br>
  <br>
   * Return fifteen hardware models. <br>
  <br>
  `https://v6-1.technopedia.com/tql?q=MATCH (e:HARDWARE_MODEL) RETURN e LIMIT 15` <br>
  <br>
   *  Return 10 manufacturers. <br>
  <br>
     `https://v6-1.technopedia.com/tql?q=MATCH (u:MANUFACTURER) RETURN u LIMIT 10` <br>
   <br>
   *  Return 10 software products that contain Microsoft in their name. <br>
  <br>
  `https://v6-1.technopedia.com/tql?q=MATCH (s:SOFTWARE_PRODUCT) WHERE s.product  CONTAINS "Microsoft" RETURN s.product LIMIT 10` <br>
  <br>
   *  Return up to three software editions named Enterprise Developer with their Technopedia IDs. <br>
  <br>
  `https://v6-1.technopedia.com/tql?q=MATCH (s:SOFTWARE_EDITION) WHERE s.edition = "Enterprise Developer" RETURN s.edition, s.technopedia_id LIMIT 3` <br>
  

  
  Tip: You can view Technopedia IDs by querying a node, for example, `MATCH (alias:NODE) RETURN alias`

  {: .warning}

  <br>
  Learn to write TQL queries by using the [Technopedia query language](../#documentationtql104)




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