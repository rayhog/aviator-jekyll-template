---
title: Manufacturer
position: 2.1
type: 
description: The manufacturer is the creator of the product and in relationships the manufacturer is referred as `HAS_A`, for example, Microsoft is the manufacturer of, or it `HAS_A` a software product called Microsoft Word, and Adobe is the manufacturer of, or it `HAS_A` software product called Adobe Photoshop.
content_markdown: |-
  The manufacturer node has many attributes; the following attributes are popular attributes: 
  * `manufacturer` provides the name of the manufacturer.
  * `technopedia_id` provides a unique ID.
  * `description` provides a description of the manfacturer.
  <br>
 
  The manufacturer has relationships to other nodes. The following MATCH query returns information about the manufacturer called Microsoft. 


  `MATCH (a:MANUFACTURER) WHERE a.manufacturer = "Microsoft" RETURN a`
  {: .info}

  The following diagram shows the the manufacturer node and its connections to software, hardware, and CPU.

  ![API Image](/images/manu.png){:class="img-responsive"} <br>
  
    
left_code_blocks:
  - code_block: |-
      curl -G -H "Authorization: Bearer b93477a9-057b-4878-a16b93477a9-057b-4878-a16f-d7f7d1f27a7af-d7f7d1f27a7a" "https://v6.technopedia.com/tql" --data-urlencode' "q=MATCH (h:MANUFACTURER) RETURN h.manufacturer"
    title: cURL Examples
    language: bash


  - code_block: >-
      MATCH (h:MANUFACTURER) RETURN h.manufacturer


      RESPONSE SAMPLE

      {
        "results": [
          {
              "h.manufacturer": "Go Ahead Web"
          },
          {
              "h.manufacturer": "State Administration of Foreign Exchange"
          },
          {
              "h.manufacturer": "Callware Technologies"
          },
          {
              "h.manufacturer": "SoundID"
          },
          {
              "h.manufacturer": "Obian"
          },
          {
              "h.manufacturer": "AnalogX"
          }
      {    
    title: Example 1
    language: javascript
  - code_block: |-
      https://v6-1.technopedia.com/tql?q=MATCH (n:MANUFACTURER) RETURN n 

      RESPONSE SAMPLE
      {
        "results": [
        {
            "n.cat_manufacturer_id": 594345,
            "n.city": null,
            "n.country": null,
            "n.created_at": null,
            "n.description": null,
            "n.email": null,
            "n.employees": null,
            "n.employees_date": null,
            "n.fax": null,
            "n.fiscal_end_date": null,
            "n.known_as": null,
            "n.legal": "Corporation",
            "n.manufacturer": "Go Ahead Web",
            "n.modified_at": null,
            "n.phone": null,
            "n.profits_date": null,
            "n.profits_per_year": null,
            "n.publicly_traded": null,
            "n.revene_date": null,
            "n.revenue": null,
            "n.state": null,
            "n.street": null,
            "n.symbol": "Private",
            "n.technopedia_id": "513a9c99-608f-4b36-b9b6-3b53dfa85625",
            "n.tier": 3,
            "n.website": "http://www.goaheadweb.co.uk/",
            "n.zip": null
        },
          
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

