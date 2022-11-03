
Checks for empty else-clauses, possibly including comments and/or an
explicit `nil` depending on the EnforcedStyle.

# Examples

```ruby
# warn on empty else and else with nil in it

# bad
if condition
  statement
else
  nil
end

# bad
if condition
  statement
else
end

# good
if condition
  statement
else
  statement
end

# good
if condition
  statement
end# warn only on empty else

# bad
if condition
  statement
else
end

# good
if condition
  statement
else
  nil
end

# good
if condition
  statement
else
  statement
end

# good
if condition
  statement
end# warn on else with nil in it

# bad
if condition
  statement
else
  nil
end

# good
if condition
  statement
else
end

# good
if condition
  statement
else
  statement
end

# good
if condition
  statement
end
# bad
if condition
  statement
else
  # something comment
  nil
end

# bad
if condition
  statement
else
  # something comment
end
# good
if condition
  statement
else
  # something comment
  nil
end

# good
if condition
  statement
else
  # something comment
end
```

[Source](http://www.rubydoc.info/gems/rubocop/RuboCop/Cop/Style/EmptyElse)