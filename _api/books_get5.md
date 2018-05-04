---
title: Software Release
position: 1.5
type: 
description: Get Book
parameters:
  - name:
    content:
content_markdown: |-
  # Returns a specific book from your collection.<br>
  ## Returns a specific book from your collection.<br>
  ## Returns a specific book from your collection.<br>
  #### Returns a specific book from your collection.<br>
  ##### Returns a specific book from your collection.<br>
  ###### # Returns a specific book from your collection.<br> 
  ![API Image](/images/logo.png){:class="img-responsive"} <br>
  
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