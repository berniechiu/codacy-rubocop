
Checks for places where `Integer#even?` or `Integer#odd?`
can be used.

# Examples

```ruby

# bad
if x % 2 == 0
end

# good
if x.even?
end
```

[Source](http://www.rubydoc.info/gems/rubocop/RuboCop/Cop/Style/EvenOdd)