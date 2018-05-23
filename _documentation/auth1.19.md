---
image: /![API Image](/images/logo.png){:class="img-responsive"}
title: Authentication
position: 1.03
description: You must authenticate before you can get data by using the API.
content_markdown: |-
  ###### The Technopedia Version 6 API uses OAuth for authentication. To authenticate in a new session, you pass the API key in the request header. The API key is provided by Flexera Technopedia support.

  In the following examples, an API key example is used in a cURL example and with the Posman API client. The API key example: `Bearer b93477a9-054b-4878-a16f-d7f5d1f27a7a` is used in both examples.
  <br>
  The following example shows where you add the API key in a cURL request:<br>
  <br>
  `curl -G -H "Authorization: Bearer b93477a9-054b-4878-a16f-d7f5d1f27a7a" "https://v6.technopedia.com/tql" --data-urlencode "q=MATCH (s:SOFTWARE_PRODUCT) RETURN s.title"`<br>
  

   {: .success}

  Use the `--data-urlencode` option in the cURL command to encode spaces.<br>
  
  The following example shows how you add the API key to the header of a GET request in Postman:<br>
  <br>
  ![API Image](/images/bearer_token.png){: .img-responsive}<br>
left_code_blocks:
  - code_block: |-
      curl -G -H "Authorization: Bearer b93477a9-054b-4878-a16f-d7f5d1f27a7a" "https://v6.technopedia.com/tql" --data-urlencode "q=MATCH (s:SOFTWARE_PRODUCT) RETURN s.title"

      curl -G -H "Authorization: Bearer b93477a9-054b-4878-a16f-d7f5d1f27a7a" "https://v6.technopedia.com/tql" --data-urlencode "q=MATCH (n:SOFTWARE_PRODUCT) WHERE n.title = "PDF Converter" RETURN n
    title: cURL examples
    language: bash
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