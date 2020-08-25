---
title: Use Hashdiff for comparing arrays or hashes in tests
date: 2020-08-25
tags: ruby
---

`Hashdiff` is a gem which helps visualizing diffs, it can be used in tests too

First install the gem, or include it in Gemfile

```ruby
gem install hashdiff
```

Use to return diff as error in RSpec

```ruby
require "hashdiff"

expect(a_large_hash).to eq(another_hash), -> { Hashdiff.diff(a_large_hash, another_hash, options) }
```

Ref : https://github.com/liufengyun/hashdiff
