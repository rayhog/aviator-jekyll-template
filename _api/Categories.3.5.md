---
title: Categories
position: 3.5
type: 
description: 
content_markdown: |-
  ###### Categories are divided into Category Group, Category_1 and Category_2.


  Category nodes are linked by relationships from the software product node.

  
  {: .info}
  
  <br>
    
  
  ![API Image](/images/cat_group.png){:class="img-responsive"} <br>
  
 
left_code_blocks:
  - code_block: |-
      curl -G -H "Authorization: Bearer b93477a9-057b-4878-a16b93477a9-057b-4878-a16f-d7f7d1f27a7af-d7f7d1f27a7a" "https://v6.technopedia.com/tql" --data-urlencode' "q=MATCH (h:CPU) RETURN h.cores"
    title: cURL Example
    language: bash
right_code_blocks:
  - code_block: |2
        label
        description
        




    title: Category_Group_Attributes
    language: bash
  - code_block: |2-
        label
        description
        cat_taxonomy2012_id
        

    title: Category_1 Attributes
    language: bash
  - code_block: |2-
        label
        description
        cat_taxonomy2012_id
       
    title: Category_2 Attributes
    language: bash
---