---
title: Manufacturer
position: 2.1
type: 
description: The manufacturer is the creator of the product and in relationships the manufacturer is referered as VENDOR_OF, for example Microsoft is the vendor of Microsoft Word, or Adobe is the vendor of Adobe Photoshop.
content_markdown: |-
  The manufacturer nodes has many attributes; examples of popular attributes are Title, Technopedia_id, and cat_manufacturer_id.
  The manufacturer has relationships to other nodes.


  The query returns software that includes 'Excel'. The query is case sensitive.
  
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
  - code_block: |2
      Technopedia_id
      Cat_Manufacturer_ID
      Title
      Legal
      Revenue
      Symbol
      Tier
      Website
      Description
      Known_as
      Phone
      Fax
      City
      Country
      Email
      Publicly_Traded
      State
      Street
      ZIP
      Revenue_Date
      Fiscal_End_Date
      Profits_Per_Year
      Profits_Date
      Employees
      Employees_Date
      Created_at
      Modified_at
    title: Manufacturer Attributes
    language: bash
  - code_block: |2-
      (Manufacturer)-[:VENDOR_OF]->(SOFTWARE_PRODUCT)
    title: Relationships
    language: bash
---

