---
title: SOFTWARE
position: 1.5
type: delete
description: Deletes a book
parameters:
  - name:
    content:
content_markdown: |-
  Deletes a book in your collection.

   Returns a specific book from your collection.<br> 
  ![API Image](/images/node_table.png){:class="img-responsive"} <br>
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

