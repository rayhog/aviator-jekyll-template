---
title: Authentication
position: 1.01
description: >-
  Your must Authenticate your query to get data back from Technopedia. 
parameters:
  - name:
    content:
content_markdown: |-
  ## You need to be authenticated for all API requests. You can generate an API key   in your developer dashboard. 
  Add the API key to all requests as a GET parameter.<br>
  ![API Image](/images/logo.png){:class="img-responsive"} <br>
  The Technopedia Version 6.0 API uses OAuth for authentication. To
  authenticate a session, pass your key in the request header. Your API key
  should have been provided to you by Flexera support. If you do not have a key
  please contact support.

# Returns a specific book from your collection.<br> 
  ![API Image](/images/node_table2.png){:class="img-responsive"} <br>
  This is a very precise query.
  You must &nbsp;this API key to authorise.

All errors will return JSON in the following format:
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
---