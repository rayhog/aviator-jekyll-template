---
title: Software Release
position: 1.6
type:
description: Get software release data from the Technopedia database.

content_markdown: >-
  `MATCH (a:SOFTWARE_RELEASE) RETURN a.release`

  {: .success} 


  &nbsp;
  
  <br>
  The following diagram shows the nodes, attributes, and relationships that feature in the query example.
  <br>
  ![API Image](/images/sw_rel_to_ver.png){:class="img-responsive"} <br>

  ###### You can paginate by using the parameters listed above.


  <br>The Technopedia Version 6.0 API uses OAuth for
  authentication. To authenticate a session, pass your key in the request
  header. Your API key should have been provided to you by Flexera support. If
  you do not have a key please contact support.
left_code_blocks:
  - code_block: |
      MATCH (n:SOFTWARE_RELEASE) RETURN n.cat_sw_release_id, n.ga_date

      RESPONSE SAMPLE
      {
          
          }

    title: Example 1
    language: javascript
  - code_block: >-
      MATCH (n:SOFTWARE_RELEASE) RETURN n.release, n.created_at LIMIT 2


      RESPONSE SAMPLE

      {
          
          }
    title: Example 2
    language: javascript
  - code_block: |-
      MATCH (srelease:SOFTWARE_RELEASE) -[:HAS_A]->(sver:SOFTWARE_VERSION)-[:HAS_A]->(sprod:SOFTWARE_PRODUCT)-[:HAS_A]->(manu:MANUFACTURER) RETURN srelease.release, sver.version, sprod.product, manu.manufacturer LIMIT 200

      Return release name, software version, software product name, manufacturer name for 200 software releases.

      RESPONSE SAMPLE
      {
          
        }
    title: Example 3
    language: javascript

  - code_block: |-
      MATCH (srelease:SOFTWARE_RELEASE) -[:HAS_A]->(sver:SOFTWARE_VERSION)-[HAS_A]->(smajor:SOFTWARE_VERSION_GROUP) RETURN srelease.release, sver.version, smajor.version_group LIMIT 20

      Return release name, software version and software group version for 2 software releases that have a version and major version group.

      RESPONSE SAMPLE
      {
          
        }
    title: Example 4
    language: javascript

  - code_block: |-
      MATCH (srelease:SOFTWARE_RELEASE) -[:HAS_A]->(sver:SOFTWARE_VERSION)-[HAS_A]->(smajor:SOFTWARE_MAJOR_VERSION) RETURN srelease.release, sver.version, smajor.version_group LIMIT 20

      Return release name, software version and software major version for 2 software releases that have a version and major version group.


      RESPONSE SAMPLE
      {
          
        }
    title: Example 5
    language: javascript

  - code_block: |-
      curl -G -H "Authorization: Bearer b93477a9-057b-4878-a16b93477a9-057b-4878-a16f-d7f7d1f27a7af-d7f7d1f27a7a" "https://v6.technopedia.com/tql" --data-urlencode' "q=MATCH (h:software_release) RETURN h.release"

      
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
      cat_sw_release_id
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

