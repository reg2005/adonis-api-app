# Adonis API with production-ready docker-compose application

This is the boilerplate for creating an API server in AdonisJs, it comes pre-configured with.

1. Bodyparser
2. Authentication
3. CORS
4. Lucid ORM
5. Migrations and seeds
6. Redis
7. Kue (Queue)
8. Swagger 2 docs (./docs/swagger)

## Setup

Use the adonis command to install the blueprint

```bash
adonis new yardstick --blueprint=https://github.com/reg2005/adonis-api-app
```

## Start
```bash
  docker-compose up -d
```

## Install

```bash
  docker-compose exec app bash -c 'yarn install'
```

## Migrations

Run the following command to run startup migrations.

```bash
  docker-compose exec app bash -c 'adonis migration:run'
```
