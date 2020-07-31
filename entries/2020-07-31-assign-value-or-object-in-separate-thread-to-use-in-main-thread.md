---
title: Assign value or object in separate thread to use in main thread
date: 2020-07-31
tags: ruby
---

Use `Thread.current[]` in the thread and access it in main thread

```ruby
thr = Thread.new {
  ...
  Thread.current["foo"] = "bar"
  ...
}

puts thr["foo"]
#=> "bar"
```

However the value would not be available immediately if the thread is still running.
We can add some wait mechanism eg. `Timeout`

```ruby
Timeout::timeout(5) {
  if thr["foo"]
    puts thr["foo"]
  end
}
```
