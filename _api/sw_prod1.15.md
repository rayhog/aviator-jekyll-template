---
title: Software Product
position: 1.15
type:
description: >-
  In the following query example, you get data from Technopedia that contains PDF Converter in the name of the software product name.
content_markdown: >-
  `MATCH (n:SOFTWARE_PRODUCT) WHERE n.product = "PDF Converter" RETURN n` 
  
  {: .success} 
  
  The following diagram shows the software nodes and relationships.

   ![API Image](/images/NodeAndRel.png){: .img-responsive}<br>&nbsp;
  
left_code_blocks:
  - code_block: |
      MATCH (n:SOFTWARE_PRODUCT) WHERE n.product = "PDF Converter" RETURN n

      RESPONSE SAMPLE
      {
         "results": [
        {
            "n.alias": null,
            "n.cat_sw_product_id": 29714096,
            "n.component": null,
            "n.created_at": "2012-08-08 14:49:44",
            "n.desupported_flag": null,
            "n.discontinued_flag": null,
            "n.family": null,
            "n.is_suite": "FALSE",
            "n.modified_at": "2015-12-05 18:44:59",
            "n.product": "PDF Converter",
            "n.technopedia_id": "273a39cf-3b86-4894-a437-956ebdebfb08",
            "n.url": "http://www.win7pdf.com/pdf-converter.html"
        },
        {
            "n.alias": null,
            "n.cat_sw_product_id": 524445392,
            "n.component": null,
            "n.created_at": "2018-01-24 10:03:20",
            "n.desupported_flag": null,
            "n.discontinued_flag": null,
            "n.family": null,
            "n.is_suite": "TRUE",
            "n.modified_at": "2018-01-24 10:03:21",
            "n.product": "PDF Converter",
            "n.technopedia_id": "0714fbe6-04e0-482c-9669-0475c5e1f8d3",
            "n.url": "http://www.mp4converter.net/pdf-converter-pro.html"
        }   
         

    title: Example one
    language: javascript
  - code_block: >-
      MATCH (s:SOFTWARE_PRODUCT) WHERE s.product = "Office" AND s.family = "HealthMatics"  RETURN s


      RESPONSE SAMPLE

      {
        "results": [
            {
                "m.manufacturer": "Immedia Internet Solutions",
                "s.created_at": "2015-03-03 16:51:26",
                "s.product": "ActionBars"
            }
        ]
      {  
    title: Example two
    language: javascript
  - code_block: |-
      MATCH (n:SOFTWARE_RELEASE) -[:RELEASE_OF]->(SOFTWARE_PRODUCT) RETURN n.cat_sw_release_id LIMIT 1

      RESPONSE SAMPLE

      {
        "results": [
            {
                "m.manufacturer": "Immedia Internet Solutions",
                "s.created_at": "2015-03-03 16:51:26",
                "s.product": "ActionBars"
            }
        ]
      {  
    title: Example three
    language: javascript

  - code_block: |-
      MATCH (n:SOFTWARE_RELEASE) -[:RELEASE_OF]->(SOFTWARE_PRODUCT) RETURN n.cat_sw_release_id LIMIT 1

      RESPONSE SAMPLE

      {
        "results": [
            {
                "m.manufacturer": "Immedia Internet Solutions",
                "s.created_at": "2015-03-03 16:51:26",
                "s.product": "ActionBars"
            }
        ]
      {  
    title: Example four
    language: javascript

  - code_block: |-
      MATCH (n:SOFTWARE_RELEASE) -[:RELEASE_OF]->(SOFTWARE_PRODUCT) RETURN n.cat_sw_release_id LIMIT 1

      RESPONSE SAMPLE

      {
        "results": [
            {
                "m.manufacturer": "Immedia Internet Solutions",
                "s.created_at": "2015-03-03 16:51:26",
                "s.product": "ActionBars"
            }
        ]
      {  
    title: Example five
    language: javascript

  - code_block: |-
      curl -G -H "Authorization: Bearer b93477a9-057b-4878-a16b93477a9-057b-4878-a16f-d7f7d1f27a7af-d7f7d1f27a7a" "https://v6.technopedia.com/tql" --data-urlencode' "q=MATCH (h:CPU) RETURN h.cores"

      
    title: cURL
    language: bash
    
right_code_blocks:
  - code_block: |2
      technopedia_id
      product
      family
      component
      is_suite
      product_desupported_flag
      product_discontinued_flag
      product_url
      created_at
      modified_at
      "alias"



      

      
    title: Software Product Attributes
    language: bash
  - code_block: |2-
      (SOFTWARE_PRODUCT)<-[:HAS_A]-(SOFTWARE_EDITION)

      (SOFTWARE_PRODUCT)-[:HAS_A]->(MANUFACTURER)

      (SOFTWARE_PRODUCT)-[:HAS_A]->(SOFTWARE_VERSION)
      
      (SOFTWARE_PRODUCT)-[:BELONGS_TO]->(CATEGORY_2)
      

    title: Relationships
    language: bash
---

