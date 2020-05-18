---
layout: post
title:  "jekyll plugins"
subtitle:   "-"
categories: howTo
tags: howTo jekyll plugins
comments: true
header-img: img/howTo/jekyll.jpg
---

1. download the gem file  
`cmd` gem install [the-plugin-name]

2. list the gem you downloaded to Gemfile  
`Gemfile` gem '[the-plugin-name]'

3. tell jekyll to use that gem  
`_config.yml` plugins:
                - [the-plugin-name]

4. `cmd` bundle update
