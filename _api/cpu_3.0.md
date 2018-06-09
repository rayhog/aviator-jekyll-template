---
title: CPU Model
position: 3.2
type: 
description: 
content_markdown: |-
  ###### The CPU model node in the Technopedia database stores information about CPUs, such as the model ID, number or cores, and model information. 

  The CPU_MODEL node is connected to the MANUFACTURER node by the `HAS_A` relationship, which points from the MANUFACTURER to the CPU node.

  Here's a simple query to return 25 results for CPU models:

  `MATCH (n:CPU_MODEL) RETURN n LIMIT 25`
   {: .info}
  
  <br>
    
  The following diagram shows the CPU node and other nodes.
  <br>
  ![API Image](/images/cpu.png){:class="img-responsive"} <br>
  
  
  #### Query Examples <br>
    
  To use the MATCH statements in the following examples, you append the MATCH statement to the following tql endpoint and make a GET request from a API client or use cURL. <br>
   <br>
  `https://v6-1.technopedia.com/tql?q=<MATCH Statement>`


left_code_blocks:
  - code_block: |
      MATCH (n:CPU_MODEL) RETURN n

      RESPONSE SAMPLE

      {
        "results": [
            {
                "n.cat_cpu_model_id": 6661614,
                "n.clockrate": null,
                "n.cores": "1",
                "n.created_at": "2009-09-03 08:46:24",
                "n.isa_bit_mode": null,
                "n.model": "HyperSPARC Processor 125 MHz (Colorado 2)",
                "n.modified_at": "2013-08-20 15:36:10",
                "n.num_threads": "1",
                "n.technopedia_id": "528bf55b-0127-456a-9da1-87ad36d28246",
                "n.url": "http://www.sunstuff.org/hardware/mbus/hypersparc.shtml"
            },
            {
                "n.cat_cpu_model_id": 28948499,
                "n.clockrate": null,
                "n.cores": "2",
                "n.created_at": "2012-06-07 08:25:44",
                "n.isa_bit_mode": null,
                "n.model": "Core 2 Duo Mobile Processor 1.50 GHz (Merom)",
                "n.modified_at": "2013-08-20 14:50:42",
                "n.num_threads": "1",
                "n.technopedia_id": "ebb37ac5-4ab0-42e6-9024-acff7b16ac28",
                "n.url": "http://en.wikipedia.org/wiki/List_of_Intel_Core_2_microprocessors"
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
                "n.clockrate": null,
                "n.cores": "1",
                "n.model": "HyperSPARC Processor 125 MHz (Colorado 2)"
            },
            {
                "n.clockrate": null,
                "n.cores": "2",
                "n.model": "Core 2 Duo Mobile Processor 1.50 GHz (Merom)"
            },
            {
                "n.clockrate": null,
                "n.cores": "8",
                "n.model": "Opteron 6134 Processor 2.30 GHz (Magny-Cours)"
            },
            {
                "n.clockrate": null,
                "n.cores": "1",
                "n.model": "Sempron 2200+ Processor 1.50 GHz (Thorton)"
            },
            {
                "n.clockrate": null,
                "n.cores": "1",
                "n.model": "Itanium 2 Processor 9110N 1.60 GHz (Montvale)"
            },
            {
                "n.clockrate": null,
                "n.cores": "1",
                "n.model": "Xeon 3.0E Processor 3.00 GHz (Irwindale)"
            },
            {
                "n.clockrate": null,
                "n.cores": "2",
                "n.model": "Celeron Processor 2.60 GHz"
            }
        ]
      {  

    title: Example two
    language: javascript

  - code_block: |-
      MATCH (h:CPU_MODEL) RETURN h.cores, h.model LIMIT 10

      RESPONSE SAMPLE

      {
        "results": [
            {
            "h.cores": "1",
            "h.model": "HyperSPARC Processor 125 MHz (Colorado 2)"
            },
            {
                "h.cores": "2",
                "h.model": "Core 2 Duo Mobile Processor 1.50 GHz (Merom)"
            },
            {
                "h.cores": "8",
                "h.model": "Opteron 6134 Processor 2.30 GHz (Magny-Cours)"
            },
            {
                "h.cores": "1",
                "h.model": "Sempron 2200+ Processor 1.50 GHz (Thorton)"
            },
            {
                "h.cores": "1",
                "h.model": "Itanium 2 Processor 9110N 1.60 GHz (Montvale)"
            },
            {
                "h.cores": "1",
                "h.model": "Xeon 3.0E Processor 3.00 GHz (Irwindale)"
            },
            {
                "h.cores": "2",
                "h.model": "Celeron Processor 2.60 GHz"
            },
            {
                "h.cores": "12",
                "h.model": "Xeon E7-4830 v3 Processor 2.10 GHz (Haswell-EX)"
            },
            {
                "h.cores": "2",
                "h.model": "Pentium G860 Processor 3.00 GHz (Sandy Bridge)"
            },
            {
                "h.cores": "4",
                "h.model": "Core i7 Mobile Processor 1.73 Ghz (Clarksfield)"
            }
        ]
      {  


    title: Example three
    language: javascript

  - code_block: |-
      MATCH (h:CPU_MODEL) WHERE h.model CONTAINS "125 MHz" AND h.isa_bit_mode = "32" RETURN h.cores, h.model, h.isa_bit_mode

      RESPONSE SAMPLE

      {
        "results": [
            {   "h.cores": "1",
                "h.model": "HyperSPARC Processor 125 MHz (Colorado 2)"
                "h.isa_bit_mode" : "32"
            },
            {
                "h.cores": "1",
                "h.model": "HyperSPARC Processor 125 MHz (Colorado 3)"
                "h.isa_bit_mode" : "32"
            },
            {
                "h.cores": "1",
                "h.model": "Pentium MMX Processor 125 MHz (P54CTB)"
                "h.isa_bit_mode" : "32"
            },
            {
                "h.cores": "1",
                "h.model": "HyperSPARC Processor 125 MHz"
                "h.isa_bit_mode" : "32"
            },
            {
                "h.cores": "1",
                "h.model": "RS64 Processor 125 MHz (Apache)"
                "h.isa_bit_mode" : "32"
            },
            {
                "h.cores": "1",
                "h.model": "PA-7100 Processor 125 MHz (Thunderbird)"
                "h.isa_bit_mode" : "32"
            },
            {
                "h.cores": "1",
                "h.model": "RS64 A25/30 Processor 125 MHz (Muskie)"
                "h.isa_bit_mode" : "32"
            },
            {
                "h.cores": "1",
                "h.model": "PA-7150 Processor 125 MHz (Thunderbird)"
                "h.isa_bit_mode" : "32"
            },
            {
                "h.cores": "1",
                "h.model": "PA-7150 Processor 125 MHz (Thunderbird)"
                "h.isa_bit_mode" : "32"
            },
            {
                "h.cores": "1",
                "h.model": "PA-7100 Processor 125 MHz (Thunderbird)"
                "h.isa_bit_mode" : "32"
            }
        ]
      {  


    title: Example 4
    language: javascript

  - code_block: |-
      MATCH (h:CPU_MODEL) WHERE h.model  <> "125 MHz"  AND h.model <> "3.00 GHz" RETURN h.cores, h.model LIMIT 10

      RESPONSE SAMPLE

      {
        "results": [
            {
                "h.cores": "1",
                "h.model": "HyperSPARC Processor 125 MHz (Colorado 2)"
            },
            {
                "h.cores": "2",
                "h.model": "Core 2 Duo Mobile Processor 1.50 GHz (Merom)"
            },
            {
                "h.cores": "8",
                "h.model": "Opteron 6134 Processor 2.30 GHz (Magny-Cours)"
            },
            {
                "h.cores": "1",
                "h.model": "Sempron 2200+ Processor 1.50 GHz (Thorton)"
            },
            {
                "h.cores": "1",
                "h.model": "Itanium 2 Processor 9110N 1.60 GHz (Montvale)"
            },
            {
                "h.cores": "1",
                "h.model": "Xeon 3.0E Processor 3.00 GHz (Irwindale)"
            },
            {
                "h.cores": "2",
                "h.model": "Celeron Processor 2.60 GHz"
            },
            {
                "h.cores": "12",
                "h.model": "Xeon E7-4830 v3 Processor 2.10 GHz (Haswell-EX)"
            },
            {
                "h.cores": "2",
                "h.model": "Pentium G860 Processor 3.00 GHz (Sandy Bridge)"
            },
            {
                "h.cores": "4",
                "h.model": "Core i7 Mobile Processor 1.73 Ghz (Clarksfield)"
            }
        ]
      {  

    title: Example five
    language: javascript

  - code_block: |-
      curl -G -H "Authorization: Bearer b93477a9-057b-4878-a16b93477a9-057b-4878-a16f-d7f7d1f27a7af-d7f7d1f27a7a" "https://v6.technopedia.com/tql" --data-urlencode' "q=MATCH (h:CPU_MODEL) RETURN h.cores"

       


      
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