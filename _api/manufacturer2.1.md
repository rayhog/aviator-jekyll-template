---
title: Manufacturer
position: 2.1
type: 
description: 
content_markdown: |-
  The manufacturer is the creator or producer of the product. In relationships, CPU model, software product, and hardware product nodes have a manufacturer, which is referred to by the `HAS_A` relationship.
  For example, the Microsoft Word software product has a manufacturer named Microsoft.<br>
  <br>
  The following attributes are examples of the manufactuer node attributes: 
  * `manufacturer` provides the name of the manufacturer.
  * `technopedia_id` provides a unique ID.
  * `description` provides a description of the manfacturer.
  <br>
 
  The following MATCH query returns information about the manufacturer named Microsoft. 
  <br>
  `MATCH (a:MANUFACTURER) WHERE a.manufacturer = "Microsoft" RETURN a` <br>
  <br>

  The following diagram shows the the manufacturer node and its connections to software, hardware, and CPU.

  ![API Image](/images/manu.png){:class="img-responsive"} <br>

  #### Query Examples <br>
    
  To use the `MATCH` statements in the following examples, you append the `MATCH` statement to the following `/tql` endpoint and make a GET request from a API client or use cURL. <br>
  <br>
  `https://v6-1.technopedia.com/tql?q=<MATCH Statement>`
    
left_code_blocks:
  - code_block: |-
      MATCH (h:MANUFACTURER) 
      RETURN h.manufacturer

      RESPONSE SAMPLE

      {
        "results": [
            {
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
      MATCH (m:MANUFACTURER)<-[:HAS_A]-(s:SOFTWARE_PRODUCT) 
      WHERE m.manufacturer = "Immedia Internet Solutions" 
      RETURN m.manufacturer, s.product, s.created_at
 
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
      MATCH (n:MANUFACTURER)<-[:HAS_A]-(p:SOFTWARE_PRODUCT)<-[:HAS_A]-(my_alias:SOFTWARE_VERSION) 
      RETURN n, my_alias 
      LIMIT 2


      RESULTS

      {
        "results": [
           {  
                "my_alias.created_at": "2015-06-17 16:25:47",
                "my_alias.desupported_flag": null,
                "my_alias.modified_at": "2015-06-17 18:40:19",
                "my_alias.order": "1",
                "my_alias.patch_level": null,
                "my_alias.technopedia_id": "6403acb4-c95b-4ce1-8b93-18218c66cc03",
                "my_alias.version": "6.14",
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
                "n.zip": null
            },
            {
                "my_alias.created_at": "2016-01-08 14:24:01",
                "my_alias.desupported_flag": null,
                "my_alias.modified_at": "2016-01-08 14:24:01",
                "my_alias.order": "2",
                "my_alias.patch_level": null,
                "my_alias.technopedia_id": "43d856b4-d761-448b-87d6-85e070b4ed4e",
                "my_alias.version": "6.15",
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
                "n.zip": null
            }
        ]
      {    
    title: Example three
    language: javascript

  - code_block: |-
      MATCH (manuf:MANUFACTURER)<-[:HAS_A]-(sw_prod:SOFTWARE_PRODUCT)<-[:HAS_A]-(sft_ver:SOFTWARE_VERSION) 
      RETURN manuf.manufacturer, sw_prod.product, sft_ver.version 
      LIMIT 5

      RESULTS

      {
        "results": [
            {   
                "manuf.manufacturer": "Callware Technologies",
                "sft_ver.version": "6.14",
                "sw_prod.product": "Callegra .UC"
            },
            {
                "manuf.manufacturer": "Callware Technologies",
                "sft_ver.version": "6.15",
                "sw_prod.product": "Callegra .UC"
            },
            {
                "manuf.manufacturer": "AnalogX",
                "sft_ver.version": "1.03",
                "sw_prod.product": "MaxMem"
            },
            {
                "manuf.manufacturer": "AnalogX",
                "sft_ver.version": "1.04",
                "sw_prod.product": "MaxMem"
            },
            {
                "manuf.manufacturer": "AnalogX",
                "sft_ver.version": "1.01",
                "sw_prod.product": "MaxMem"
            }
        ]
      {    
    title: Example four
    language: javascript

  - code_block: |-
      MATCH (n:MANUFACTURER)-[:HAS_A]-(product:SOFTWARE_PRODUCT)<-[:HAS_A]-(version:SOFTWARE_VERSION) 
      RETURN n.manufacturer, product, version 
      LIMIT 2

      RESULTS

      {
        "results": [
            { 
                "n.manufacturer": "Callware Technologies",
                "product.alias": null,
                "product.component": null,
                "product.created_at": "2007-08-28 00:32:35",
                "product.desupported_flag": null,
                "product.discontinued_flag": null,
                "product.family": "Callegra .UC",
                "product.is_suite": null,
                "product.modified_at": "2011-09-01 10:11:30",
                "product.product": "Callegra .UC",
                "product.technopedia_id": "c9a1430d-242e-4370-a0ab-6300571fd6ba",
                "product.url": "http://www.callware.com/pdfs/UC11/UC11scr.pdf",
                "version.created_at": "2015-06-17 16:25:47",
                "version.desupported_flag": null,
                "version.modified_at": "2015-06-17 18:40:19",
                "version.order": "1",
                "version.patch_level": null,
                "version.technopedia_id": "6403acb4-c95b-4ce1-8b93-18218c66cc03",
                "version.version": "6.14"
            },
            {
                "n.manufacturer": "Callware Technologies",
                "product.alias": null,
                "product.component": null,
                "product.created_at": "2007-08-28 00:32:35",
                "product.desupported_flag": null,
                "product.discontinued_flag": null,
                "product.family": "Callegra .UC",
                "product.is_suite": null,
                "product.modified_at": "2011-09-01 10:11:30",
                "product.product": "Callegra .UC",
                "product.technopedia_id": "c9a1430d-242e-4370-a0ab-6300571fd6ba",
                "product.url": "http://www.callware.com/pdfs/UC11/UC11scr.pdf",
                "version.created_at": "2016-01-08 14:24:01",
                "version.desupported_flag": null,
                "version.modified_at": "2016-01-08 14:24:01",
                "version.order": "2",
                "version.patch_level": null,
                "version.technopedia_id": "43d856b4-d761-448b-87d6-85e070b4ed4e",
                "version.version": "6.15"
                
           }
        ]
      {    

      
    title: Example five
    language: bash
  - code_block: >-
      curl -G -H "Authorization: Bearer b93477a9-057b-4878-a16b93477a9-057b-4878-a16f-d7f7d1f27a7af-d7f7d1f27a7a" "https://v6.technopedia.com/tql" --data-urlencode' "q=MATCH (h:MANUFACTURER) RETURN h.manufacturer"
    title: cURL 
    language: bash
    
right_code_blocks:
  - code_block: |2
      technopedia_id
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

