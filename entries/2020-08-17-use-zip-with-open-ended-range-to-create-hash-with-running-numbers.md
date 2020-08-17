---
title: Use zip with open-ended range to create hash with running numbers
date: 2020-08-17
tags: ruby
---

```ruby
%[a b c].zip(1..).to_h
#=> { a: 1, b: 2, c: 3 }

# But not the other way around
(1..).zip(%w[a b c]) # Infinite loop!
```
