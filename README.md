#costume-party
## 1. SQL COMMANDS for creating database + user
We create a db for every project and a specific user in the db for the project (for security purposes)
```
create database costume_party;
create user 'dba'@'localhost' identified by 'yellowpencil';
grant all privileges on costume_party.* to 'dba'@'localhost';
```