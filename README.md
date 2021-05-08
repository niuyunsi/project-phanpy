# project-phanpy

## Set up PostgreSQL server and pgAdmin

[Quickstart](https://linuxhint.com/postgresql_docker/)

1. run the db server and pgAdmin instances.

   ```
   make up
   ```

2. copy the database .tar file to docker volume.

   ```
   docker cp dvdrental.tar project-phanpy_db_1:/var/lib/postgresql/data
   ```

   ```
   docker exec project-phanpy_db_1 ls /var/lib/postgresql/data
   ```

3. restore databse from .tar file.

   ```
   docker exec project-phanpy_db_1 pg_restore -c -U admin -d dvdrental -v '/var/lib/postgresql/data/dvdrental.tar'
   ```

4. go to `localhost:8080` and use pgAdmin to manage db.

## Use vscode to connect and query (Optional)

[Quickstart](https://docs.microsoft.com/en-us/azure/azure-sql/database/connect-query-vscode)

1. install `PostgreSQL` extension.

2. connect to db server.

3. send query.
