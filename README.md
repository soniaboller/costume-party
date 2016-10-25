#costume-party
## 1. SQL COMMANDS for creating database + user
We create a db for every project and a specific user in the db for the project (for security purposes)
```
create database costume_party;
create user 'dba'@'localhost' identified by 'yellowpencil';
grant all privileges on costume_party.* to 'dba'@'localhost';
```

## 2. Environment Variables
Our environment variables are stored in .env but may also be declared as needed
```
DB_USER=dba
DB_PWD=yellowpencil
DB_NAME=costume_party
DB_TYPE=mysql
DB_SERVER=localhost
```

## 3. Database Connect

A database connection is defined inside of db.js. It contains all the information needed to connect to MySQL
```
//./models/db.js
'use strict';

// loads environment variables from .env
require('dotenv').config();

// knex is a databast adapter for node
// npm install knex and npm install logash
// lodash is a dependency of knex and knex will not work without lodash
var db = require('knex')({
    client: process.env.DB_TYPE,
    connection: {
        host: process.env.DB_SERVER,
        user: process.env.DB_USER,
        password: process.env.DB_PWD,
        database: proces.env.DB_NAME
    }
});

module.exports = db;
```
