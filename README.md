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

## Clone
Use the adonis command to install the blueprint

```bash
git clone --dissociate https://github.com/reg2005/adonis-api-app-with-docker
```

## Think up the url of the application
For example: my-adonis-app.loc
And set it in /etc/hosts

```
127.0.0.1 my-adonis-app.loc
```

## Setup nginx reverse proxy
Please copy ./docker/reverseProxy folder in global env. NginxReverseProxy listen 80 port and proxying traffic to your app.
Use it as one instance!
```bash
  cd yourNginxReverseFolder
  docker-compose up -d
```

## Make environment
Copy .env.example to .env and set variables
1. REAL_URL=my-adonis-app.loc
2. DB_USER=custom_user
3. DB_PASSWORD=custom_password
4. DB_DATABASE-custom_db

## Start
```bash
  docker-compose up -d
```

## Instal dependencies && generate key

```bash
  docker-compose exec app bash -c 'yarn install && adonis key:generate'
```

## Restart conatiners

```bash
  docker-compose restart
```

## Open your app in browser
For example: http://my-adonis-app.loc/

## Migrations

Run the following command to run startup migrations.

```bash
  docker-compose exec app bash -c 'adonis migration:run'
```

## Work inside the container for use specific adonis commands...

Run the following command to run startup migrations.

```bash
  docker-compose exec app bash
```

## View logs

For all containers

```bash
  docker-compose logs -f
```

Or selected container

```bash
  docker-compose logs -f app
```

Troubleshooting
If you get nginx "Not found error":
```bash
  docker-compose restart
```

Or view logs and find bugs
```bash
  docker-compose logs -f web
```
