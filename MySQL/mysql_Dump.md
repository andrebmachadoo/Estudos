# Dump 

## Backup da estrutura do banco sem os dados

```sh
mysqldump -h host -u user --no-data --database databasename > filename.sql -p
```

A flag ***--no-data*** que permite copiar somente a estrutura do banco de dados.