---
image: /images/NodeAndRel.png
title: Getting Started
position: 1.02
content_markdown: >-
  ###### Welcome to the API documentation page about getting started.<br>
  Technopedia endpoints enable to you to use the Technopedia ID endpoint to get product information for a specific product by specifying the Technopedia ID, and to use the Technopedia query language (TQL) with the TQL endpoint to query data from the Technopedia database.<br> 
  You can only make GET API requests. Examples of API GET requests and MATCH statements are provided throughout this guide. 
  Mac and Linux users typically have cURL installed already, although Windows users will likely need to install cURL.
   
  ###### The base URL for all queries by using the API is: https://v6.technopedia.com/ <br>
  The Technopedia Version 6 API uses OAuth for authentication. To authenticate in a new session, you pass the API key in the request header. The API key is provided by Flexera Technopedia support.

  Here’s some examples of using the following fake API key by using cURL and Postman.<br>
  `curl -G -H "Authorization: Bearer b93477a9-054b-4878-a16f-d7f5d1f27a7a" "https://v6.technopedia.com/tql" --data-urlencode "q=MATCH (s:SOFTWARE) RETURN s.title"`<br>
  

   {: .success}

  To avoid issues with whitespaces in https Get requests, use the `--data-urlencode` option in the cURL command to encode spaces.<br><br>
  
  
  Here’s an example of adding the API key to the header in Postman:<br>
  <br>

  ![API Image](/images/bearer_token.png){: .img-responsive}<br>

 
  

left_code_blocks:
  - code_block: |-
      {
        "error": true,
        "message": "error message here"
      }
    title: Response
    language: json
    right_code_blocks:
  - code_block: "{\r\n  \"error\": true,\r\n  \"message\": \"error message here\"\r\n}\r\n\r\n{\r\n    \"message\": \"Internal Server Error\",\r\n    \"request-id\": \"4f6bfd02-e367-4a61-90c7-832d0226dd8c\"\r\n}"
    title: Error Examples
    language: json
left_code_blocks:
  - code_block: |-
      $.ajax({
        "url": "http://api.myapp.com/books/3",
        "type": "DELETE",
        "data": {
          "token": "YOUR_APP_KEY"
        },
        "success": function(data) {
          alert(data);
        }
      });
    title: jQuery
    language: javascript
right_code_blocks:
  - code_block: |2-
      {
        "id": 3,
        "status": "deleted"
      }
    title: Response
    language: json
  - code_block: |2-
      {
        "error": true,
        "message": "Book doesn't exist"
      }
    title: Error
    language: json
---