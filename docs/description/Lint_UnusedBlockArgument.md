
Checks for unused block arguments.

# Examples

```ruby
# bad
do_something do |used, unused|
  puts used
end

do_something do |bar|
  puts :foo
end

define_method(:foo) do |bar|
  puts :baz
end

# good
do_something do |used, _unused|
  puts used
end

do_something do
  puts :foo
end

define_method(:foo) do |_bar|
  puts :baz
end# good
do_something { |unused| }# bad
do_something { |unused| }# bad
do_something do |unused: 42|
  foo
end# good
do_something do |unused: 42|
  foo
end
```

[Source](http://www.rubydoc.info/gems/rubocop/RuboCop/Cop/Lint/UnusedBlockArgument)