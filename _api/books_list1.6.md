---
title: Software Release
position: 1.6
type: 
description: Get software release data from Technopedia
parameters:
  - name: Categories
    content: Category of class
  - name: Relationships
    content: Relationships to other Nodes
content_markdown: |-
  MATCH (SOFTWARE_VERSION:a) RETURN a
  {: .info }
  <br>
  ###### You can paginate by using the parameters listed above.
  Lists all the photos you have access to. You can paginate by using the parameters listed above.<br>
  ![API Image](/images/apiEcon.png){:class="img-responsive"} 
  <br> The Technopedia Version 6.0 API uses OAuth for authentication. To authenticate a session, pass your key in the request header. 
  Your API key should have been provided to you by Flexera support. If you do not have a key please contact support.

left_code_blocks:
  - code_block: |-
      $.get("http://api.myapp.com/books/", { "token": "YOUR_APP_KEY"}, function(data) {
        alert(data);
      });
    title: jQuery
    language: javascript
  - code_block: |-
      r = requests.get("http://api.myapp.com/books/", token="YOUR_APP_KEY")
      print r.text
    title: Python
    language: python
  - code_block: |-
      var request = require("request");
      request("http://api.myapp.com/books?token=YOUR_APP_KEY", function (error, response, body) {
      if (!error && response.statusCode == 200) {
        console.log(body);
      }
    title: Node.js
    language: javascript
  - code_block: |-
      curl http://sampleapi.readme.com/orders?key=YOUR_APP_KEY
    title: Curl
    language: bash
right_code_blocks:
  - code_block: |2-
      [
        {
          "id": 1,
          "title": "The Hunger Games",
          "score": 4.5,
          "dateAdded": "12/12/2013"
        },
        {
          "id": 1,
          "title": "The Hunger Games",
          "score": 4.7,
          "dateAdded": "15/12/2013"
        },
      ]
    title: Response
    language: json
  - code_block: |2-
      {
        "error": true,
        "message": "Invalid offset"
      }
    title: Error
    language: json
---