# Docker, Python, Redis and MySQL

Used this for reference. https://docs.docker.com/compose/gettingstarted/#step-1-setup


    git clone <this-repo>
    
    cd <this-repo>

    docker-compose up --detach


Some example endpoints:

- http://localhost:8080
- http://localhost:8080/api


To Stop Docker containers:

    docker-compose stop


# MySQL:

Connect to the MySQL database from a database client using

    host: localhost
    port: 3306
    user: MY_DB_USER
    pass: MY_DB_PW

Once connected select the database.

```sql
USE MY_DB;
```

Create a simple table.

```sql
CREATE TABLE `USERS` (
    `ID`            INT NOT NULL AUTO_INCREMENT,
    `EMAIL`         VARCHAR(255) DEFAULT NULL,
    `FIRST_NAME`    VARCHAR(255) DEFAULT NULL,
    `LAST_NAME`     VARCHAR(255) DEFAULT NULL,
    
    PRIMARY KEY (`id`),
    UNIQUE KEY `EMAIL_UNIQUE` (`email`)
) 
ENGINE=InnoDB 
AUTO_INCREMENT=2
DEFAULT CHARSET=utf8mb4
COLLATE=utf8mb4_0900_ai_ci;
```

Insert a record.

```sql
INSERT INTO USERS ( 
    EMAIL, 
    FIRST_NAME, 
    LAST_NAME 
) VALUES ( 
    'username@example.com',
    'John', 
    'Doe' 
);
```

Select the records from the table to make sure it's all working.

```sql
SELECT * FROM USERS;
```