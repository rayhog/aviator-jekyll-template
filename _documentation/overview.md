---
image: /![API Image](/images/logo.png){:class="img-responsive"}
title: Overview
position: 1.01
description: 
content_markdown: |-
  ###### Technopedia version 6 API enables cloud-based access to asset data in Technopedia that provides you with a cloud-first and high-performance resource to manage your assets.<br>
  Technopedia is a Graph database that is designed to process data by using a graph-based methodology, rather than a relational database model.<br>

  <br>
  ###### You query the Technopedia database by using the graph-based Technopedia query language (TQL) to select nodes and attributes of those nodes to define the criteria for your query and return relevant data. 
  <br>
  The following diagram shows an overview of the Technopedia API enpoints, and examples of nodes and relationships in the Technopedia database.
  <br>
  ![API Image](/images/V6api.png){: .img-responsive}
  <br>
  ###### The following query is an example of a GET request by using the Technopedia query language (TQL). TQL uses `MATCH` to select nodes, attributes, and relationships in the Technopedia graph, which is like a `SELECT` statement in SQL. The query selects the software product node and then returns software product names. <br>
  
  `GET:` `https://v6.technopedia.com/tql?=MATCH (n:SOFTWARE_PRODUCT) RETURN n.product` <br>



  #### What’s included in Technopedia V6 API?


  * Graph store organization model that enables Technopedia to store asset data
  from any entity.

  * TQL (Technopedia Query Language) endpoint that you use for graph-based
  querying of the Technopedia database.

  * Technopedia-id endpoint that you use to query any Technopedia product by its ID.


  #### What are the V6 API Endpoints?


  ###### To query the Technopedia database you use one of the following two endpoints:


  * `https://v6-1.technopedia.com/tql?q=MATCH <Query Parameters>`

    ###### You provide query parameters to the MATCH statement to generate the criteria for your query, as shown in the following example:

    ![API Image](/images/get_tql.png){: .img-responsive}

  * `https://v6-1.technopedia.com/technopedia-id/<Technopedia ID>.`

    ###### You provide the Technopedia ID for the product that you're querying to return data for that specific product, as in the following example:

    ![API Image](/images/tid.png){: .img-responsive}

  #### Technopedia graph concepts

  ###### Data storage in Technopedia involves the following concepts:


  * Nodes are Graph data records that are entities in the graph, such as
  software version or hardware.                 
    
  * Nodes contain attributes, which provide data in key-value
  pairs such as `{title: Excel}` or `{manufacturer: Microsoft}`.

  * Nodes are connected by relationships that you use to query multiple nodes in a single query. 

  ###### The following graph shows the Technopedia nodes and relationships:
  
  ![API Image](/images/graph.png){: .img-responsive}<br>&nbsp;

left_code_blocks:
  - code_block: |-
      GET:  https://v6-1.technopedia.com/tql?q=MATCH <Query Parameters>
      GET: https://v6-1.technopedia.com/tql?MATCH (xx:SOFTWARE_PRODUCT) RETURN xx

      GET:  https://v6-1.technopedia.com/technopedia-id/<technopedia_id>
      GET:  https://v6-1.technopedia.com/technopedia-id/4d35ec28-0f16-4787-acca-885679265b59
      
    title: API Query Examples
    language: bash
right_code_blocks:
  - code_block: |2
      https://v6-1.technopedia.com/tql
      https://v6-1.technopedia.com/technopedia-id/
      
      


    title: Technopedia Endpoints
    language: bash
  
---