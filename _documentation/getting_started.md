---
title: Get Started
position: 1.01
parameters:
  - name:
    content:
content_markdown: |-
# Welcome to our API documentation
  ![API Image](/images/node_table.png){:class="img-responsive"} <br>


## This API document is designed for those interested in developing for our
## platform. This API is still under development and is a work in progress


  You'll succeed if you do this.

  {: .success}


  Here's some useful information.

  {: .info}


  Something may not happen if you try and do this.

  {: .warning}


  Something bad will happen if you do this.

  {: .error}
left_code_blocks:
  - code_block: |
      GET Example

      require 'kittn'

      api = Kittn::APIClient.authorize!('meowmeowmeow')
      api.kittens.get

      import kittn

      api = kittn.authorize('meowmeowmeow')
      api.kittens.get()

      curl "http://example.com/api/kittens"
        -H "Authorization: meowmeowmeow"
    title:
    language:
<!right_code_blocks:
  - code_block:
    title:
    language:-->
---