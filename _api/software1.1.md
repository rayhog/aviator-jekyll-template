---
title: Software Nodes
position: 1.1
type: 
description: 
content_markdown: |-
  Software is categorized by edition, product, version, version group, major version and release. To query a specific category, you query the node that represents the category, such as software editon.
  <br>
  The software product node is a good starting point when you want to start with a product name reference and then build out your query to include data from other software nodes such as edition or version. <br>
  <br>

  The following query examples return data that is specific to software data: <br>

  * `MATCH (a:SOFTWARE_RELEASE) RETURN a` <br>
     Returns release data <br>
  * `MATCH (f:SOFTWARE_PRODUCT) RETURN f` <br>
     Returns product data <br>
  * `MATCH (x:SOFTWARE_EDITION) RETURN x` <br>
     Returns edition data <br>
  * `MATCH (y:SOFTWARE_VERSION) RETURN y` <br>
     Returns version data <br>
  * `MATCH (z:SOFTWARE_MAJOR_VERSION) RETURN z` <br>
     Returns major version data  <br>
  * `MATCH (abc:SOFTWARE_VERSION_GROUP) RETURN abc` <br>
     Returns version group data  <br>

  <br>
  
  For more information about specific software nodes, click a link to go to the relevant page:

   * [Product node](../#apisw_prod115)
   * [Version node](../#apisw_verison12)
   * [Edition node](../#apisw_edition15)
   * [Release node](../#apisw_release16)

  Use a combination of the software nodes with relationships to query software data in Technopedia. <br>
  
  The following diagram shows the software nodes, manufacturer node, and node relationships.
  <br>
  ![API Image](/images/sw_graph.png){:class="img-responsive"} <br> 
  <br>
 
  #### Query Examples <br>
    
  To use the `MATCH` statements in the following examples, you append the `MATCH` statement to the following `/tql` endpoint and make a GET request from a API client or use cURL. <br>
  <br>
  `https://v6-1.technopedia.com/tql?q=<MATCH Statement>`
left_code_blocks:
  - code_block: |
      MATCH (n:SOFTWARE_PRODUCT)<-[:HAS_A]-(b:SOFTWARE_VERSION)<-[:HAS_A]-(x:SOFTWARE_RELEASE)-[:HAS_A]->(y:SOFTWARE_EDITION) 
      RETURN n.product, b.version, y.edition 
      LIMIT 5

      RESULTS

      {
        "results": [
            {
                
                "b.version": "4.0",
                "n.product": "Windows NT",
                "y.edition": "Server"
            },
            {
                "b.version": "4.0",
                "n.product": "Windows NT",
                "y.edition": "Server"
            },
            {
                "b.version": "4.0",
                "n.product": "Windows NT",
                "y.edition": "Server"
            },
            {
                "b.version": "3.5",
                "n.product": "Windows NT",
                "y.edition": "Server"
            },
            {
                "b.version": "3.51",
                "n.product": "Windows NT",
                "y.edition": "Server"
            }
        ]
      {  


    title: Example one
    language: javascript
  - code_block: >-
      MATCH (s:SOFTWARE_PRODUCT) 
      WHERE s.product CONTAINS "Vagrant Manager" 
      RETURN s
      
      
      RESPONSE SAMPLE

      {
        "results": [
            {
                "s.alias": null,
                "s.component": null,
                "s.created_at": "2017-08-23 14:23:31",
                "s.desupported_flag": null,
                "s.discontinued_flag": null,
                "s.family": null,
                "s.is_suite": "FALSE",
                "s.modified_at": "2017-12-18 16:44:19",
                "s.product": "Vagrant Manager for OS X",
                "s.technopedia_id": "895b9a9f-4484-437e-a8ba-528fc4ed6c70",
                "s.url": "https://github.com/lanayotech/vagrant-manager"
            },
            {
                "s.alias": null,
                "s.component": null,
                "s.created_at": "2017-08-23 14:23:57",
                "s.desupported_flag": null,
                "s.discontinued_flag": null,
                "s.family": null,
                "s.is_suite": "FALSE",
                "s.modified_at": "2017-08-23 18:30:03",
                "s.product": "Vagrant Manager",
                "s.technopedia_id": "db156f02-ba82-4c3b-bd68-d5eb29372c40",
                "s.url": "http://vagrantmanager.com/windows/"
            }
        ]
      {  

    title: Example 2
    language: javascript
  - code_block: |-
      MATCH (s:SOFTWARE_PRODUCT)-[:BELONGS_TO]->(cat2:CATEGORY_2) 
      WHERE s.product CONTAINS "Tools" 
      RETURN s.product, cat2.label 
      LIMIT 5

      RESULTS 

      {
        "results": [
            {
                "cat2.label": "Accounting",
                "s.product": "Estate Planning Tools"
            },
            {
                "cat2.label": "PIM & Contact Managers",
                "s.product": "FaxTools eXPert"
            },
            {
                "cat2.label": "PIM & Contact Managers",
                "s.product": "Password Recovery Tools"
            },
            {
                "cat2.label": "PIM & Contact Managers",
                "s.product": "OutlookTools"
            },
            {
                "cat2.label": "PIM & Contact Managers",
                "s.product": "Java Calendar Tools"
            }
       ]
      {  

    title: Example three
    language: javascript

  - code_block: |-
      MATCH (s:SOFTWARE_PRODUCT)-[:BELONGS_TO]->(cat2:CATEGORY_2)-[:BELONGS_TO]->(cat1:CATEGORY_1)-[:BELONGS_TO]->(catgrp:CATEGORY_GROUP) 
      WHERE s.product CONTAINS "Tools" RETURN s.product, cat1.label, cat2.label, catgrp.label 
      LIMIT 5

      RESULTS

      {
        "results": [
            {
                "cat1.label": "Product Lifecycle Management (PLM)",
                "cat2.label": "Product Data Management",
                "catgrp.label": "Business Applications",
                "s.product": "Service Desk Knowledge Tools"
            },
            {
                "cat1.label": "Product Lifecycle Management (PLM)",
                "cat2.label": "Product Data Management",
                "catgrp.label": "Business Applications",
                "s.product": "ServicePlus Knowledge Tools"
            },
            {
                "cat1.label": "Product Lifecycle Management (PLM)",
                "cat2.label": "Product Data Management",
                "catgrp.label": "Business Applications",
                "s.product": "Service Desk Knowledge Tools"
            },
            {
                "cat1.label": "Product Lifecycle Management (PLM)",
                "cat2.label": "Product Data Management",
                "catgrp.label": "Business Applications",
                "s.product": "JTB CAD Automation Tools"
            },
            {
                "cat1.label": "Manufacturing Resource Planning (MRP)",
                "cat2.label": "Plant/Shop Control",
                "catgrp.label": "Business Applications",
                "s.product": "PowerTools"
            }      
        ]
      {  

    title: Example four
    language: javascript

  - code_block: |-
      MATCH (n:SOFTWARE_RELEASE)-[:HAS_A]->(r:SOFTWARE_VERSION)-[:HAS_A]->(k:SOFTWARE_PRODUCT) 
      RETURN n, r, k 
      LIMIT 1

      RESULTS

      {
        "results": [
            {
                "k.alias": null,
                "k.component": null,
                "k.created_at": "2008-03-25 22:07:06",
                "k.desupported_flag": null,
                "k.discontinued_flag": null,
                "k.family": "Windows Live",
                "k.is_suite": "FALSE",
                "k.modified_at": "2011-03-21 17:47:50",
                "k.product": "ID Web Authentication Software Development Kit (SDK)",
                "k.technopedia_id": "359e53c0-6cda-4e3b-aaa1-2b05537ca718",
                "k.url": "http://www.microsoft.com/Downloads/details.aspx?familyid=E565FC92-D5F6-4F5F-8713-4DD1C90DE19F&displaylang=en",
                "n.created_at": "2010-01-08 21:17:49",
                "n.desupported_flag": null,
                "n.discontinued_flag": null,
                "n.modified_at": "2014-04-01 14:52:04",
                "n.technopedia_id": "4aa33382-7a99-4210-8e71-7b7680879acd",
                "n.url": null,
                "r.created_at": "2010-01-08 21:04:11",
                "r.desupported_flag": null,
                "r.modified_at": "2012-05-17 18:24:50",
                "r.order": "1",
                "r.patch_level": null,
                "r.technopedia_id": "154568f0-d0b3-4afd-9a4d-079dfc4ebe69",
                "r.version": "1.0"
            }
        ]
      {  

    title: Example five
    language: javascript
  - code_block: |-
      MATCH (sp:SOFTWARE_PRODUCT)<-[:HAS_A]-(se:SOFTWARE_EDITION)<-[:HAS_A]-(srelease:SOFTWARE_RELEASE) 
      RETURN sp.product, se.edition, srelease.technopedia_id 
      LIMIT 5

      RESULTS

      {
        "results": [
            {
                "se.edition": "Server",
                "sp.product": "Windows NT",
                "srelease.technopedia_id": "6f5a33e3-0cc4-4a39-90b4-4ca8c2d1e488"
            },
            {
                "se.edition": "Server",
                "sp.product": "Windows NT",
                "srelease.technopedia_id": "42ec9c15-6fda-4ec4-97dd-a89d454c35a7"
            },
            {
                "se.edition": "Server",
                "sp.product": "Windows NT",
                "srelease.technopedia_id": "cdb759aa-4ce7-49cf-b8ee-5a9c9f441d59"
            },
            {
                "se.edition": "Server",
                "sp.product": "Windows NT",
                "srelease.technopedia_id": "5cdfbb2e-611f-4f50-abf1-26e7eee235f0"
            },
            {
                "se.edition": "Server",
                "sp.product": "Windows NT",
                "srelease.technopedia_id": "9848e1a2-0116-4b62-91da-ee681da8ad1a"
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
      Software consists of the following nodes:

      SOFTWARE_PRODUCT
      SOFTWARE_VERSION
      SOFTWARE_VERSION_GROUP
      SOFTWARE_MAJOR_VERSION
      SOFTWARE_EDITION
      SOFTWARE_RELEASE

      Query specific software data by using the individual nodes, or use relationships to connect nodes.      

    title: Software Nodes
    language: text
  - code_block: |2-
      SOFTWARE NODES RELATIONSHIPS

      (SOFTWARE_PRODUCT)<-[:HAS_A]-(SOFTWARE_EDITION)

      (SOFTWARE_RELEASE)-[:HAS_A]->(SOFTWARE_EDITION)

      (MANUFACTURER)<-[:HAS_A]-(SOFTWARE_PRODUCT)

      (SOFTWARE_VERSION)<-[:HAS_A]-(SOFTWARE_RELEASE)

      (SOFTWARE_VERSION)-[:HAS_A]->(SOFTWARE_VERSION_GROUP)

      (SOFTWARE_VERSION)-[:HAS_A]->(SOFTWARE_MAJOR VERSION)

      (SOFTWARE_RELEASE)-[:HAS_A]->(SUPPORT_STAGE)

      (SOFTWARE_RELEASE)-[:HAS_A]->(SOFTWARE_EDITION)-[:HAS_A]->(SUPPORT_POLICY)

      (SOFTWARE_RELEASE)-[:HAS_A]->(COMPATIBLE_PLATFORM)

      (SOFTWARE_RELEASE)-[:HAS_A]->(CERTIFICATION)

      



    title: Software Nodes Relationships
    language: text
  - code_block: |2-
      WHERE
      Return software products where the name field is equal to ‘Office’. 

      MATCH (s:SOFTWARE_PRODUCT) WHERE s.product = "Office"  RETURN s

      AND
      Return software products where name is Office and the family is HealthMatics. 

      MATCH (s:SOFTWARE_PRODUCT) WHERE s.product = "Office" AND s.family = "HealthMatics" RETURN s 
           
      OR
      Return software products where product name is Office or HealthMatics. 

      MATCH (s:SOFTWARE_PRODUCT) WHERE s.product = "Office" OR s.product = "HealthMatics" RETURN s 
            
      COUNT
      Return count of records. 

      MATCH (s:SOFTWARE_PRODUCT) RETURN count(*) 

      DISTINCT
      Return distinct records only, which do not show duplicates.

      MATCH (s:SOFTWARE_PRODUCT) WHERE s.product = "Microsoft Exchange Server Monitor" RETURN DISTINCT s 
      
      CONTAINS
      Use the CONTAINS clause to return results when an attribute word value is matched. 

      MATCH (s:SOFTWARE_PRODUCT) WHERE s.product CONTAINS "Microsoft" RETURN s 

      AS
      Return output parameter as another name. 

      MATCH (n:SOFTWARE_EDITION) RETURN n.edition as ED, n.modified_at as MOD

      ORDER BY  <br>
      Sort in ascending (ASC) or descending (DESC) order
      
      MATCH (n:SOFTWARE_PRODUCT) RETURN n.product ORDER BY n.product ASC
      MATCH (n:SOFTWARE_PRODUCT) RETURN n.product ORDER BY n.product DESC

      Operators =, <>, >, <, >=, <=
    title: TQL Clauses
    language: text
---