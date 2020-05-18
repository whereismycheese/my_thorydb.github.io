---
layout: post
title:  "jquery cookie"
subtitle:   "-"
categories: jquery
tags: jquery cookie
comments: true
header-img: img/jquery/cookie.jpg
---

[reference here](https://openbase.io/js/jquery.cookie)

```HTML
<script src="js/jquery.cookie.js"></script>
```

## USAGE

Create session cookie:  
`$.cookie('the_cookie', 'the_value');`

Create expiring cookie, 7 days from then:  
`$.cookie('the_cookie', 'the_value', { expires: 7 });`

Create expiring cookie, valid across entire site:  
`$.cookie('the_cookie', 'the_value', { expires: 7, path: '/' });`

Read cookie:  
`$.cookie('the_cookie'); // => "the_value"`  
`$.cookie('not_existing'); // => undefined`

Read all available cookies:  
`$.cookie(); // => { "the_cookie": "the_value", "...remaining": "cookies" }`

Delete cookie:  
// Returns true when cookie was found, false when no cookie was found...
`$.removeCookie('the_cookie');`

// Same path as when the cookie was written...  
`$.removeCookie('the_cookie', { path: '/' });`

Note: when deleting a cookie,  
you must pass the exact same path, domain and secure options  
that were used to set the cookie,  
unless you’re relying on the default options that is.


## CONFIGURATION


## Cookie Options


## Converters
