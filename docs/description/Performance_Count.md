
This cop is used to identify usages of `count` on an `Enumerable` that
follow calls to `select`, `find_all`, `filter` or `reject`. Querying logic can instead be
passed to the `count` call.

# Examples

```ruby
# bad
[1, 2, 3].select { |e| e > 2 }.size
[1, 2, 3].reject { |e| e > 2 }.size
[1, 2, 3].select { |e| e > 2 }.length
[1, 2, 3].reject { |e| e > 2 }.length
[1, 2, 3].select { |e| e > 2 }.count { |e| e.odd? }
[1, 2, 3].reject { |e| e > 2 }.count { |e| e.even? }
array.select(&:value).count

# good
[1, 2, 3].count { |e| e > 2 }
[1, 2, 3].count { |e| e < 2 }
[1, 2, 3].count { |e| e > 2 && e.odd? }
[1, 2, 3].count { |e| e < 2 && e.even? }
Model.select('field AS field_one').count
Model.select(:value).count
```

[Source](http://www.rubydoc.info/gems/rubocop/RuboCop/Cop/Performance/Count)