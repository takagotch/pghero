### pghero
---

https://github.com/ankane/pghero

##### rails
```
gem 'pghero'
mount PgHero::Engine, at: "pghero"
gem 'pg_query', '>=0.9.0'
ENV["PGHERO_USERNAME"] = "link"
ENV["PGHERO_PASSWORD"] = "hyrule"

authenticate :user, -> (user) { user.admin? } do
  mount PgHero::Engine, at: "pghero"
end



```

```
```

```ruby
```

```
```




https://github.com/ankane


```
```

```ruby
```

```
```


