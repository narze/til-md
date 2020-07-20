---
title: Minitest does not have described_class like rspec
date: 2020-07-20
tags: ruby, testing
---
To make `described_class` work in Minitest, use this snippet.

```ruby
def described_class
  [self.class.desc, *self.class.module_parents].find { |m| m.kind_of?(Class) && m.class != Object }
end
```

Kind of dirty, but works.
