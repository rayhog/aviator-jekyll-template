---
title: Hardware Licensing
position: 2.1
type: 
description: Licensing information
parameters:
  - name:
    content:
content_markdown: |-
  Deletes a book in your collection.

  The query returns software that includes 'Excel'. This is query is case
  sensitive.

  {: .success}

  The query returns software that includes 'Excel'. This is query is case
  sensitive.

  {: .success}



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

