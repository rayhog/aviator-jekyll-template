---
title: Software Edition
position: 1.5
type: 
description: Matches the software edition from the Technopedia database.
content_markdown: |-
  Software edition represents the version of the product, such as Standard, Premium, or other version name for the product.
  <br>


  `MATCH (e:SOFTWARE_EDITION {edition: 'Black'}) RETURN e`
  {: .success}

  <br>
  Here's an example of querying the release title "Advanced Partitioning Option" that is a release of a software version.<br>
  <br>
  `MATCH (s.SOFTWARE_PRODUCT)<-[:HAS_A]-(n:SOFTWARE_EDITION) WHERE n.edition = "Advanced Partitioning Option" RETURN n`
  <br>
  The following diagram shows the sofware editon node and its related software nodes.
  <br>
  ![API Image](/images/sw_edition.png){:class="img-responsive"} <br>

  #### Query Examples <br>
    
  To use the MATCH statements in the following examples, you append the MATCH statement to the following tql endpoint and run a GET request from a API client or use cURL. <br>
  <br>
  `https://v6-1.technopedia.com/tql?q=<MATCH Statement>`
left_code_blocks:
  - code_block: |
      https://v6-1.technopedia.com/tql?q=MATCH (n:SOFTWARE_EDITION) RETURN n.edition AS EDITION, n.modified_at AS MODIFIED 

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
      MATCH (e:SOFTWARE_EDITION {edition: 'Server'}) RETURN e
      RESPONSE SAMPLE

      {
        "results": [
            {
            "e.cat_sw_edition_id": 1175193,
            "e.created_at": "2007-08-23 15:47:19",
            "e.desupported_flag": null,
            "e.edition": "Server",
            "e.modified_at": "2017-04-20 14:49:12",
            "e.order": 5,
            "e.technopedia_id": "fa5b79c1-8304-4604-bc70-f2e4f9469960",
            "e.url": "https://en.wikipedia.org/wiki/List_of_Microsoft_Windows_versions"
        },
        {
            "e.cat_sw_edition_id": 58734341,
            "e.created_at": "2014-02-21 16:14:21",
            "e.desupported_flag": null,
            "e.edition": "Server",
            "e.modified_at": "2014-02-21 16:14:21",
            "e.order": 2,
            "e.technopedia_id": "36caabb2-af3a-4591-9466-d854bad6cf3f",
            "e.url": "http://www.ni.com/datafinder/"
        }
        ]
      {  
    title: Example two
    language: javascript
  - code_block: |-
      MATCH (n:SOFTWARE_RELEASE)-[p:HAS_A]->(a:SOFTWARE_VERSION)-[o:HAS_A]->(g:SOFTWARE_PRODUCT) RETURN n.name LIMIT 5

      RESPONSE SAMPLE

      {
        "results": [
            {
                "test",
                "s.test",
                "s.anything"
            }
        ]
      {  
    title: Example three
    language: javascript

  - code_block: |-
      MATCH (n:SOFTWARE_RELEASE)-[:HAS_A]->(x:SOFTWARE_VERSION) RETURN x.version LIMIT 10

      RESPONSE SAMPLE

      {
        "results": [
            {
                "test",
                "s.test",
                "s.anything"
            }
        ]
      {  
    title: Example four
    language: javascript

  - code_block: |-
      MATCH (n:SOFTWARE_EDITION) -[:HAS_A]->(u:SOFTWARE_PRODUCT) RETURN n, u LIMIT 10

      RESPONSE SAMPLE

      {
        "results": [
            {
                "test",
                "s.test",
                "s.anything"
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
      edition_order
      url
      created_at
      modified_at

    title: Software Edition Attributes
    language: bash
  - code_block: |2-
      (SOFTWARE_EDITION)<-[:EDITION_OF]-(SOFTWARE_EDITION)

      (SOFTWARE_EDITION)-[:HAS_A]->(SOFTWARE_RELEASE)

      (SOFTWARE_EDITION)-[:HAS_A]->(SOFTWARE_PRODUCT)
      
      (SOFTWARE_EDITION)<-[:HAS_A]->(SOFTWARE_RELEASE)-[:HAS_A]->(SUPPORT_STAGE)

      (SOFTWARE_EDITION)<-[:HAS_A]->(SOFTWARE_RELEASE)-[:HAS_A]->(COMPATIBLE_PLATFORM)

      

      



    title: Relationships
    language: bash
---

