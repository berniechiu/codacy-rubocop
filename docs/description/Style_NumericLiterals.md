
This cop checks for big numeric literals without _ between groups
of digits in them.

# Examples

```ruby

# bad
1000000
1_00_000
1_0000

# good
1_000_000
1000
# good
10_000_00 # typical representation of $10,000 in cents
# bad
10_000_00 # typical representation of $10,000 in cents
# good
3000 # You can specify allowed numbers. (e.g. port number)
```

[Source](http://www.rubydoc.info/gems/rubocop/RuboCop/Cop/Style/NumericLiterals)