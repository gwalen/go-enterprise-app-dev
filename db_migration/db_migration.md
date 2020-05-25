## Db migration tools

Go has very useful package for performing continuous migrations : [golang-migrate/migrate](https://github.com/golang-migrate/migrate)

It applies your migrations ordered by version and breaks on error. You can also define revert migration in case of an error.
Migrate package crates a small table `schema_migrations` in your db where it holds last applied migration and its result (success/fail).
It has **good documentation**.

You can use it from CLI or from code. Syntax is very easy, for example
```
➜  migrate -path migration/ -database "mysql://user:pass@tcp(127.0.0.1:3306)/bettertomorrow?charset=utf8" up
```
will apply all not yet performed migrations from migration directory (relative path) to my MySQL database.

Drivers can run migrations from local and remote sources like :
* Filesystem
* GitHub
* GitLab
* AWS S3
* Google Cloud Storage
* Go-Bindata

It supports bunch of databases:
* PostgreSQL
* Redshift
* Ql
* Cassandra
* MySQL/ MariaDB
* Neo4j
* MongoDB
* Google Cloud Spanner
* CockroachDB
* ClickHouse
* Firebird
* MS SQL Server


#### Conclusion

Mature tool to run migrations.
