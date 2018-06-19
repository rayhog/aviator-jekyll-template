---
title: Software Edition
position: 1.5
type: 
description: 
content_markdown: |-
  The software edition node provides edition data from the Technopedia database.
  Software edition represents the version of the product, such as Standard, Premium, or other version name for the product. The edition is helpful for identifying versions of a product.
  <br>

  The following query returns data for the software edition that is named 'Black': <br>
  
  `MATCH (e:SOFTWARE_EDITION {edition: 'Black'}) RETURN e`
  
  <br>
  The following example is a query to find an edition that is named: "Advanced Partitioning Option":<br>
  <br>
  `MATCH (s.SOFTWARE_PRODUCT)<-[:HAS_A]-(n:SOFTWARE_EDITION) WHERE n.edition = "Advanced Partitioning Option" RETURN n`
  <br>
  
  The following diagram shows attributes for the sofware editon node, and its related software nodes.
  
  <br>
  ![API Image](/images/sw_edition.png){:class="img-responsive"} <br>

  #### Query Examples <br>
    
  To use the `MATCH` statements in the following examples, you append the `MATCH` statement to the following `/tql` endpoint and make a GET request from a API client or use cURL. <br>
  <br>
  `https://v6-1.technopedia.com/tql?q=<MATCH Statement>`
left_code_blocks:
  - code_block: |
      MATCH (n:SOFTWARE_EDITION) 
      RETURN n.edition AS EDITION, n.modified_at AS MODIFIED 
      LIMIT 8

      RESPONSE SAMPLE

      {
        "results": [
            {
                "EDITION": "Server",
                "MODIFIED": "2017-04-20 14:49:12"
            },
            {
                "EDITION": "Personal",
                "MODIFIED": "2011-03-11 11:16:48"
            },
            {
                "EDITION": "Black",
                "MODIFIED": "2017-05-10 17:45:22"
            },
            {
                "EDITION": "Deluxe",
                "MODIFIED": "2017-09-28 11:34:11"
            },
            {
                "EDITION": "Java for Education",
                "MODIFIED": "2016-09-12 09:48:23"
            },
            {
                "EDITION": "Standard",
                "MODIFIED": "2012-08-06 18:11:55"
            },
            {
                "EDITION": "Lite",
                "MODIFIED": "2015-10-23 14:31:44"
            },
            {
                "EDITION": "Enterprise",
                "MODIFIED": "2017-03-20 11:44:49"
            }
        ]
      {  

    title: Example one
    language: javascript
  - code_block: >-
      MATCH (e:SOFTWARE_EDITION {edition: 'Server'}) 
      RETURN e 
      
      
      RESPONSE SAMPLE

      {
        "results": [
            {
                "e.created_at": "2014-02-21 16:14:21",
                "e.desupported_flag": null,
                "e.edition": "Server",
                "e.modified_at": "2014-02-21 16:14:21",
                "e.order": 2,
                "e.technopedia_id": "36caabb2-af3a-4591-9466-d854bad6cf3f",
                "e.url": "http://www.ni.com/datafinder/"
            },
            {
                "e.created_at": "2011-01-06 11:39:43",
                "e.desupported_flag": null,
                "e.edition": "Server",
                "e.modified_at": "2016-08-19 15:39:58",
                "e.order": 2,
                "e.technopedia_id": "672fb073-536b-4a6b-9279-9a646bb9dcbb",
                "e.url": "http://www.crestron.com/downloads/pdf/product_misc/gs_sw-roomvw-server.pdf"
            }
       ]
      {  
    title: Example two
    language: javascript
  - code_block: |-
      MATCH (p:SOFTWARE_PRODUCT)<-[:HAS_A]-(s:SOFTWARE_EDITION) 
      WHERE s.order = 2 AND s.edition = "Enterprise Developer" 
      RETURN p.product, s.edition, s.order 
      LIMIT 3
      
      RESPONSE SAMPLE

      {
        "results": [
            {
                "p.product": "JViews",
                "s.edition": "Enterprise Developer",
                "s.order": 2
            },
            {
                "p.product": "Unwired Platform",
                "s.edition": "Enterprise Developer",
                "s.order": 2
            },
            {
                "p.product": "Elixir",
                "s.edition": "Enterprise Developer",
                "s.order": 2
            }
        ]
      {  
    title: Example three
    language: javascript

  - code_block: |-
      MATCH (s:SOFTWARE_EDITION) 
      WHERE s.order = 2 AND s.edition = "Enterprise Developer" 
      RETURN s.edition, s.order 
      LIMIT 3

      RESPONSE SAMPLE

      {
        "results": [
            {
                "s.edition": "Enterprise Developer",
                "s.order": 2
            },
            {
                "s.edition": "Enterprise Developer",
                "s.order": 2
            },
            {
                "s.edition": "Enterprise Developer",
                "s.order": 2
            }
        ]
      {  
    title: Example four
    language: javascript

  - code_block: |-
     MATCH (n:SOFTWARE_EDITION) -[:HAS_A]->(u:SOFTWARE_PRODUCT) 
     RETURN u.product AS Product, n.edition AS Edition, n.order AS Edition_order  
     LIMIT 6

      RESPONSE SAMPLE

      {
        "results": [
            {
                "Edition": "Server",
                "Edition_order": 5,
                "Product": "Windows NT"
            },
            {
                "Edition": "Personal",
                "Edition_order": 1,
                "Product": "Web Intelligence"
            },
            {
                "Edition": "Black",
                "Edition_order": 1,
                "Product": "Need for Speed Most Wanted"
            },
            {
                "Edition": "Deluxe",
                "Edition_order": 2,
                "Product": "ClientCare Contact Center"
            },
            {
                "Edition": "Java for Education",
                "Edition_order": 2,
                "Product": "ArcExplorer"
            },
            {
                "Edition": "Standard",
                "Edition_order": 1,
                "Product": "IT Change Manager"
            }
        ]
      {  
    title: Example five
    language: javascript

  - code_block: |-
      curl -G -H "Authorization: Bearer b93477a9-057b-4878-a16b93477a9-057b-4878-a16f-d7f7d1f27a7af-d7f7d1f27a7a" "https://v6.technopedia.com/tql" --data-urlencode' "q=MATCH (h:SOFTWARE_EDITION) RETURN h.edition"

      
    title: cURL
    language: bash
right_code_blocks:
  - code_block: |2
      technopedia_id
      edition
      edition_desupported_flag
      order
      url
      created_at
      modified_at

    title: Software Edition Attributes
    language: bash
  - code_block: |2-
      (SOFTWARE_EDITION)-[:HAS_A]->(SOFTWARE_PRODUCT)

      (SOFTWARE_EDITION)<-[:HAS_A]-(SOFTWARE_RELEASE)

      (SOFTWARE_EDITION)-[:HAS_A]->(SOFTWARE_PRODUCT)
      
      (SOFTWARE_EDITION)<-[:HAS_A]->(SOFTWARE_RELEASE)-[:HAS_A]->(SUPPORT_STAGE)

      (SOFTWARE_EDITION)<-[:HAS_A]->(SOFTWARE_RELEASE)-[:HAS_A]->(COMPATIBLE_PLATFORM)

      

      



    title: Relationships
    language: bash
---

