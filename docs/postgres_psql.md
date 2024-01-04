## Postgres commands

### Pre-requisite 

- Install `Postgres` using homebrew
- Install `psql` which is interface to Postgress.


### Commands
* connect to database : `psql -U aloktripathi -d diary_app`
* Switch to another database : `\c postgres`` (inside prompt)
* Drop the database : `DROP DATABASE your_database;`
* Exit from the prompt : `\q`
* list the database : `psql -l`


Creating DB command :
>`createdb -h <DB_HOSTNAME> -p <DB_PORT> -U <DB_USER> diary_app --password`

Example :

>`createdb -h localhost -p 5432 -U aloktripathi diary_app --password`








