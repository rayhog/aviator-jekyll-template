---
title: CPU
position: 3.2
type: 
description: 
content_markdown: |-
  ###### The CPU node in the Technopedia database stores information that relates to the CPU, such as the model ID, number or cores, and model information. 

  The CPU node is connected to the MANUFACTUER node by the VENDOR_OF relationship, which points toward the CPU node.

  `MATCH (a:CPU) RETURN a.model`
  {: .info}
  
  <br>
    
  
  ![API Image](/images/graph.png){:class="img-responsive"} <br>
  
 
left_code_blocks:
  - code_block: |-
      curl -G -H "Authorization: Bearer b93477a9-057b-4878-a16b93477a9-057b-4878-a16f-d7f7d1f27a7af-d7f7d1f27a7a" "https://v6.technopedia.com/tql" --data-urlencode' "q=MATCH (h:CPU) RETURN h.cores"
    title: cURL Example
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
      (MANUFACTURER)-[:VENDOR_OF]->(CPU)
    title: Relationships
    language: bash
---