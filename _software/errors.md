---
title: ERRORS
position: 1.3
parameters:
  - name:
    content:
content_markdown: |-
  | Code | Name | Description |
  | --- | --- | --- |
  | 200 | OK | Success |
  | 201 | Created | Creation Successful |
  | 400 | Bad Request | Unable to process the request Test2 |
  | 403 | Forbidden | You're not authorized |
### Temp Image
 Returns a specific book from your collection.<br> 
  ![API Image](/images/apiEcon.png){:class="img-responsive"} <br>

  All errors will return JSON in the following format:
left_code_blocks:
  - code_block: |-
      {
        "error": true,
        "message": "error message here"
      }
    title: Response
    language: json
---