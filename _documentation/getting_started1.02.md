---
image: /images/NodeAndRel.png
title: Getting Started
position: 1.02
description: 
content_markdown: >-
  ###### Technopedia endpoints enable to you to use the Technopedia ID endpoint to get product information for a specific product by specifying the Technopedia ID, and to use the Technopedia query language (TQL) with the TQL endpoint to query data from the Technopedia database.<br> 

  You can only make GET API requests. Examples of API GET requests and MATCH statements are provided throughout this guide. 
  Typically Mac and Linux users have cURL installed, and Windows users most likely have to install cURL. You can also use a third-party API client, such as Postman to send API requests.
   
  ###### The base URL for all API queries is: https://v6.technopedia.com/ <br>
  
 
  

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