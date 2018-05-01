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

left_code_blocks:
  - code_block: |-
      $.get("http://api.myapp.com/books/3", {
        token: "YOUR_APP_KEY",
      }, function(data) {
        alert(data);
      });
    title: jQuery
    language: javascript
right_code_blocks:
  - code_block: |2-
      {
        "id": 3,
        "title": "The Book Thief",
        "score": 4.3,
        "dateAdded": "5/1/2015"
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