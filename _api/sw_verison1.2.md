---
title: Software Version
position: 1.2
type: 
description: >-
  Two nodes represent software versions. The Software major version represents the major version attributes and the software version represents the attributes that are associated with child versions of the parent major version.
content_markdown: >-
  The query returns software that includes 'Excel'. This is query is case sensitive.
  
  Gets software version information

  MATCH (a:SOFTWARE_VERSION) RETURN a.version

  {: .success} 

  
  <br>

  ### Software Major Version
  <br>
  
  MATCH (a:SOFTWARE_MAJOR_VERSION) RETURN a.version

  {: .success} 

  ###### The node that represents the major version of software is `SOFTWARE_MAJOR_VERSION`.
  Software versioning is used to categorize the unique states of software as it is developed and released. The version identifier might be a word, or a number, or inlcude both. For example, version 1.0 is often used to represent the initial release of a software product.


  
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
      VERSION ATTRIBUTES
      Technopedia_id
      Edition
      Edition_Desupported_Flag
      Edition_Order
      URL
      Created_At
      Modified_At

      MAJOR VERSION ATTRIBUTES
      Version
      Version Order

    title: Software Version Attributes
    language: bash
  - code_block: |2-
      (SOFTWARE_VERSION)<-[:RELEASE_OF]-(SOFTWARE_RELEASE)
      (SOFTWARE_VERSION)<-[:MAJOR_VERSION_OF]-(SOFTWARE_MAJOR_VERSION)
    title: Relationships
    language: bash
---

