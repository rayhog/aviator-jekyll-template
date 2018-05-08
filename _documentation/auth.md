---
image: /![API Image](/images/logo.png){:class="img-responsive"}
title: Authentication
position: 1.19
description: ### You must authenticate before you can get data with the API
content_markdown: |-
  ###### The Technopedia Version 6.0 API is hosted by Flexera, so no installation is required.
  ###### In this document we provide you with inline examples about sending requests to the API. The cURL examples should work on most systems. Mac and Linux users typically have cURL installed already, although Windows users will likely need to install cURL.
  ###### The Technopedia Version 6.0 API uses OAuth for authentication. To authenticate a session, pass your key in the request header. Your API key should have been provided to you by Flexera support. If you do not have a key please contact support.
  
  ###### All errors will return JSON in the following format
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