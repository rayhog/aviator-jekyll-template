---
title: Software Version
position: 1.2
type: 
description: >-
  Software versions are represented by three nodes. The Software Version Group node represents the group version attributes. 
  The software version node represents the attributes that are associated with child versions of the parent major version or version group.

  The relationship bewtween the nodes is `HAS_A` which points from the `SOFTWARE_VERSION` to `SOFTWARE_VERSION_GROUP` and `SOFTWARE_MAJOR_VERSION.
content_markdown: >-
  The highlighted query returns version information for software.
  <br>
  `MATCH (a:SOFTWARE_VERSION) RETURN a.version`
  <br>
  The following diagram shows the nodes, attributes, and relationships that feature software nodes and their relationships.
  <br>
  ![API Image](/images/sw_ver.png){:class="img-responsive"} <br>

  ### Software Major Version
  
  ######
  The node that represents the major version of software is `SOFTWARE_MAJOR_VERSION`.
  Software versioning is used to categorize the unique states of software as it is developed and released. 
  The version identifier might be a word, or a number, or inlcude both. For example, version 1.0 is often used to represent the initial release of a software product.

  The following query returns software major version information. <br>
   
  `MATCH (a:SOFTWARE_MAJOR_VERSION) RETURN a.version`
  

  ### Software Version Group
  
  ######
  The node that represents the major version of software is `SOFTWARE_VERSION_GROUP`.
  Software version group is used to categorize the software when the version is part of version group that may or may not have a major version.

  Returns software version group information


  `MATCH (a:SOFTWARE_VERSION_GROUP) RETURN a.version`


  <br>

  #### Query Examples <br>
    
  To use the MATCH statements in the following examples, you append the MATCH statement to the following tql endpoint and make a GET request from a API client or use cURL. <br>
  <br>
  `https://v6-1.technopedia.com/tql?q=<MATCH Statement>`
  
left_code_blocks:
  - code_block: |
      MATCH (s:SOFTWARE_PRODUCT)<-[:HAS_A]-(n:SOFTWARE_VERSION) 
      WHERE s.product = "Advanced Partitioning Option" 
      RETURN n, s

      RESPONSE SAMPLE

      {
        "results": [
            {
            "n.cat_sw_version_id": 10427776,
            "n.created_at": "2010-04-12 16:04:13",
            "n.desupported_flag": null,
            "n.modified_at": "2014-02-13 21:44:41",
            "n.order": "2",
            "n.patch_level": null,
            "n.technopedia_id": "72321748-1173-4f2d-9f50-48c069b1a0eb",
            "n.version": "8.0",
            "s.alias": null,
            "s.cat_sw_product_id": 1013435,
            "s.component": null,
            "s.created_at": "2006-12-04 18:04:27",
            "s.desupported_flag": null,
            "s.discontinued_flag": null,
            "s.family": "HiRDB",
            "s.is_suite": null,
            "s.modified_at": "2014-11-26 09:29:51",
            "s.product": "Advanced Partitioning Option",
            "s.technopedia_id": "5e36c7f2-ed15-4fb4-b816-d29696738c13",
            "s.url": "http://www.hitachi.co.jp/Prod/comp/soft1/manual/hirdben/v8/d635100e/W3510016.HTM"
        },
        {
            "n.cat_sw_version_id": 10427777,
            "n.created_at": "2010-04-12 16:04:18",
            "n.desupported_flag": null,
            "n.modified_at": "2014-02-13 21:44:41",
            "n.order": "1",
            "n.patch_level": null,
            "n.technopedia_id": "ad8131bd-e80e-48ad-8aaa-985bab95f06d",
            "n.version": "7.0",
            "s.alias": null,
            "s.cat_sw_product_id": 1013435,
            "s.component": null,
            "s.created_at": "2006-12-04 18:04:27",
            "s.desupported_flag": null,
            "s.discontinued_flag": null,
            "s.family": "HiRDB",
            "s.is_suite": null,
            "s.modified_at": "2014-11-26 09:29:51",
            "s.product": "Advanced Partitioning Option",
            "s.technopedia_id": "5e36c7f2-ed15-4fb4-b816-d29696738c13",
            "s.url": "http://www.hitachi.co.jp/Prod/comp/soft1/manual/hirdben/v8/d635100e/W3510016.HTM"
        }
       ]
      {  

    title: Example one
    language: javascript
  - code_block: >-
      MATCH (n:SOFTWARE_RELEASE) 
      WHERE n.release contains "studio" 
      RETURN n 
      
      RESPONSE SAMPLE

      {
        "results": [
            {
                
                "n.created_at": "2015-11-03 16:53:59",
                "n.desupported_flag": null,
                "n.discontinued_flag": null,
                "n.modified_at": "2017-12-07 09:20:33",
                "n.release": "Math Resource Studio",
                "n.technopedia_id": "4b4c9a40-3f64-4536-b719-d2e95e277481",
                "n.url": null
            },
            {
                "n.created_at": "2009-08-24 07:02:45",
                "n.desupported_flag": null,
                "n.discontinued_flag": null,
                "n.modified_at": "2009-11-13 10:30:42",
                "n.release": "DriverStudio",
                "n.technopedia_id": "e243f07f-ff85-4e08-8839-965f20a13808",
                "n.url": null
            }
        ]
      {  
    title: Example two
    language: javascript
  - code_block: |-
      MATCH (n:SOFTWARE_RELEASE)-[:HAS_A]->(v:SOFTWARE_VERSION)-[:HAS_A]-(pr:SOFTWARE_PRODUCT) 
      WHERE n.release = "WMSigner" 
      RETURN n.release, pr.product, v.version
      
      RESPONSE SAMPLE

      {
        "results": [
            {
            "n.release": "WMSigner",
            "pr.product": "WMSigner",
            "v.version": "1.3"
            },
            {
                "n.release": "WMSigner",
                "pr.product": "WMSigner",
                "v.version": "1.0"
            },
            {
                "n.release": "WMSigner",
                "pr.product": "WMSigner",
                "v.version": "1.2"
            },
            {
                "n.release": "WMSigner",
                "pr.product": "WMSigner",
                "v.version": "1.1"
            },
            {
                "n.release": "WMSigner",
                "pr.product": "WMSigner",
                "v.version": "2.0"
            },
            {
                "n.release": "WMSigner",
                "pr.product": "WMSigner",
                "v.version": "0.1"
            }
        ]
      {   
        
    title: Example 3
    language: javascript

  - code_block: |-
      MATCH (sp:SOFTWARE_PRODUCT)<-[:HAS_A]-(n:SOFTWARE_VERSION)-[:HAS_A]->(p:SOFTWARE_MAJOR_VERSION) 
      RETURN sp.product AS Product, n.version AS VERSION, p.version AS Major_Version  
      LIMIT 5
      
      RESPONSE SAMPLE

      {
        "results": [
            {
                
                "Major_Version": "8.2",
                "Product": "Common Management Information Protocol (CMIP)",
                "VERSION": "8.2.1"
            },
            {
                "Major_Version": "4.0",
                "Product": "Web Proxy Server",
                "VERSION": "4.0.9"
            },
            {
                "Major_Version": "4.0",
                "Product": "Web Proxy Server",
                "VERSION": "4.0.8"
            },
            {
                "Major_Version": "4.0",
                "Product": "Web Proxy Server",
                "VERSION": "4.0.6"
            },
            {
                "Major_Version": "4.0",
                "Product": "Web Proxy Server",
                "VERSION": "4.0.7"
            }
        ]
      {  

    title: Example 4
    language: bash


  - code_block: |-

      MATCH (manu:MANUFACTURER)<-[:HAS_A]-(sp:SOFTWARE_PRODUCT)<-[:HAS_A]-(n:SOFTWARE_VERSION)-[:HAS_A]->(p:SOFTWARE_MAJOR_VERSION) 
      RETURN manu.manufacturer AS Manufacturer, sp.product AS Product, n.version AS VERSION, p.version AS Major_Version 
      LIMIT 5
      
      RESPONSE SAMPLE

      {
        "results": [
            {
                "Major_Version": "8.2",
                "Manufacturer": "Sun Microsystems",
                "Product": "Common Management Information Protocol (CMIP)",
                "VERSION": "8.2.1"
            },
            {
                "Major_Version": "4.0",
                "Manufacturer": "Sun Microsystems",
                "Product": "Web Proxy Server",
                "VERSION": "4.0.9"
            },
            {
                "Major_Version": "4.0",
                "Manufacturer": "Sun Microsystems",
                "Product": "Web Proxy Server",
                "VERSION": "4.0.8"
            },
            {
                "Major_Version": "4.0",
                "Manufacturer": "Sun Microsystems",
                "Product": "Web Proxy Server",
                "VERSION": "4.0.6"
            },
            {
                "Major_Version": "4.0",
                "Manufacturer": "Sun Microsystems",
                "Product": "Web Proxy Server",
                "VERSION": "4.0.7"
            }
        ]
      {  

    title: Example 5
    language: bash

  - code_block: |-
      curl -G -H "Authorization: Bearer b93477a9-057b-4878-a16b93477a9-057b-4878-a16f-d7f7d1f27a7af-d7f7d1f27a7a" "https://v6-1.technopedia.com/tql" --data-urlencode' "q=MATCH (s:SOFTWARE_PRODUCT)<-[:HAS_A]-(n:SOFTWARE_VERSION) WHERE s.product = "Advanced Partitioning Option" RETURN n, s
    title: cURL
    language: bash

right_code_blocks:
  - code_block: |2
      VERSION ATTRIBUTES
      technopedia_id
      version
      order
      created_at
      modified_at


      SOFTWARE VERSION GROUP
      technopedia_id
      version_group
      modified_at
      

      SOFTWARE MAJOR VERSION 
      technopedia_id
      version
      

    title: Software Version Attributes
    language: bash
  - code_block: |2-
      (SOFTWARE_VERSION)<-[:HAS_A)]-(SOFTWARE_RELEASE)

      (SOFTWARE_VERSION)-[:HAS_A)]->(SOFTWARE_PRODUCT)

      (SOFTWARE_VERSION)-[:HAS_A]->(SOFTWARE_VERSION_GROUP)

      (SOFTWARE_VERSION)-[:HAS_A]->(SOFTWARE_MAJOR_VERSION)


    title: Relationships
    language: bash
---

