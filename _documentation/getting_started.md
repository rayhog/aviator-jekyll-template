---
title: Getting Started with version 6 API
position: 1
parameters:
  - name:
    content:
content_markdown: >-
  ** Welcome to our API documentation.**


## This API document is designed for those interested in developing for our
## platform. This API is still under development and is a work in progress

![My logo](/images/logo.svg "my image")


```javascript
function fancyAlert(arg) {
  if(arg) {
    $.facebox({div:'#foo'})
  }
}
```



  | Node Type | Software Category | Software Attributes | Relationships | More
  content |

  | <font size="1"><font color="#333333"><font
  face="Consolas">cat_sw_product_id</font><font
  face="Arial">&nbsp;</font></font></font> | &nbsp; | &nbsp; | &nbsp; | &nbsp; |

  | <font color="#333333"><font face="Consolas"><font size="1">Alerts and
  Monitoring Tools</font></font></font> | &nbsp; | &nbsp; | &nbsp; | &nbsp; |

  | <font color="#333333"><font face="Consolas"><font
  size="1">Analytics</font></font></font> | &nbsp; | &nbsp; | &nbsp; | &nbsp; |

  | <font color="#333333"><font face="Consolas"><font size="1">Anti Virus and
  Malware</font></font></font> | &nbsp; | &nbsp; | &nbsp; | &nbsp; |

  | <font color="#333333"><font face="Consolas"><font size="1">Application
  Architecture and Design</font></font></font> | &nbsp; | &nbsp; | &nbsp; |
  &nbsp; |

  | <font color="#333333"><font face="Consolas"><font size="1">Application
  Servers</font></font></font> | &nbsp; | &nbsp; | &nbsp; | &nbsp; |

  | <font color="#333333"><font face="Consolas"><font size="1">Application
  Testing and QA</font></font></font> | &nbsp; | &nbsp; | &nbsp; | &nbsp; |

  | <font color="#333333"><font face="Consolas"><font size="1">Archiving and
  Content Storage</font></font></font> | &nbsp; | &nbsp; | &nbsp; | &nbsp; |

  | <font color="#333333"><font face="Consolas"><font size="1">Backup and
  Recovery</font></font></font> | &nbsp; | &nbsp; | &nbsp; | &nbsp; |

  | <font color="#333333"><font face="Consolas"><font
  size="1">Banking</font></font></font> | &nbsp; | &nbsp; | &nbsp; | &nbsp; |

  | <font color="#333333"><font face="Consolas"><font size="1">Blogs &amp;
  Wikis</font></font></font> | &nbsp; | &nbsp; | &nbsp; | &nbsp; |

  | <font color="#333333"><font face="Consolas"><font size="1">Business
  Intelligence (BI) Suites</font></font></font> | &nbsp; | &nbsp; | &nbsp; |
  &nbsp; |

  | <font color="#333333"><font face="Consolas"><font size="1">Business Metrics
  and Reporting Tools</font></font></font> | &nbsp; | &nbsp; | &nbsp; | &nbsp; |

  | <font color="#333333"><font face="Consolas"><font size="1">Business
  Performance Management</font></font></font> | &nbsp; | &nbsp; | &nbsp; |
  &nbsp; |


  | &nbsp; | &nbsp; | &nbsp; | &nbsp; | &nbsp; |


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
right_code_blocks:
  - code_block:
    title:
    language:
---