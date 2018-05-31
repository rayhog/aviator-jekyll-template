---
title: Categories
position: 3.5
type: 
description: 
content_markdown: |-
  ###### Categories are classified by Category Group, Category_1 and Category_2.


  Category nodes are linked by relationships from the software product node and the hardware product node.
  {: .info}
  
  The following diagaram shows the nodes and relationships for categories:

  ![API Image](/images/cat_group.png){:class="img-responsive"} <br>

  <br>
  ### Category 1
  
  This category node features 
  `MATCH (n:CATEGORY_1) RETURN n LIMIT 25`



  ### Category 2

  This category node features 
  `MATCH (n:CATEGORY_2) RETURN n LIMIT 25`
  


  ### Category Group

  This category node features 
  `MATCH (n:CATEGORY_1) RETURN n LIMIT 25`


    
  
  
  
 
left_code_blocks:
  - code_block: |
      MATCH (n:CATEGORY_1) RETURN n.label LIMIT 5

      RESPONSE SAMPLE
      {
          
          }

    title: Category_1 Example
    language: javascript

  - code_block: >-
      MATCH (n:CATEGORY_2) RETURN n.label, n.description LIMIT 2


      RESPONSE SAMPLE

      {
         
          }
    title: Example 1
    language: javascript

  - code_block: |-
      MATCH (n:CATEGORY_2) WHERE n.label = "Distributed Network Architecture" RETURN n LIMIT 2

      RESPONSE SAMPLE
      {
         
        }
    title: Example 2 
    language: javascript

  - code_block: |- 
      MATCH (n:CATEGORY_2)-[v:CHILD_OF]->(c:CATEGORY_1) RETURN c, n LIMIT 25
      
      Return records for CATEGORY_2 and CATEGORY_1 where CATEGORY_2 has a child of relationship with CATEGORY_1

      RESPONSE SAMPLE
      {
         
        }
    title: Example 3
    language: javascript

  - code_block: |- 
      MATCH (n:CATEGORY_2) WHERE n.label = "Distributed Network Architecture" RETURN n LIMIT 2
      RESPONSE SAMPLE
      {
         
        }
    title: Category_Group Example
    language: javascript

  - code_block: |- 
      MATCH (n:CATEGORY_2) WHERE n.label = "Distributed Network Architecture" RETURN n LIMIT 2
      RESPONSE SAMPLE
      {
         
        }
    title: Category_Group Example
    language: javascript
right_code_blocks:
  - code_block: |2
        label
        description
    title: Category_Group_Attributes
    language: bash

  - code_block: |2-
        technopedia_id
        label
        description
        cat_taxonomy2012_id
        categrory_group
    title: Category_1 Attributes
    language: bash

  - code_block: |2-
        technopedia_id
        label
        description
        cat_taxonomy2012_id
        cat_taxonomy2012_parent_id
    title: Category_2 Attributes
    language: bash
---