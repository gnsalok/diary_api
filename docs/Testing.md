## Testing APIs


#### Create Test table 

It will help to create separate table, so that ENG env would not get affected.

```sh
createdb -h localhost -p 5432 -U aloktripathi diary_app_test --password
```


## Commands 

To Run all the test in the same directory 

```go test -v -cover ./controller```

