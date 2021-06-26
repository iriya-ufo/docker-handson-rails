# Docker 勉強会のコード

初期状態の Rails リポジトリを Docker で動かす

## 実行方法

```
$ git clone git@github.com:iriya-ufo/docker-handson-rails.git
$ cd docker-handson-rails
$ touch .env
$ touch config/database.yml
$ docker compose build
$ docker compose up
```

`database.yml` の例を以下に示す

```
default: &default
  adapter:   mysql2
  encoding:  utf8mb4
  reconnect: false
  username: root
  password: root
  host: db

development:
  <<: *default
  database: docker_handson_rails_dev

test:
  <<: *default
  database: docker_handson_rails_test

production:
  <<: *default
  database: docker_handson_rails_prod
```
