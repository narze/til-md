---
title: Ruby Struct with :keyword_init option
date: 2020-07-21
tags: ruby
---

Ruby `Struct` is useful, but the keyword has to be defined in order.

```ruby
Person = Struct.new(:name, :age, :gender)
Person.new("Paul", 20, "Male") # Valid
Person.new("Percy", "Female", 18) # Invalid
```

In Ruby 2.5, you can add `keyword_init: true` to support initializing the object with keywords

```ruby
Person = Struct.new(:name, :age, :gender, keyword_init: true)
Person.new(name: "Percy", gender: "Female", age: 18) # Valid
```

It will be easier to understand as well.

Reference : https://www.rubyguides.com/2017/06/ruby-struct-and-openstruct
