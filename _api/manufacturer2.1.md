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

  ![API Image](/images/query.ex.png){: .img-responsive}<br>&nbsp;
  
    
left_code_blocks:
  - code_block: |-
      curl -G -H "Authorization: Bearer b93477a9-057b-4878-a16b93477a9-057b-4878-a16f-d7f7d1f27a7af-d7f7d1f27a7a" "https://v6.technopedia.com/tql" --data-urlencode' "q=MATCH (h:MANUFACTURER) RETURN h.manufacturer"
    title: cURL 
    language: bash


  - code_block: >-
      MATCH (h:MANUFACTURER) RETURN h.manufacturer

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
        }
       ]
      {    
    title: Example one
    language: javascript
  - code_block: |-
      MATCH (m:MANUFACTURER)<-[:HAS_A]-(s:SOFTWARE_PRODUCT) WHERE m.manufacturer = "Immedia Internet Solutions" RETURN m.manufacturer, s.product, s.created_at
 
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
      MATCH (n:MANUFACTURER)<-[:HAS_A]-(w:SOFTWARE_PRODUCT)-[BELONGS_TO]->(v:CATEGORY_2) RETURN n, w, v

      RESPONSE SAMPLE

      {
        "results": [
           {  
                
            
           }
        ]
      {    
    title: Example three
    language: javascript

  - code_block: |-
      MATCH (n:MANUFACTURER)<-[:HAS_A]-(p:SOFTWARE_PRODUCT)<-[:HAS_A]-(my_alias:SOFTWARE_VERSION) RETURN n, p, my_alias LIMIT 1

      RESPONSE SAMPLE

      {
        "results": [
           {   
               "my_alias.cat_sw_version_id": 124285141,
                "my_alias.created_at": "2015-06-17 16:25:47",
                "my_alias.desupported_flag": null,
                "my_alias.modified_at": "2015-06-17 18:40:19",
                "my_alias.order": "1",
                "my_alias.patch_level": null,
                "my_alias.technopedia_id": "6403acb4-c95b-4ce1-8b93-18218c66cc03",
                "my_alias.version": "6.14",
                "n.cat_manufacturer_id": 5068,
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
                "n.manufacturer": "Callware Technologies",
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
                "n.technopedia_id": "6aacf387-f0cf-48dd-be9b-54eeb24f1dbe",
                "n.tier": 3,
                "n.website": "http://www.callware.com/",
                "n.zip": null,
                "p.alias": null,
                "p.cat_sw_product_id": 1179972,
                "p.component": null,
                "p.created_at": "2007-08-28 00:32:35",
                "p.desupported_flag": null,
                "p.discontinued_flag": null,
                "p.family": "Callegra .UC",
                "p.is_suite": null,
                "p.modified_at": "2011-09-01 10:11:30",
                "p.product": "Callegra .UC",
                "p.technopedia_id": "c9a1430d-242e-4370-a0ab-6300571fd6ba",
                "p.url": "http://www.callware.com/pdfs/UC11/UC11scr.pdf"   
           }
        ]
      {    
    title: Example four
    language: javascript

  - code_block: |-
      MATCH (n:MANUFACTURER)-[:HAS_A]->(p:SOFTWARE_PRODUCT)-[:HAS_A]->(my_alias:SOFTWARE_VERSION) RETURN n, p, my_alias

      RESPONSE SAMPLE

      {
        "results": [
           {   
            
           }
        ]
      {    

      
    title: Example five
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

