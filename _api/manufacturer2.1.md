---
title: Manufacturer
position: 2.1
type: 
description: The manufacturer is the creator of the product and in relationships the manufacturer is referered as VENDOR_OF, for example Microsoft is the vendor of Microsoft Word, or Adobe is the vendor of Adobe Photoshop.
content_markdown: |-
  The manufacturer nodes has many attributes; examples of popular attributes are Title, Technopedia_id, and cat_manufacturer_id.
  The manufacturer has relationships to other nodes.


  `MATCH (a:MANUFACTURER) WHERE title = “Microsoft” RETURN a.title`

  {: .success}

  
  
  {: .success}

    
left_code_blocks:
  - code_block: |-
      curl -G -H "Authorization: Bearer b900477a9-057b-4878-a16b93477a9-057b-4878-a16f-d7f7d1f27a7af-d7f7d1f27a7a" "https://v6.technopedia.com/tql" --data-urlencode' "q=MATCH (m:MANUFACTURER)-[VENDOR_OF]->(s:SOFTWARE_PRODUCT)<-[VERSION_OF]->(v:SOFTWARE_VERSION)<-[MAJOR_VERSION_OF]->(z:SOFTWARE_MAJOR_VERSION)  WHERE m.manufacturer = "Microsoft" RETURN m, s, v, z LIMIT 1

      
    title: cURL Example
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
      (Manufacturer)-[:VENDOR_OF]->(SOFTWARE_PRODUCT)
      
    title: Relationships
    language: bash
---

