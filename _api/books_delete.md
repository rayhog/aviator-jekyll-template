---
title: CVE 
position: 1.5
type: 
description: Matches a CVE from Technopedia XXXX
parameters:
  - Category: Any category for the Software Category list
    Attribute: Any attribute from the Software Attributes list
    Requirement: The category is optional
content_markdown: |-
  This API deletes a book in your collection.
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

