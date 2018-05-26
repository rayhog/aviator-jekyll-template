---
title: Overview
position: 1.01
type:
description:
content_markdown: >-
  ###### The Technopedia version 6 API enables cloud-based access to asset data in Technopedia that provides you with a cloud-first, high-performance resource to manage your assets.

  ###### You can use the API with TQL (Technopedia query language), which is a graph-based query language that you use to query the Technopedia database. Graph databases are designed to process data by using a graph-based methodology, rather than the relational database model. <br>
  <br>

  ###### You query the Technopedia database by using the graph-based Technopedia query language (TQL) to select nodes and attributes of those nodes to define the criteria for your query and return relevant data. For example, you might query the `SOFTWARE_PRODUCT` node in Technopedia and specify the title attribute becasuse you want to return titles of software products. The following examplE is a TQL query that returns software titles:
  <br>
  `MATCH (s:SOFTWARE_PRODUCT) WHERE title = "Microsoft" RETURN s.title`
  <br>

  ###### The following query is an example of a GET request with a graph query, which is like a `SELECT` statement in SQL, which selects the software node and then returns titles of software products.<br>
  
  `GET:` `https://v6.technopedia.com/tql?MATCH (n:SOFTWARE_PRODUCT) RETURN n.title`<br>



  #### What’s included in Technopedia V6 API?


  * Graph store organization model that enables Technopedia to store asset data
  from any entity.

  * TQL (Technopedia Query Language) endpoint that you use for graph-based
  querying of the Technopedia database.

  * Technopedia-id endpoint that you use to query any Technopedia product by its ID.


  #### What are the V6 API Endpoints?


  ###### To query the Technopedia database you use one of the following two endpoints:


  * `https://v6.technopedia.com/tql?q=MATCH [Query Parameters]`

    ###### You provide query parameters to the MATCH statement to generate the criteria for your query, as shown in the following example:

    ![API Image](/images/get_tql.png){: .img-responsive}

  * `https://v6.technopedia.com/technopedia-id/[Technopedia ID]`

    ###### You provide the Technopedia ID for the product that you're querying to return data for that specific product, as in the following example:

    ![API Image](/images/tid.png){: .img-responsive}

 

left_code_blocks:
  - code_block: |-
      $.get("http://api.myapp.com/books/3", {
        token: "YOUR_APP_KEY",
      }, function(data) {
        alert(data);
      });
    title: jQuery
    language: javascript
right_code_blocks:
  - code_block: |-
      Endpoints   
      
      https://v6.technopedia.com/tql?
      
      https://v6.technopedia.com/technopedia-id/

    title: Technopedia Endpoints
    language: html
  ---