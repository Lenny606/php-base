# php-base

run docker compose - DEV
```sh
docker compose -f docker-compose.dev.yml up --build -d
```
run docker compose - LOCAL
```sh
docker compose -f docker-compose.dev.yml --env-file .env.local up --build -d
```

copy env files- LOCAL
```sh
cp ./infrastructure/.env.dev ./.env && cp ./infrastructure/.env.local.dev ./.env.local
```
