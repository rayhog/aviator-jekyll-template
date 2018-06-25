 #### What are the V6.1 API Endpoints?


  To query the Technopedia database you use one of the following two endpoints:


  * `https://v6-1.technopedia.com/tql?q=MATCH <Query Parameters>`
    
    ###### You provide query parameters in the TQL MATCH statement to generate the criteria for your query, as shown in the following example:<br>
    
    GET: `https://v6-1.technopedia.com/tql?q=MATCH (sft:SOFTWARE_PRODUCT) RETURN sft LIMIT 1`<br>

  * `https://v6-1.technopedia.com/technopedia-id/<Technopedia ID>.`
    
    ###### You provide the Technopedia ID for the entity that you're querying to return data for that specific entity. 
    The following example shows a dummy Technopedia ID: <br>
    
    GET: `https://v6-1.technopedia.com/technopedia-id/86-7ytdf89jdjhjsdh87`
   