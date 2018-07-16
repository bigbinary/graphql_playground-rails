[![Gem Version](https://badge.fury.io/rb/graphql_playground-rails.svg)](https://badge.fury.io/rb/graphql_playground-rails)
# GraphqlPlayground::Rails
A blatant copy of [GraphiQL::Rails](https://github.com/rmosolgo/graphiql-rails) with much less functionality but with [GraphQL Playground](https://github.com/graphcool/graphql-playground) instead.

## Reason for fork
Graphql playground gem uses Rails version 5.1. We had a requirement in one of the project to use the Rails version lesser than 5.1 so we forked to gem [repository](https://github.com/papodaca/graphql_playground-rails) and downgraded the rails version to 5.0.7.


## Installation
Add this line to your application's Gemfile:

```ruby
# GraphQL Playground for query editor in a Rails.
gem 'graphql_playground-rails', github: 'bigbinary/graphql_playground-rails'
```

And then execute:
```bash
$ bundle install
```

### Mount the Engine

Add the engine to `routes.rb`:

```ruby
# config/routes.rb
Rails.application.routes.draw do
  # ...
  if Rails.env.development?
    mount GraphqlPlayground::Rails::Engine, at: "/graphql_playground", graphql_path: "/your/endpoint"
  end
end
```

## Contributing

Submit a PR.

## License
The gem is available as open source under the terms of the [MIT License](https://opensource.org/licenses/MIT).
