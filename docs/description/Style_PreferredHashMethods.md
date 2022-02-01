
This cop checks for uses of methods `Hash#has_key?` and
`Hash#has_value?`, and suggests using `Hash#key?` and `Hash#value?` instead.

It is configurable to enforce the verbose method names, by using the
`EnforcedStyle: verbose` configuration.

# Examples

```ruby
# bad
Hash#has_key?
Hash#has_value?

# good
Hash#key?
Hash#value?# bad
Hash#key?
Hash#value?

# good
Hash#has_key?
Hash#has_value?
```

[Source](http://www.rubydoc.info/gems/rubocop/RuboCop/Cop/Style/PreferredHashMethods)