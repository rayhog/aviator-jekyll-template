---
title: Software Product
position: 1.15
type:
description: >-
  The software product node features the product name and other important attributes. When you query any of the software nodes, it's likely that you will want to include the software product node to get back the product name in your results.
  
content_markdown: >-
  In the following query example, you get data from Technopedia that contains PDF Converter in the name of the software product name.


  `MATCH (n:SOFTWARE_PRODUCT) WHERE n.product = "PDF Converter" RETURN n` 
  
  {: .success} 
  
  <br>
  The following diagram shows the six software nodes and their relationships.
  
  ![API Image](/images/sw_prod.png){: .img-responsive}<br>&nbsp;

  #### Query Examples <br>
    
  To use the MATCH statements in the following examples, you append the MATCH statement to the following tql endpoint and make a GET request from a API client or use cURL. <br>
  <br>
  `https://v6-1.technopedia.com/tql?q=<MATCH Statement>`
  
left_code_blocks:
  - code_block: |
      MATCH (n:SOFTWARE_PRODUCT) 
      WHERE n.product = "PDF Converter" 
      RETURN n
      LIMIT 2

      RESPONSE SAMPLE
      {
         "results": [
            {
                
                "n.alias": null,
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
        ]
      {     
         

    title: Example one
    language: javascript
  - code_block: >-
      MATCH (s:SOFTWARE_PRODUCT) 
      WHERE s.product = "Office" AND s.family = "HealthMatics"  
      RETURN s
      LIMIT 2
      
      
      RESPONSE SAMPLE

      {
        "results": [
            {
                "s.alias": null,
                "s.component": null,
                "s.created_at": "2007-04-22 04:55:16",
                "s.desupported_flag": null,
                "s.discontinued_flag": null,
                "s.family": "HealthMatics",
                "s.is_suite": null,
                "s.modified_at": "2017-06-01 10:44:00",
                "s.product": "Office",
                "s.technopedia_id": "141d9f85-66b2-40a6-8efa-450038c2700c",
                "s.url": "http://investor.allscripts.com/phoenix.zhtml?c=112727&p=irol-newsArticle&ID=858912&highlight="
            },
            {
                "s.alias": null,
                "s.component": null,
                "s.created_at": "2007-11-06 01:01:57",
                "s.desupported_flag": null,
                "s.discontinued_flag": null,
                "s.family": "HealthMatics",
                "s.is_suite": null,
                "s.modified_at": "2017-06-01 15:32:17",
                "s.product": "Office",
                "s.technopedia_id": "918cadd3-b2fc-4733-8f0f-7a141234037c",
                "s.url": "http://investor.allscripts.com/phoenix.zhtml?c=112727&p=irol-newsArticle&ID=858912&highlight="
            }
        ]
      {  
    title: Example two
    language: javascript
  - code_block: |-
      MATCH (sp:SOFTWARE_PRODUCT)<-[:HAS_A]-(sv:SOFTWARE_VERSION)<-[:HAS_A]-(sr:SOFTWARE_RELEASE)-[:HAS_A]->(st:SUPPORT_STAGE) 
      RETURN sp.product, sv.version, sr, st 
      LIMIT 2

      RESPONSE SAMPLE

      {
        "results": [
                "sp.product": "ID Web Authentication Software Development Kit (SDK)",
                "sr.created_at": "2010-01-08 21:17:49",
                "sr.desupported_flag": null,
                "sr.discontinued_flag": null,
                "sr.modified_at": "2014-04-01 14:52:04",
                "sr.release": "ID Web Authentication Software Development Kit (SDK)",
                "sr.technopedia_id": "4aa33382-7a99-4210-8e71-7b7680879acd",
                "sr.url": null,
                "st.created_at": "2005-09-09 15:00:46",
                "st.definition": "Self-Help Online Support is available throughout a product's lifecycle and for a minimum of 12 months after the product
                 reaches the end of its support. By using the Microsoft online Knowledge Base articles, FAQs, troubleshooting tools, and other resources, many customers can quickly resolve their issues without needing to contact Microsoft directly.\r\nSee http://support.microsoft.com/lifecycle/",
                "st.modified_at": "2016-07-15 14:49:36",
                "st.order": 3,
                "st.support_stage": null,
                "st.technopedia_id": "9af71bf0-55c5-46ca-9bf5-b2790a31c384",
                "sv.version": "1.0"
            },
            {
                "sp.product": "ID Web Authentication Software Development Kit (SDK)",
                "sr.created_at": "2010-01-08 21:17:49",
                "sr.desupported_flag": null,
                "sr.discontinued_flag": null,
                "sr.modified_at": "2014-04-01 14:52:04",
                "sr.release": "ID Web Authentication Software Development Kit (SDK)",
                "sr.technopedia_id": "4aa33382-7a99-4210-8e71-7b7680879acd",
                "sr.url": null,
                "st.created_at": "2005-09-09 15:00:46",
                "st.definition": "Extended Support phase follows Mainstream Support for Business and Developer products. \r\nAt the supported service pack
                 level, Extended Support includes:\r\nPaid support\r\nSecurity update support at no additional cost\r\nNon-security related hotfix support requires a separate Extended Hotfix Support Agreement to be purchased (per-fix fees also apply)\r\nMicrosoft will not accept requests for warranty support, design changes, or new features during the Extended Support phase\r\nExtended Support is not available for Consumer, Hardware, Multimedia, and Microsoft Dynamics products\r\nSee http://support.microsoft.com/lifecycle/",
                "st.modified_at": "2016-07-15 14:49:36",
                "st.order": 2,
                "st.support_stage": null,
                "st.technopedia_id": "6ad733c9-8997-4efd-821b-d76592774476",
                "sv.version": "1.0"
            }
        ]
      {  
          
    title: Example three
    language: javascript

  - code_block: |-
      MATCH (sp:SOFTWARE_PRODUCT)<-[:HAS_A]-(sv:SOFTWARE_VERSION)<-[:HAS_A]-(sr:SOFTWARE_RELEASE)-[:HAS_A]->(st:SUPPORT_STAGE) 
      WHERE sr.release = "ID Web Authentication Software Development Kit (SDK)" 
      RETURN sp.product, sv.version, sr, st 
      LIMIT 2

      RESPONSE SAMPLE

      {
        "results": [
            {
                "sp.product": "ID Web Authentication Software Development Kit (SDK)",
                "sr.created_at": "2010-01-08 21:17:28",
                "sr.desupported_flag": null,
                "sr.discontinued_flag": null,
                "sr.modified_at": "2014-04-01 14:51:55",
                "sr.release": "ID Web Authentication Software Development Kit (SDK)",
                "sr.technopedia_id": "734576e8-8ef4-4707-be61-3c5ecd133802",
                "sr.url": null,
                "st.created_at": "2005-09-09 15:00:46",
                "st.definition": "Self-Help Online Support is available throughout a product's lifecycle and for a minimum of 12 months after the product
                 reaches the end of its support. By using the Microsoft online Knowledge Base articles, FAQs, troubleshooting tools, and other resources, many customers can quickly resolve their issues without needing to contact Microsoft directly.\r\nSee http://support.microsoft.com/lifecycle/",
                "st.modified_at": "2016-07-15 14:49:36",
                "st.order": 3,
                "st.support_stage": null,
                "st.technopedia_id": "9af71bf0-55c5-46ca-9bf5-b2790a31c384",
                "sv.version": "1.2"
            },
            {
                "sp.product": "ID Web Authentication Software Development Kit (SDK)",
                "sr.created_at": "2010-01-08 21:17:28",
                "sr.desupported_flag": null,
                "sr.discontinued_flag": null,
                "sr.modified_at": "2014-04-01 14:51:55",
                "sr.release": "ID Web Authentication Software Development Kit (SDK)",
                "sr.technopedia_id": "734576e8-8ef4-4707-be61-3c5ecd133802",
                "sr.url": null,
                "st.created_at": "2005-09-09 15:00:46",
                "st.definition": "Extended Support phase follows Mainstream Support for Business and Developer products. \r\nAt the supported service pack
                 level, Extended Support includes:\r\nPaid support\r\nSecurity update support at no additional cost\r\nNon-security related hotfix support  requires a separate Extended Hotfix Support Agreement to be purchased (per-fix fees also apply)\r\nMicrosoft will not accept requests for warranty support, design changes, or new features during the Extended Support phase\r\nExtended Support is not available for Consumer, Hardware, Multimedia, and Microsoft Dynamics products\r\nSee http://support.microsoft.com/lifecycle/",
                "st.modified_at": "2016-07-15 14:49:36",
                "st.order": 2,
                "st.support_stage": null,
                "st.technopedia_id": "6ad733c9-8997-4efd-821b-d76592774476",
                "sv.version": "1.2"
            }
        ]
      {  
    title: Example four
    language: javascript

  - code_block: |-
      MATCH (sp:SOFTWARE_PRODUCT)<-[:HAS_A]-(sv:SOFTWARE_VERSION)<-[:HAS_A]-(sr:SOFTWARE_RELEASE)-[:HAS_A]->(se:SOFTWARE_EDITION) 
      WHERE sp.product CONTAINS "Software Development Kit" 
      RETURN sp.product, sv.version, sr, se 
      LIMIT 2

      RESPONSE SAMPLE

      {
        "results": [
            {
            "se.created_at": "2007-03-13 05:33:25",
            "se.desupported_flag": null,
            "se.edition": "Standard",
            "se.modified_at": "2017-04-21 16:42:40",
            "se.order": 1,
            "se.technopedia_id": "95c26142-8dcf-4666-94e9-61f53fbc13e3",
            "se.url": "https://www.ibm.com/support/knowledgecenter/ssw_i5_54/rzaat/rzaatj.htm",
            "sp.product": "Java 2 Software Development Kit (J2SDK)",
            "sr.created_at": "2007-08-23 20:09:08",
            "sr.desupported_flag": true,
            "sr.discontinued_flag": null,
            "sr.modified_at": "2017-10-10 14:52:00",
            "sr.release": "Java 2 Software Development Kit (J2SDK)",
            "sr.technopedia_id": "d3bffa93-34c4-49bd-8c81-01864cc7e11c",
            "sr.url": null,
            "sv.version": "1.3.1_15"
        },
        {
            "se.created_at": "2007-03-13 05:33:25",
            "se.desupported_flag": null,
            "se.edition": "Standard",
            "se.modified_at": "2017-04-21 16:42:40",
            "se.order": 1,
            "se.technopedia_id": "95c26142-8dcf-4666-94e9-61f53fbc13e3",
            "se.url": "https://www.ibm.com/support/knowledgecenter/ssw_i5_54/rzaat/rzaatj.htm",
            "sp.product": "Java 2 Software Development Kit (J2SDK)",
            "sr.created_at": "2007-04-22 22:19:12",
            "sr.desupported_flag": true,
            "sr.discontinued_flag": null,
            "sr.modified_at": "2017-10-10 14:52:00",
            "sr.release": "Java 2 Software Development Kit (J2SDK)",
            "sr.technopedia_id": "3dca4671-f574-4a3e-bc8a-a6e8667a54dd",
            "sr.url": null,
            "sv.version": "1.5.0"
        }
      ]
    {  
    title: Example five
    language: javascript

  - code_block: |-
      MATCH (s:SOFTWARE_PRODUCT) 
      WHERE s.product = "Office" OR s.product = "HealthMatics" 
      RETURN s 
      LIMIT 2

      RESPONSE SAMPLE

      {
        "results": [
            {
                "s.alias": null,
                "s.component": null,
                "s.created_at": "2007-04-22 04:55:16",
                "s.desupported_flag": null,
                "s.discontinued_flag": null,
                "s.family": "HealthMatics",
                "s.is_suite": null,
                "s.modified_at": "2017-06-01 10:44:00",
                "s.product": "Office",
                "s.technopedia_id": "141d9f85-66b2-40a6-8efa-450038c2700c",
                "s.url": "http://investor.allscripts.com/phoenix.zhtml?c=112727&p=irol-newsArticle&ID=858912&highlight="
            },
            {
                "s.alias": null,
                "s.component": null,
                "s.created_at": "2013-01-09 10:00:34",
                "s.desupported_flag": null,
                "s.discontinued_flag": null,
                "s.family": null,
                "s.is_suite": "FALSE",
                "s.modified_at": "2014-02-13 21:43:30",
                "s.product": "Office",
                "s.technopedia_id": "35785f94-d5e2-4e0b-b2f1-b7e59ecde968",
                "s.url": "http://www.corel.com/corel/product/index.jsp?pid=prod3430104&cid=catalog50008&segid=692&storeKey=ca&languageCode=en"
            }
        ]
      {  
    title: Example six
    language: javascript

  - code_block: |-
      curl -G -H "Authorization: Bearer b93477a9-057b-4878-a16b93477a9-057b-4878-a16f-d7f7d1f27a7af-d7f7d1f27a7a" "https://v6.technopedia.com/tql" --data-urlencode' "q=MATCH (h:SOFTWARE_PRODUCT) RETURN h.product"

      
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

      (SOFTWARE_PRODUCT)<-[:HAS_A]-(SOFTWARE_VERSION)

      (SOFTWARE_PRODUCT)<-[:HAS_A]-(SOFTWARE_VERSION)<-[:HAS_A]-(SOFTWARE_RELEASE)

      
      (SOFTWARE_PRODUCT)-[:BELONGS_TO]->(CATEGORY_2)
      

    title: Relationships
    language: bash
---

