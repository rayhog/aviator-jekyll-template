---
title: Authentication
position: 1.2
description: You must authenticate before you can get data with the API
parameters:
  - name:
    content:
content_markdown: |-
##### The Technopedia Version 6.0 API is hosted by Flexera, so no installation is required.
##### Throughout this document we provide you with inline examples regarding how to perform requests to the API. 
##### The cURL examples should work on most systems. Mac and Linux users typically have cURL installed already, although Windows users will likely need to install cURL.
The Technopedia Version 6.0 API uses OAuth for authentication. To authenticate a session, pass your key in the request header. Your API key should have been provided to you by Flexera support. If you do not have a key please contact support.

Do not share your API key with anyone else.


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