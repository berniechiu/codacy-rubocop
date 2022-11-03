
Checks whether trailing commas in block arguments are
required. Blocks with only one argument and a trailing comma require
that comma to be present. Blocks with more than one argument never
require a trailing comma.

# Examples

```ruby
# bad
add { |foo, bar,| foo + bar }

# good
add { |foo, bar| foo + bar }

# good
add { |foo,| foo }

# good
add { foo }

# bad
add do |foo, bar,|
  foo + bar
end

# good
add do |foo, bar|
  foo + bar
end

# good
add do |foo,|
  foo
end

# good
add do
  foo + bar
end
```

[Source](http://www.rubydoc.info/gems/rubocop/RuboCop/Cop/Style/TrailingCommaInBlockArgs)