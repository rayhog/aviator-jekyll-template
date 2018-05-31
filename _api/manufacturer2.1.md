---
title: Manufacturer
position: 2.1
type: 
description: The manufacturer is the creator of the product and in relationships the manufacturer is referred as HAS_A, for example, Microsoft is the manufacturer of, or `HAS_A` a software product called Microsoft Word, and Adobe is the manufacturer of, or `HAS_A` software product called Adobe Photoshop.
content_markdown: |-
  The manufacturer node has many attributes; the following attributes are popular attributes: 
  * `manufacturer` provides the name of the manufacturer.
  * `technopedia_id` provides a unique ID.
  * `description` provides a description of the manfacturer.
  <br>
 
  The manufacturer has relationships to other nodes. The following MATCH query returns information about the manufactuer called Microsoft. 


  `MATCH (a:MANUFACTURER) WHERE a.manufacturer = "Microsoft" RETURN a`
  {: .info}

  The following diagram shows the the manufacturer node and its connections to software, haredware, and CPU.

  ![API Image](/images/manu.PNG){:class="img-responsive"} <br>
  
    
left_code_blocks:
  - code_block: |-
      curl -G -H "Authorization: Bearer b93477a9-057b-4878-a16b93477a9-057b-4878-a16f-d7f7d1f27a7af-d7f7d1f27a7a" "https://v6.technopedia.com/tql" --data-urlencode' "q=MATCH (h:MANUFACTURER) RETURN h.manufacturer"
    title: cURL Examples
    language: bash


  - code_block: >-
      MATCH (h:MANUFACTURER) RETURN h.manufacturer


      RESPONSE SAMPLE

      {
          
          }
    title: Example 1
    language: javascript
  - code_block: |-
      MATCH (h:MANUFACTURER) RETURN h.manufacturer

      RESPONSE SAMPLE
      {
          
        }
    title: Example 2
    language: javascript

  - code_block: |-
      MATCH (n:MANUFACTURER)<-[:HAS_A]-(w:SOFTWARE_PRODUCT)-[BELONGS_TO]->(v:CATEGORY_2) RETURN n, w, v

      RESPONSE SAMPLE
      {
          
        }
    title: Example 3
    language: javascript

  - code_block: |-
      MATCH (n:MANUFACTURER)-[:HAS_A]->(p:SOFTWARE_PRODUCT)-[:HAS_A]->(my_alias:SOFTWARE_VERSION) RETURN n, p, my_alias

      RESPONSE SAMPLE
      {
          
        }
    title: Example 4
    language: javascript

  - code_block: |-
      curl -G -H "Authorization: Bearer b93477a9-057b-4878-a16b93477a9-057b-4878-a16f-d7f7d1f27a7af-d7f7d1f27a7a" "https://v6.technopedia.com/tql" --data-urlencode' "q=MATCH (h:MANUFACTURER) RETURN h.manufacturer"

      
    title: Example 5
    language: bash
right_code_blocks:
  - code_block: |2
      technopedia_id
      cat_manufacturer_id
      manufacturer
      legal
      revenue
      symbol
      tier
      website
      description
      known_as
      phone
      fax
      city
      country
      email
      publicly_traded
      state
      street
      zip
      revenue_date
      fiscal_end_date
      profits_per_year
      profits_date
      employees
      employees_date
      created_at
      modified_at



    title: Manufacturer Attributes
    language: bash
  - code_block: |2-
      (MANUFACTURER)-[:HAS_A]->(SOFTWARE_PRODUCT)

      (MANUFACTURER)-[:HAS_A]->(CPU)

      (MANUFACTURER)-[:HAS_A]->(HARWARE_PRODUCT)

      
    title: Relationships
    language: bash
---

