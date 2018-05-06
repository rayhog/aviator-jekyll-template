---
title: TQL 
position: 1.03
type: 
description: TQL (Technopedia Query Language) is the graph query language that you use to get data from Technpedia.
content_markdown: |-
  Deletes a book in your collection.
  The query returns software that includes 'Excel'. This is query is case
  sensitive.
  {: .success}

  The query returns software that includes 'Excel'. This is query is case
  sensitive.

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

