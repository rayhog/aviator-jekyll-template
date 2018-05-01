---
title: Authentication
position: 1.1
parameters:
  - name:
    content:
content_markdown: |-
  ## You need to be authenticated for all API requests. You can generate an API key
  in your developer dashboard. 
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

  {: .error}
left_code_blocks:
  - code_block: |-
      curl -G -H "Authorization: Bearer <Your_API_Key>"
      "https://v6.technopedia.com/<endpoint>" --data-urlencode "<query>"
    title: REQUEST EXAMPLE
    language: javascript
right_code_blocks:
  - code_block: |2-
       $.get("http://api.myapp.com/books/", { "token": "YOUR_APP_KEY"}, function(data) {
         alert(data);
       });
    title: JQuery
    language: javascript
  - code_block: ' curl http://api.myapp.com/books?token=YOUR_APP_KEY'
    title: Curl
    language: bash
---