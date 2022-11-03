
Identifies places where `fetch(key) { value }`
can be replaced by `fetch(key, value)`.

In such cases `fetch(key, value)` method is faster
than `fetch(key) { value }`.

# Examples

```ruby
# bad
hash.fetch(:key) { 5 }
hash.fetch(:key) { true }
hash.fetch(:key) { nil }
array.fetch(5) { :value }
ENV.fetch(:key) { 'value' }

# good
hash.fetch(:key, 5)
hash.fetch(:key, true)
hash.fetch(:key, nil)
array.fetch(5, :value)
ENV.fetch(:key, 'value')# bad
ENV.fetch(:key) { VALUE }

# good
ENV.fetch(:key, VALUE)
```

[Source](http://www.rubydoc.info/gems/rubocop/RuboCop/Cop/Style/RedundantFetchBlock)