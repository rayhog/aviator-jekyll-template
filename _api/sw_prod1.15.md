---
title: Software Product
position: 1.15
type:
description: >-
  In the following query example, you get data from Technopedia that contains PDF Converter in the name of the software product name.
content_markdown: >-
  `MATCH (n:SOFTWARE_PRODUCT) WHERE n.name = "PDF Converter" RETURN n` 
  
  {: .success} 
  
  
left_code_blocks:
  - code_block: |-
      MATCH QUERY EXAMPLES:
      
      MATCH (n:SOFTWARE_PRODUCT) RETURN n.name

      MATCH (n:SOFTWARE_PRODUCT) RETURN n.cat_sw_product_id
      
    title: MATCH Queries
    language: bash
right_code_blocks:
  - code_block: |2
      technopedia_id
      cat_sw_product_id
      name
      family
      component
      alias
      is_suite
      product_desupported_flag
      product_discontinued_flag
      product_url
      created_at
      modified_at



      

      
    title: Software Product Attributes
    language: bash
  - code_block: |2-
      (SOFTWARE_PRODUCT)<-[:EDITION_OF]-(SOFTWARE_EDITION)
      (SOFTWARE_PRODUCT)<-[:VENDOR_OF]-(MANUFACTURER)
      (SOFTWARE_PRODUCT)-[:CATEGORY]->(CATEGORY_2)
      

    title: Relationships
    language: bash
---

