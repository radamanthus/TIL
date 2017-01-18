## Sidekiq

By default, Sidekiq assumes that Redis is running locally. If Redis is running in a different instance, you need to tell Sidekiq how to find Redis. You can do this by adding a `config/initializers/sidekiq.rb`:


```
redis_config = YAML.load_file(Rails.root + 'config/redis.yml')[Rails.env]

Sidekiq.configure_server do |config|
  config.redis = {
    url: "redis://#{redis_config['host']}:#{redis_config['port']}"
  }
end

Sidekiq.configure_client do |config|
  config.redis = {
    url: "redis://#{redis_config['host']}:#{redis_config['port']}"
  }
end
```

The above code parses `config/redis.yml` to determine the Redis host. The [Redis recipe](https://github.com/engineyard/ey-cookbooks-stable-v5/tree/next-release/examples/redis) automatically creates `/data/<app_name>/shared/config/redis.yml` that points to the correct Redis host.
