---
title: Getting Started
position: 1.01
parameters:
  - name:
    content:
content_markdown: |-
  | Code | Name | Description |
  | --- | --- | --- |
  | 200 | OK | Success |
  | 201 | Created | Creation Successful |
  | 400 | Bad Request | We could not process that action TESTx |
  | 403 | Forbidden | We couldn't authenticate you |

You'll succeed if you do this.

  {: .success}


  Here's some useful information.

  {: .info}


  Something may not happen if you try and do this.

  {: .warning}


  Something bad will happen if you do this.

  {: .error}

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