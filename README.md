### pghero
---

https://github.com/ankane/pghero

##### rails

```ruby
gem 'pghero'
mount PgHero::Engine, at: "pghero"
gem 'pg_query', '>=0.9.0'
ENV["PGHERO_USERNAME"] = "link"
ENV["PGHERO_PASSWORD"] = "hyrule"

authenticate :user, -> (user) { user.admin? } do
  mount PgHero::Engine, at: "pghero"
end

ENV["PGHERO_STATS_DATABASE_URL"]

gem 'aws-sdk-cloudwatch'
gem 'aws-sdk'

PGHERO_ACCESS_KEY_ID=accesskey123
PGHERO_SECRET_ACCESS_KEY=secret123
PGHERO_DB_INSTANCE_IDENTIFIER=epona

```

```sh
rails g pghero:query_stats
rake db:migrate
rake pghero:capture_query_stats
PgHero.capture_query_stats

rails g pghero:space_stats
rake db:migrate
rake pghero:capture_space_stats
PgHero.capture_space_stats

PgHero.long_running_query_sec = 60
PgHero.slow_query_ms = 20
PgHero.slow_query_calls = 100
PgHero.total_connections_threshold = 500
PgHero.explain_timeout_sec = 10

PgHero.running_queries
PgHero.long_running_queries
PgHero.index_usage
PgHero.missing_indexes
PgHero.unused_indexes
PgHero.unused_tables
PgHero.database_size
PgHero.relation_size
PgHero.relation_sizes
PgHero.index_hit_rate
PgHero.table_hit_rate
PgHero.table_hit_rate
PgHero.total_connections
PgHero.locks

PgHero.kill(pid)
PgHero.kill_long_running_queries
PgHero.kill_all

PgHero.query_stats_enbaled?
PgHero.enable_query_stats
PgHero.disable_query_stats
PgHero.reset_query_stats
PgHero.query_stats
PgHero.slow_queries

PgHero.suggested_indexes
PgHero.best_index(query)

PgHero.ssl_used?

PgHero.replica?
PgHero.replication_lag

PgHero.databases["db2"].running_queries

PgHero.create_user("link")

PgHero.create_user("epona", readonly: true)
PgHero.create_user("zelda", password: "hyrule")
PgHero.create_user("navi", tables: ["triforce"])
PgHero.drop_user("ganondorf")

PgHero.databases[].running_queries
PgHero.with(:database2) { PgHero.running_queries }

add_column :pghero_query_stats, :user, :text
add_column :pghero_query_stats, :query_hash, :integer, limit: 8

DROP EXTENSION pg_stat_statements;
CREATE EXTENSION pg_stat_statements;

```

```
{
  "Version": "2012-10-17",
  "Statement": {
    "Effect": "Allow",
    "Action": "cloudwatch:GetMetricStatistics",
    "Resource": "*"
    
  }
}
```

```
# config/pghero.yml
databases:
  primary:
    url: <%= ENV["PGHERO_DATABASE_URL"] %>
  replica:
    url: <%= ENV["REPLICA_DATABASE_URL"] %>

```


###### author
https://github.com/ankane


```
```

```ruby
```

```
```


