---
title: Software Release
position: 1.6
type:
description: 

content_markdown: >-
  You reference the software release node to get software release data in Technopedia.<br>
  <br>
  The following query returns all software release data:<br>

  `MATCH (a:SOFTWARE_RELEASE) RETURN a.release`<br>
  <br>

  
  The following diagram shows the software nodes, relationships, and the software release attributes.<br>
  <br>

  ![API Image](/images/sw_release.png){:class="img-responsive"} <br>
  <br>
 
  The software release node connects to the software edtion, software version, and support stage nodes by the `HAS_A` relationship. <br>
  <br>
  The software release and support stage nodes are connected by the `HAS_A` relationship, which has its own attributes.
  <br>
  To retrieve information about a relationship, you assign it an alias for later reference. <br>
  You place the alias in front of the colon that precedes the relationship: <br>
   `-[my_alias:HAS_A]->` <br>

  The following query returns data for the end date of the software release's support stage.<br>
  <br>
  `MATCH (:SOFTWARE_RELEASE)-[my_alias:HAS_A {end_date: "2013-12-10 00:00:00"}]->(:SUPPORT_STAGE) RETURN my_alias`

  #### Query Examples <br>
    
  To use the `MATCH` statements in the following examples, you append the `MATCH` statement to the following `/tql` endpoint and make a GET request from a API client or use cURL. <br>
  <br>
  `https://v6-1.technopedia.com/tql?q=<MATCH Statement>`
left_code_blocks:
  - code_block: |
      MATCH (n:SOFTWARE_RELEASE) 
      RETURN n.release, n.created_at 
      LIMIT 5

      RESPONSE SAMPLE

      {
        "results": [
            {
                "n.created_at": "2014-04-25 15:20:43",
                "n.release": "WMSigner"
            },
            {
                "n.created_at": "2016-02-11 11:18:47",
                "n.release": "Virtualenvwrapper"
            },
            {
                "n.created_at": "2015-02-02 13:48:58",
                "n.release": "File Master Plus"
            },
            {
                "n.created_at": "2016-02-24 09:44:04",
                "n.release": "WV-ASF900 Series"
            },
            {
                "n.created_at": "2015-05-18 10:58:59",
                "n.release": "Wise Plugin Manager"
            }
         ]
      }

    title: Example one
    language: javascript
  - code_block: >-
      MATCH (nodeX)-[an_alias:relationship {relationship_attribute : value}]->(:nodeY) 
      RETURN an_alias


      MATCH (:SOFTWARE_RELEASE)-[h:HAS_A {end_date: "2013-12-10 00:00:00"}]->(:SUPPORT_STAGE) 
      RETURN h
      

      RESPONSE SAMPLE

      {
        "results": [
            {
                "end_date": "2013-12-10 00:00:00",
                "modified_at": "2018-05-04 20:01:57",
                "created_at": "2018-05-03 17:29:30"
            }
        ]
      {  
    title: Example two
    language: javascript
  - code_block: |-
      MATCH (srelease:SOFTWARE_RELEASE)-[:HAS_A]->(sver:SOFTWARE_VERSION)-[:HAS_A]->(sprod:SOFTWARE_PRODUCT)-[:HAS_A]->(manu:MANUFACTURER) 
      RETURN srelease.release, sver.version, sprod.product, manu.manufacturer 
      LIMIT 2

      RESPONSE SAMPLE

      {
        "results": [
            {
                "manu.manufacturer": "Callware Technologies",
                "sprod.product": "Callegra .UC",
                "srelease.release": "Callegra .UC",
                "sver.version": "6.14"
            },
            {
                "manu.manufacturer": "Callware Technologies",
                "sprod.product": "Callegra .UC",
                "srelease.release": "Callegra .UC",
                "sver.version": "6.15"
            }
        ]
      {  
    title: Example three
    language: javascript

  - code_block: |-
      MATCH (srelease:SOFTWARE_RELEASE)-[:HAS_A]->(sver:SOFTWARE_VERSION)-[:HAS_A]->(smajor:SOFTWARE_VERSION_GROUP) 
      RETURN srelease.release, sver.version, smajor.version_group 
      LIMIT 5
      
      RESPONSE SAMPLE

      {
        "results": [
            {
                "smajor.version_group": "7",
                "srelease.release": "Archive Services for SAP",
                "sver.version": "7.2"
            },
            {
                "smajor.version_group": "7",
                "srelease.release": "Archive Services for SAP",
                "sver.version": "7.0"
            },
            {
                "smajor.version_group": "6",
                "srelease.release": "ECI (Enterprise Content Integration) Services",
                "sver.version": "6.5"
            },
            {
                "smajor.version_group": "6",
                "srelease.release": "ECI (Enterprise Content Integration) Services",
                "sver.version": "6.0"
            },
            {
                "smajor.version_group": "6",
                "srelease.release": "ECI (Enterprise Content Integration) Services",
                "sver.version": "6.5"
            }
        ]
      {  
    title: Example four
    language: javascript

  - code_block: |-
      MATCH (srelease:SOFTWARE_RELEASE)-[:HAS_A]->(sver:SOFTWARE_VERSION)-[:HAS_A]->(smajor:SOFTWARE_MAJOR_VERSION) 
      RETURN srelease.release, sver.version, smajor.version 
      LIMIT 5
      
      RESPONSE SAMPLE

      {
        "results": [
            {
                "smajor.version": "8.2",
                "srelease.release": "Common Management Information Protocol (CMIP)",
                "sver.version": "8.2.1"
            },
            {
                "smajor.version": "4.0",
                "srelease.release": "Web Proxy Server",
                "sver.version": "4.0.9"
            },
            {
                "smajor.version": "4.0",
                "srelease.release": "Web Proxy Server",
                "sver.version": "4.0.8"
            },
            {
                "smajor.version": "4.0",
                "srelease.release": "Web Proxy Server",
                "sver.version": "4.0.6"
            },
            {
                "smajor.version": "4.0",
                "srelease.release": "Web Proxy Server",
                "sver.version": "4.0.7"
            }
        ]
      {  
        
    title: Example five
    language: javascript

  - code_block: |-
      curl -G -H "Authorization: Bearer b93477a9-057b-4878-a16b93477a9-057b-4878-a16f-d7f7d1f27a7af-d7f7d1f27a7a" "https://v6-1.technopedia.com/tql" --data-urlencode' "q=MATCH (n:SOFTWARE_RELEASE) WHERE n.release contains "studio" RETURN n

      
      
    title: cURL
    language: bash
right_code_blocks:
  - code_block: |-
      technopedia_id
      release
      discontinued_flag
      desupported_flag
      url
      created_at
      modified_at
      
    title: Software Release Attributes
    language: bash
  - code_block: |2-
      (SOFTWARE_RELEASE)-[:HAS_A]->(SOFTWARE_VERSION)

      (SOFTWARE_RELEASE)-[:HAS_A]->(SOFTWARE_EDITION)

      (SOFTWARE_RELEASE)-[:HAS_A]->(SUPPORT_STAGE)
      Relationship attributes: 
      created_at
      modified_at
      end_date

      (SOFTWARE_RELEASE)-[:HAS_A]->(COMPATIBLE_PLATFORM)
      Relationship attributes: 
      status                          
      description
      upgrade_path
      date
       
      (SOFTWARE_RELEASE)-[:HAS_A]->(CERTIFICATION)
      Relationship attributes: 
      certified
    title: Relationships
    language: bash
right_code_blocks:
  - code_block: |2
      technopedia_id
      release
      discontinued_flag
      desupported_flag
      url
      created_at
      modified_at
      
    title: Software Release Attributes
    language: bash
  - code_block: |2-
      (SOFTWARE_RELEASE)-[:HAS_A]->(SOFTWARE_VERSION)

      (SOFTWARE_RELEASE)-[:HAS_A]->(SOFTWARE_EDITION)

      (SOFTWARE_RELEASE)-[:HAS_A]->(SUPPORT_STAGE)
      Relationship attributes: 
      created_at
      modified_at
      end_date

      (SOFTWARE_RELEASE)-[:HAS_A]->(COMPATIBLE_PLATFORM)
      Relationship attributes: 
      status
      description
      upgrade_path
      date
       
      (SOFTWARE_RELEASE)-[:HAS_A]->(CERTIFICATION)
      Relationship attributes: 
      certified
    title: Relationships
    language: bash
---

