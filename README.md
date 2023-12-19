## Ports and Adapter GO

![Ports And Adapter Image](https://alistair.cockburn.us/wp-content/uploads/2018/02/Hexagonal-architecture-basic-1.gif)

## Requirements

- Docker
- Docker compose

## How to run

Run docker compose up:

`docker-compose up -d`

After that, we can run a docker exec to create the database:

```
docker exec -it appproduct bash
touch db.sqlite
sqlite3 db.sqlite
```

You are using the sqlite3 cli tool now, please execute the following command

```
CREATE TABLE products (
  id string,
  name string,
  price float,
  status string
);
.exit
```

So now, you can run the application:

```
go run main.go
```

## Running tests

Run docker compose up:

`docker-compose up -d`

After that, we can run a docker exec to create the database:

```
docker exec -it appproduct bash
go mod tidy
go test ./...
```
