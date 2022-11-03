
Checks the migration for which timestamps are not included
when creating a new table.
In many cases, timestamps are useful information and should be added.

# Examples

```ruby
# bad
create_table :users

# bad
create_table :users do |t|
  t.string :name
  t.string :email
end

# good
create_table :users do |t|
  t.string :name
  t.string :email

  t.timestamps
end

# good
create_table :users do |t|
  t.string :name
  t.string :email

  t.datetime :created_at, default: -> { 'CURRENT_TIMESTAMP' }
end

# good
create_table :users do |t|
  t.string :name
  t.string :email

  t.datetime :updated_at, default: -> { 'CURRENT_TIMESTAMP' }
end
```

[Source](http://www.rubydoc.info/gems/rubocop/RuboCop/Cop/Rails/CreateTableWithTimestamps)