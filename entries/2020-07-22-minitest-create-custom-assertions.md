---
title: Minitest create custom assertions
date: 2020-07-22
tags: ruby, minitest
---

To create custom assertions, extend the Minitest::Assertions module

```ruby
require "minitest/assertions"

module Minitest
  module Assertions
    def assert_validation_pass(model, attribute_name)
      model = model.dup
      model.validate
      assert_empty model.errors[attribute_name.to_sym]
    end

    def assert_validation_fail(model, attribute_name)
      model = model.dup
      model.validate
      refute_empty model.errors[attribute_name.to_sym]
    end
  end
end

# Usage

assert_validation_pass(User.new(username: "foo"), :username)
assert_validation_fail(User.new(age: -1), :age)
```

To make assertions work on `expect` style specs, use `Enumerable.infection_an_assertion` on `Minitest::Expectations` module

```ruby
require "minitest/spec"

module Minitest
  module Expectations
    Enumerable.infect_an_assertion :assert_validation_pass, :must_pass_validation_of, true
    Enumerable.infect_an_assertion :assert_validation_fail, :wont_pass_validation_of, true
  end
end

# Usage

expect(User.new(username: "foo")).must_pass_validation_of(:username)
expect(User.new(age: -1).wont_pass_validation_of(:age)
```

`true` at the 3rd argument is to tell Minitest not to flip the arguments on conversion

Ref :

- https://chriskottom.com/blog/2014/08/customize-minitest-assertions-and-expectations/
