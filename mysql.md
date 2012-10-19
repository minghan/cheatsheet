MySQL
=====

Accessing from shell

    mysql --user=root --password
    mysql --user=root --password -p someDB

Basic

    use someDB;
    create database someDB;
    drop database someDB;
    describe someTable;
    show columns from someTable;

Create user

    grant all privileges on mydb.* to mydbuser@localhost identified by 'mydbpassword';
    grant all privileges on mydb.* to mydbuser@% identified by 'mydbpassword';

Backup and Restore

    mysqldump someDB   --user=root --password > backup.sql
    mysql -u root -p someDB < backup.sql
