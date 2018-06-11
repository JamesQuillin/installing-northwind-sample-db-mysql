# About
This is a well-known sample database from Microsoft that is great for using to practice or learn SQL.

This repo is based on https://github.com/dalers/mywind, and is intended to be simpler for people who are new to SQL and programming in general.

# Installing MySQL:

### Ubuntu:

```
sudo apt-get install mysql-client mysql-server
sudo mysql_secure_installation
```

For the options probably select: 'No' (to the plugin), 'No' (since you just set the password), and 'Yes' to the rest.

### Mac or Windows: 

check out the documentation (sorry I don't use them):

- https://dev.mysql.com/doc/refman/5.7/en/windows-installation.html
- https://dev.mysql.com/doc/refman/5.7/en/osx-installation.html

# Installing the sample database

To start, open a terminal and run mysql with the command:

```
mysql -u root -p
```

Then from the mysql command prompt, you need to make the database, use it, and confirm that it's being used:

```
CREATE DATABASE northwind;
USE northwind;
SELECT DATABASE();
```

Which returns something like:

```
        +------------+
        | database() |
        +------------+
        | northwind  |
        +------------+
        1 row in set (0.00 sec)
```

Now we create the tables and then insert all the data in. Head over to the data and tables file and you can just copy/paste the whole thing (it's just a bunch of sql statements to create tables and insert data). Depending on how the paste works it might execute all of the statements except the last when you paste them since there are line breaks, so make sure you hit [enter] to run the last statement too (the last one is just a SHOW TABLES; statement). To see if it worked try something like:

```
SELECT first_name, last_name, company FROM customers;
```

and you should be able to see some of the data:

```
        +---------------+------------------+------------+
        | first_name    | last_name        | company    |
        +---------------+------------------+------------+
        | Anna          | Bedecs           | Company A  |
        | Antonio       | Gratacos Solsona | Company B  |
        | Thomas        | Axen             | Company C  |
        | Martin        | O’Donnell        | Company E  |
        | Francisco     | Pérez-Olaeta     | Company F  |
        | Ming-Yang     | Xie              | Company G  |
        | Elizabeth     | Andersen         | Company H  |
        | Sven          | Mortensen        | Company I  |
        | Roland        | Wacker           | Company J  |
        | Peter         | Krschne          | Company K  |
        | John          | Edwards          | Company L  |
        | Andre         | Ludick           | Company M  |
        | Carlos        | Grilo            | Company N  |
        | Helena        | Kupkova          | Company O  |
        | Daniel        | Goldschmidt      | Company P  |
        | Jean Philippe | Bagel            | Company Q  |
        | Catherine     | Autier Miconi    | Company R  |
        | Alexander     | Eggerer          | Company S  |
        | George        | Li               | Company T  |
        | Bernard       | Tham             | Company U  |
        | Luciana       | Ramos            | Company V  |
        | Michael       | Entin            | Company W  |
        | Jonas         | Hasselberg       | Company X  |
        | John          | Rodman           | Company Y  |
        | Run           | Liu              | Company Z  |
        | Karen         | Toh              | Company AA |
        | Amritansh     | Raghav           | Company BB |
        | Soo Jung      | Lee              | Company CC |
        +---------------+------------------+------------+
        28 rows in set (0.00 sec)
```
