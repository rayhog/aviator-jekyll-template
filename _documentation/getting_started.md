---
title: Getting Started
position: 1.02
content_markdown: >-
  ![API Image](/images/logo.png){: .img-responsive}


  ###### Welcome to the API documentation page

  Here's an example image
  image: ![API Image](/images/allservices_diagram.png){: .img-responsive}

  ### This API document is designed for those interested in developing for the
  platform. Throughout this document we provide you with inline examples regarding how to perform requests to the API. The cURL examples should work on most systems. Mac and Linux users typically have cURL installed already, although Windows users will likely need to install cURL.

  ### This API is still under development and is a work in progress.
  Throughout this document we provide you with inline examples regarding how to perform requests to the API. The cURL examples should work on most systems. Mac and Linux users typically have cURL installed already, although Windows users will likely need to install cURL.


  ![API Image](/images/nodes_and_rel.png){: .img-responsive}<br>Here's another
  image: ![API Image](/images/allservices_diagram.png){: .img-responsive}


  ###### This API document is designed for those interested in developing for
  the platform.


  This API is still under development and is a work in progress.
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
right_code_blocks:
  - code_block: |-


      {
        "id": 3,
        "status": "deleted"
      }
    title: Test for image
    language: json
  - code_block: |-


      {
        "error": true,
        "message": "Book doesn't exist"
      }
      
    title: Error
    language: json
    image: ![API Image](/images/logo.png){:class="img-responsive"}
  - code_block: |-
  
      Here's another one
    title: Another one
    language: json
---