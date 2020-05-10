---
layout: post
title:  "Deep dive in Rails"
date:   2019-09-15 20:10:23 +0800
categories: rails
tags: rails
---
[Ruby on Rails Reading Guide](https://speakerdeck.com/a_matsuda/ruby-on-rails-reading-guide/)

Deep dive in Rails

> Remember to use caller when you get lost in the method call hell.

e.g. in Rails.root/config.ru
```
puts caller
require ::File.expand_path('../config/environment', __FILE__)
run Rails.application
```