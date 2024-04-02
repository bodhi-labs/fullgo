# Project Notes

## init
```shell
❯ cd /Volumes/Mac_Data/Mac_mini/go
❯ cd mkdir fullgo
❯ cd fullgo
❯ code .

```

## git init
```shell
❯ git init

❯ touch .gitignore
# add this line
*node_modules

```
## docker compose 
```shell
❯ touch compose.yaml

```

```yaml
services:
  db:
    container_name: db
    image: postgres:13
    environment:
      POSTGRES_USER: postgres
      POSTGRES_PASSWORD: postgres
      POSTGRES_DB: postgres
    ports:
      - 5432:5432
    volumes:
      - pgdata:/var/lib/postgresql/data

volumes:
  pgdata: {}
```

### Test docker compose
```shell
docker compose up -d db
docker ps -a
```

```shell
docker exec -it db psql -U postgres

postgres=# \l
postgres=# \dt
Did not find any relations.
Use \q to quit.
postgres-# \q
```

## start add backend codes

```shell
mkdir backend 
cd backend

go mod init  api

go get github.com/gorilla/mux github.com/lib/pq

```

```shell
touch main.go go.dockerfile

```
### build Docker compose

```shell
cd ..
docker compose build

docker compose up -d goapp
```

```shell
docker ps -a

```

## frontend

```shell
npx create-next-app@latest --no-git
npm i axios
npm run dev
```

## postgres sql

```shell
postgres=# \dt
         List of relations
 Schema | Name  | Type  |  Owner   
--------+-------+-------+----------
 public | users | table | postgres
(1 row)

postgres=# select * from users;
 id |   name    |        email        
----+-----------+---------------------
  1 | dhamma    | dhamma@gmail.com
  2 | culasubha | culasubha@gmail.com
  3 | bhoga     | bhoga@gmail.com
  4 | gavesaka  | gavesaka@gmail.com
  5 | medinga   | medinga@gmail.com
  ```


### docker file for Nextjs

```shell
touch .dockerignore next.dockerfile
```


### edit next.config.mjs

```mjs
/** @type {import('next').NextConfig} */
const nextConfig = {
  output: 'standalone'
};

export default nextConfig;
```


```shell

docker compose build

docker compose up -d nextapp
```

### stop all container

```shell
docker-compose down
```

