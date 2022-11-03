
Checks for grouping of mixins in `class` and `module` bodies.
By default it enforces mixins to be placed in separate declarations,
but it can be configured to enforce grouping them in one declaration.

# Examples

```ruby
# bad
class Foo
  include Bar, Qox
end

# good
class Foo
  include Qox
  include Bar
end# bad
class Foo
  extend Bar
  extend Qox
end

# good
class Foo
  extend Qox, Bar
end
```

[Source](http://www.rubydoc.info/gems/rubocop/RuboCop/Cop/Style/MixinGrouping)