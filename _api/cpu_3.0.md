---
title: CPU Model
position: 3.2
type: 
description: 
content_markdown: |-
  ###### The CPU model node in the Technopedia database stores information about CPUs, such as the model ID, number or cores, and model information. 

  The CPU_MODEL node is connected to the MANUFACTURER node by a `HAS_A` relationship, which points from the MANUFACTURER to the CPU node.

  Here's a simple query to return 25 results for CPU models:

  `MATCH (n:CPU_MODEL) RETURN n LIMIT 25`
   {: .info}
  
  <br>
    
  The following diagram shows the CPU node and other nodes.
  <br>
  ![API Image](/images/cpu.png){:class="img-responsive"} <br>
  
  
  #### Query Examples <br>
    
  To use the MATCH statements in the following examples, you append the MATCH statement to the following tql endpoint and run a GET request from a API client or use cURL. <br>
  
  `https://v6-1.technopedia.com/tql?q=<MATCH Statement>`


left_code_blocks:
  - code_block: |
      MATCH (n:CPU_MODEL) RETURN n.isa_bit_mode, n.num_threads

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


    title: Example one
    language: javascript
  - code_block: >-
      MATCH (n:CPU_MODEL) RETURN n.model, n.cores, n.clockrate


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
      MATCH (n:CPU_MODEL)<-[:HAS_A]->(x:MANUFACTURER) RETURN n, x

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
      MATCH (n:CPU_MODEL)<-[:HAS_A]-(x:MANUFACTURER)<-[:HAS_A]- RETURN n.cores, x.manufacturer

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


    title: Example 4
    language: javascript

  - code_block: |-
      MATCH (n:HARDWARE_PRODUCT)<-[e:HAS_A]-(o:MANUFACTURER)-[u:HAS_A]-(y:CPU_MODEL) RETURN n, o, y

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
      curl -G -H "Authorization: Bearer b93477a9-057b-4878-a16b93477a9-057b-4878-a16f-d7f7d1f27a7af-d7f7d1f27a7a" "https://v6.technopedia.com/tql" --data-urlencode' "q=MATCH (h:CPU_MODEL) RETURN h.cores"

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


      
    title: cURL
    language: bash
    

right_code_blocks:
  - code_block: |2
      technopedia_id
      model
      url
      cores
      clock_rate
      isa_bit_mode
      num_threads
      created_at
      modified_at

    title: CPU Attributes
    language: bash
  - code_block: |2-
      (MANUFACTURER)-[:HAS_A]->(CPU_MODEL)
    title: Relationships
    language: bash
---