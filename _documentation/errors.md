---
title: API Codes
position: 1.2
content_markdown: |-
  ###### The following table shows the codes that are returned by the API
  Throughout this document we provide you with inline examples regarding how to perform requests to the API. The cURL examples should work on most systems. Mac and Linux users typically have cURL installed already, although Windows users will likely need to install cURL.
  
  | Code | Name | Description |
  | --- | --- | --- |
  | 200 | OK | Success |
  | 201 | Created | Creation Successful |
  | 400 | Bad Request | We could not process that action TEST2 |
  | 403 | Forbidden | We couldn't authenticate you |

  Throughout this document we provide you with inline examples regarding how to perform requests to the API. The cURL examples should work on most systems. Mac and Linux users typically have cURL installed already, although Windows users will likely need to install cURL.

  All errors will return JSON in the following format

  | Code | Name | Description |
  | --- | --- | --- |
  | 200 | OK | Success |
  | 201 | Created | Creation Successful |
  | 400 | Bad Request | We could not process that action TEST2 |
  | 403 | Forbidden | We couldn't authenticate you |
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
