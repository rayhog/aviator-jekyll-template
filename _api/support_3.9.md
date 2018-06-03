---
title: Support
position: 3.9
type: 
description: >-
 You can access support data from the SUPPORT_STAGE and SUPPORT_POLICY nodes, which are connected to Software and Hardware.

content_markdown: >-
 ###### Much software and hardware is supported by the vendor or manufacturer. In Technopedia, this support is identified a `SUPPORT_STAGE`, which refers to the type of support and the definition attribute provides more detailed information about applicability and timelines.
 
 Many `SUPPORT_STAGES have a `SUPPORT_POLICY` that defines the type of policy, such as standard or Open Source. 
  <br>

  `MATCH (a:SUPPORT_STAGE)-[:HAS_A]-(SUPPORT_POLICY) RETURN a`
  {: .info}
  {: .success}

  The following diagram shows the support nodes and relationships.
  <br>
  ![API Image](/images/support.png){:class="img-responsive"} <br> 

  <br>

  
 
  #### Query Examples <br>
    
  Run any of the MATCH query statements in the examples with the TQL enpoint <br> `https://v6.technopedia.com/tql` in an API client, or use cURL.

left_code_blocks:
  - code_block: |-
      curl -G -H "Authorization: Bearer b93477a9-057b-4878-a16b93477a9-057b-4878-a16f-d7f7d1f27a7af-d7f7d1f27a7a" "https://v6.technopedia.com/tql" --data-urlencode' "q=MATCH (h:SUPPORT_STAGE) RETURN h.stage"










    title: cURL 
    language: bash


  - code_block: >-
      MATCH (n:SUPPORT_STAGE) RETURN n LIMIT 25
        
      RESPONSE SAMPLE

      {
        "results": [
            {
                "technopedia_id": "abc3378a-7eaa-4fa6-94b7-cf5e0b75c57b",
                "created_at": "2010-11-08 10:58:22",
                "modified_at": "2010-11-08 10:58:22",
                "cat_support_policy_id": 16561748,
                "policy": "Standard"
            }
        ]
      {      
          
    title: Example 1
    language: javascript
  - code_block: |-
      MATCH (n:SUPPORT_POLICY) RETURN n LIMIT 25
      
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

    title: Example two
    language: javascript

  - code_block: |-
      MATCH (n:MANUFACTURER)<-[:HAS_A]-(w:SOFTWARE_PRODUCT)-[BELONGS_TO]->(v:CATEGORY_2) RETURN n, w, v

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
      MATCH (n:MANUFACTURER)-[:HAS_A]->(p:SOFTWARE_PRODUCT)-[:HAS_A]->(my_alias:SOFTWARE_VERSION) RETURN n, p, my_alias

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
      curl -G -H "Authorization: Bearer b93477a9-057b-4878-a16b93477a9-057b-4878-a16f-d7f7d1f27a7af-d7f7d1f27a7a" "https://v6.technopedia.com/tql" --data-urlencode' "q=MATCH (h:MANUFACTURER) RETURN h.manufacturer"

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
    language: bash
right_code_blocks:
  - code_block: |2
      SUPPORT_STAGE
      technopedia_id
      support_stage
      order
      created_at
      modified_at
      
      SUPPORT_POLICY
      technopedia_id
      support_policy
      created_at
      modified_at

    title: Support Attributes
    language: bash
  - code_block: |2-
      (SUPPORT_STAGE)-[HAS_A]->[SUPPORT_POLICY]
      
    title: Relationships
    language: bash
---


