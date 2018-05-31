---
title: Manufacturer
position: 2.1
type: 
description: The manufacturer is the creator of the product and in relationships the manufacturer is referred as HAS_A, for example, Microsoft is the manufacturer of, or `HAS_A` a software product called Microsoft Word, and Adobe is the manufacturer of, or `HAS_A` software product called Adobe Photoshop.
content_markdown: |-
  The manufacturer node has many attributes; the following attributes are popular attributes: 
  * `manufacturer` provides the name of the manufacturer.
  * `Technopedia_id` provides a unique ID.
  * `cat_manufacturer_id` provides the ID of the manfacturer.
  <br>
 
  The manufacturer has relationships to other nodes. The following MATCH query returns information about the manufactuer called Microsoft. 


  `MATCH (a:MANUFACTURER) WHERE a.manufacturer = "Microsoft" RETURN a`
  {: .info}

  The following diagram shows the the manufacturer node and nodes that are one hop away.

  ![API Image](/images/manu.PNG){:class="img-responsive"} <br>
  
    
left_code_blocks:
  - code_block: |-
      curl -G -H "Authorization: Bearer b93477a9-057b-4878-a16b93477a9-057b-4878-a16f-d7f7d1f27a7af-d7f7d1f27a7a" "https://v6.technopedia.com/tql" --data-urlencode' "q=MATCH (h:MANUFACTURER) RETURN h.manufacturer"
    title: cURL Examples
    language: bash


  - code_block: >-
      MATCH (n:SOFTWARE_RELEASE) RETURN n.cat_sw_release_id, n.release_url n.ga_date


      RESPONSE SAMPLE

      {
          
          }
    title: Example 1
    language: javascript
  - code_block: |-
      MATCH (n:SOFTWARE_RELEASE) -[:RELEASE_OF]->(SOFTWARE_PRODUCT) RETURN n.cat_sw_release_id LIMIT 1

      RESPONSE SAMPLE
      {
          
        }
    title: Example 2
    language: javascript

  - code_block: |-
      MATCH (n:n:MANUFACTURER) -[:RELEASE_OF]->(SOFTWARE_PRODUCT) RETURN n.cat_sw_release_id LIMIT 1

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

