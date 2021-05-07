1. run the db and pgadmin instances

   ```
   make up
   ```

2. [set up server and db](https://linuxhint.com/postgresql_docker/)

3. copy the database .tar file to docker volume

   ```
   docker cp dvdrental.tar project-phanpy_db_1:/var/lib/postgresql/data
   ```

   ```
   docker exec project-phanpy_db_1 ls /var/lib/postgresql/data
   ```

4. restore databse from .tar file

   ```
   docker exec project-phanpy_db_1 pg_restore -c -U admin -d dvdrental -v '/var/lib/postgresql/data/dvdrental.tar'
   ```
