---
title: Manufacturer
position: 2.1
type: 
description: The manufacturer is the creator of the prouduct and in relationships the manufacturer is referered to as VENDOR_OF, for example Microsoft is the vendor of Microsoft Word.
content_markdown: |-
  Deletes a book in your collection.
  The query returns software that includes 'Excel'. This is query is case
  sensitive.

  

   {: .success}

  This API is being continuously developed and changes are implemented on a regular basis.
  Throughout this document inline examples are provided that show examples of how to make requests to the API. The cURL examples should work on most systems. Mac and Linux users typically have cURL installed already, although Windows users will likely need to install cURL.
  
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
  - code_block: |2
      Technopedia_id
      Edition
      Edition_Desupported_Flag
      Edition_Order
      URL
      Created_At
      Modified_At
    title: Software Product Attributes
    language: bash
  - code_block: |2-
      [:VENDOR_OF]->(Manufacturer)
    title: Relationships
    language: bash
---

