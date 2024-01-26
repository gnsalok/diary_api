# Diary API 

A Golang based API which allows user to add entries in the diary.

## Requirement

- Go 1.19 or >
- psql
- PostgreSQL installed on your machine


## Local Development 
1. Prepare the environment variable `.env.local`. To know more details about Postgres, check [Postgres psql](docs/postgres_psql.md)

2. Go to `diary_api` root directory and run `go run main.go`

3. Application starts running on PORT `8000`

4. You can play around the API now.


---
## API Description

### Register User 

```sh
curl -i -H "Content-Type: application/json" \
    -X POST \
    -d '{"username":"<<USERNAME>>", "password":"<<PASSWORD>>"}' \
    http://localhost:8000/auth/register
```
Response :
```sh
    {
    "user": {
        "ID": 1,
        "CreatedAt": "2024-01-26T20:00:25.947058+05:30",
        "UpdatedAt": "2024-01-26T20:00:25.947058+05:30",
        "DeletedAt": null,
        "username": "admin",
        "Entries": null
    }
```

### Login User 

```sh

curl -i -H "Content-Type: application/json" \
    -X POST \
    -d '{"username":"<<USERNAME>>", "password":"<<PASSWORD>>"}' \
    http://localhost:8000/auth/login

```
Response :

```sh

{
    "jwt": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlYXQiOjE3MDYyODM3MzMsImlhdCI6MTcwNjI4MTczMywiaWQiOjF9.YILavz-<example....>"
}
    
```


### Add Entry

```sh

curl -d '{"content":"This is second entry"}' \
    -H "Content-Type: application/json" \
    -H "Authorization: Bearer <<JWT>>" \
    -X POST http://localhost:8000/api/entry

```
Response :

```sh

 {
    "ID": 2,
    "CreatedAt": "2024-01-26T20:41:00.31836+05:30",
    "UpdatedAt": "2024-01-26T20:41:00.31836+05:30",
    "DeletedAt": null,
    "content": "This is second entry",
    "UserID": 1
}
    
```



Happy Coding :)



