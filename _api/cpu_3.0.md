---
title: CPU
position: 3.2
type: 
description: 
content_markdown: |-
  ###### The CPU node in the Technopedia database stores information that relates to the CPU, such as the model ID, number or cores, and model information. 

  The CPU node is connected to the MANUFACTURER node by the `HAS_A` relationship, which points from the MANUFACTURER to the CPU node.

  Here's a simple query to return 25 results for CPU models:

  `MATCH (n:CPU_MODEL) RETURN n LIMIT 25`
   {: .info}
  
  <br>
    
  
  ![API Image](/images/graph.png){:class="img-responsive"} <br>
  
 


left_code_blocks:
  - code_block: |
      MATCH (n:CPU) RETURN n.isa_bitmode, n.num_threads

      RESPONSE SAMPLE
      {
          
          }

    title: Example 1
    language: javascript
  - code_block: >-
      MATCH (n:CPU) RETURN n.model, n.cores, n.clockrate


      RESPONSE SAMPLE

      {
          
          }
    title: Example 2
    language: javascript

  - code_block: |-
      MATCH (n:CPU)<-[:HAS_A]->(x:MANUFACTURER) RETURN n, x

      RESPONSE SAMPLE
      {
          
        }
    title: Example 3
    language: javascript

  - code_block: |-
      MATCH (n:CPU)<-[:HAS_A]-(x:MANUFACTURER)<-[:HAS_A]- RETURN n.cores, x.manufacturer

      RESPONSE SAMPLE
      {
          
        }
    title: Example 4
    language: javascript

  - code_block: |-
      MATCH (n:HARDWARE_PRODUCT)<-[e:HAS_A]-(o:MANUFACTURER)-[u:HAS_A]-(y:CPU) RETURN n, o, y

      RESPONSE SAMPLE
      {
          
        }
    title: Example 5
    language: javascript

  - code_block: |-
      curl -G -H "Authorization: Bearer b93477a9-057b-4878-a16b93477a9-057b-4878-a16f-d7f7d1f27a7af-d7f7d1f27a7a" "https://v6.technopedia.com/tql" --data-urlencode' "q=MATCH (h:CPU) RETURN h.cores"

      
    title: cURL
    language: bash
    

right_code_blocks:
  - code_block: |2
      cat_cpu_model_id
      technopedia_id
      model
      url
      cores
      clockrate
      isa_bitmode
      num_threads
      created_at
      modified_at

    title: CPU Attributes
    language: bash
  - code_block: |2-
      (MANUFACTURER)-[:HAS_A]->(CPU)
    title: Relationships
    language: bash
---