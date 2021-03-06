---
image: /![API Image](/images/logo.png){:class="img-responsive"}
title: Authentication
position: 4.5
description: You must authenticate before you can get data by using the API.
content_markdown: |-
  ###### The Technopedia Version 6 API uses OAuth for authentication. To authenticate in a new session, you pass the API key in the request header. The API key is provided by Flexera Technopedia support.

  In the following examples, an API key example is used in a cURL example and in the Postman API client. The key `Bearer b93477a9-054b-4878-a16f-d7f5d1f27a7a` is used in both examples.
  <br>
  <br>
  The following example shows the API key in a cURL request:<br>
  <br>
  `curl -G -H "Authorization: Bearer b93477a9-054b-4878-a16f-d7f5d1f27a7a" "https://v6.technopedia.com/tql" --data-urlencode "q=MATCH (s:SOFTWARE_PRODUCT) RETURN s.name"`<br>
  
   {: .success}

  Use the `--data-urlencode` option in the cURL command to encode spaces.<br>
  
  The following example shows where you add the API key to the header of a GET request in the Postman API client:<br>
  <br>
  ![API Image](/images/bearer_token.png){: .img-responsive}<br>

  <br>
  <br>
  #### HTTP Status Codes
  The following table shows the HTTP status codes that are returned by the API.

  | Code | Name | Description |
  | --- | --- | --- |
  | 200 | OK | Success |
  | 201 | Created | Creation Successful |
  | 400 | Bad Request | Request can't be processed |
  | 403 | Forbidden | Failed to authenticate |

  <br>
  <br>

left_code_blocks:
  - code_block: |-
      curl -G -H "Authorization: Bearer b93477a9-054b-4878-a16f-d7f5d1f27a7a" "https://v6.technopedia.com/tql" --data-urlencode "q=MATCH (s:SOFTWARE_PRODUCT) RETURN s.name"

      curl -G -H "Authorization: Bearer b93477a9-054b-4878-a16f-d7f5d1f27a7a" "https://v6.technopedia.com/tql" --data-urlencode "q=MATCH (n:SOFTWARE_PRODUCT) WHERE n.name = "PDF Converter" RETURN n
    title: cURL examples
    language: bash
  - code_block: |-
        GET: https://v6.technopedia.com/tql?q=MATCH (s:SOFTWARE_PRODUCT) RETURN s.product

        GET: https://v6.technopedia.com/tql?q=MATCH (n:SOFTWARE_PRODUCT) WHERE n.product = "PDF Converter" RETURN n
    title: GET request examples
    language: bash
right_code_blocks:
  - code_block: |2-
      {
        "id": 3,
        "status": "deleted"
      }



 






    title: Status codes
    language: json
  
---