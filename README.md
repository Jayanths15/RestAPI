# MariaDB Permissions API

A REST API for managing MariaDB table permissions.

## Setup

1. Prerequisites:
   - Java 11+
   - Maven
   - MariaDB

2. Database Setup:
```sql
CREATE DATABASE permissions_db;
CREATE USER 'testuser'@'%' IDENTIFIED BY 'password';
CREATE TABLE permissions_db.users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    username VARCHAR(50) NOT NULL
);
```

3. Run Application:
```bash
mvn spring-boot:run
```

## API Endpoints

1. Grant Permissions:
```bash
curl -X POST http://localhost:8085/permissions/grant \
-H "Content-Type: application/json" \
-d '{
    "username": "testuser",
    "database": "permissions_db",
    "table": "users",
    "permissions": ["SELECT", "INSERT"]
}'
```

2. Revoke Permissions:
```bash
curl -X POST http://localhost:8085/permissions/revoke \
-H "Content-Type: application/json" \
-d '{
    "username": "testuser",
    "database": "permissions_db",
    "table": "users",
    "permissions": ["INSERT"]
}'
```

3. List Permissions:
```bash
curl http://localhost:8085/permissions/testuser
```
```

Would you like me to help you implement any of these remaining features? We can:
1. Add the input validations
2. Create the unit tests
3. Write the README.md
4. Implement the bonus features

