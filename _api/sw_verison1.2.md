---
title: Software Version
position: 1.2
type: 
description: >-
  Software versions are represented by two nodes. The Software major version represents the major version attributes and the software version represents the attributes that are associated with child versions of the parent major version. The relationship bewtween the nodes is `MAJOR_VERSION_OF` which point to `SOFTWARE_VERSION` from `SOFTWARE_MAJOR_VERSION`
content_markdown: >-
  Gets software version information
  <br>
  <br>
  

  `MATCH (a:SOFTWARE_VERSION) RETURN a.version`

  {: .success} 
  
  <br>

  ### Software Version Group
  
  ######
  The node that represents the major version of software is `SOFTWARE_GROUP_VERSION`.
  Software versioning is used to categorize the unique states of software as it is developed and released. The version identifier might be a word, or a number, or inlcude both. For example, version 1.0 is often used to represent the initial release of a software product.


  `MATCH (a:SOFTWARE_GROUP_VERSION) RETURN a.version`

  {: .success} 


  <br>
  


  
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
      technopedia_id
      cat_sw_version_id
      version
      version_patchlevel
      is_major
      version_order
      version_desupported_flag

      MAJOR VERSION GROUP
      Version
      cat_sw_version_group_id

    title: Software Version Attributes
    language: bash
  - code_block: |2-
      (SOFTWARE_VERSION)<-[:RELEASE_OF]-(SOFTWARE_RELEASE)
      (SOFTWARE_VERSION)<-[:MAJOR_VERSION_OF]-(to be determined)
    title: Relationships
    language: bash
---

