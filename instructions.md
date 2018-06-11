## About
This is a well-known sample database from Microsoft that is great for using to practice or learn SQL.

This repo is based on https://github.com/dalers/mywind, and is intended to be simpler for people who are new to SQL and programming in general.

## Installing MySQL

If you don't have MySQL installed yet then this section has a little information to hopefully make it easier.

#### Ubuntu:

If you are running Ubuntu (or a similar flavor of Linux) here is how I installed mine:

```
sudo apt-get install mysql-client mysql-server
sudo mysql_secure_installation
```

For the options probably select: 'No' (to the password plugin, unless you want it), 'No' (since you just set the password), and 'Yes' to the rest.

#### Mac or Windows: 

It looks like you can download installers from their website at this link below:

https://dev.mysql.com/downloads/mysql/

## Installing the sample database

First, open a terminal/command prompt and run mysql:

```
mysql -u root -p
```
(The above command says to use the root user and to prompt you for a password). Then from the mysql command prompt, you need to make the database, select it to use, and confirm that it's the one currently selected by MySQL:

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

Now we create the tables and then insert all the data in. Head over to the data and tables file (raw file [here](https://raw.githubusercontent.com/JamesQuillin/installing-northwind-sample-db-mysql/master/data-and-tables.txt)) and you can just copy/paste the whole thing (it's just a bunch of SQL statements to create tables and insert data). Depending on how the paste works it might execute all of the statements except the last when you paste them since there are line breaks, so make sure you hit [enter] to run the last statement too (the last one is just a SHOW TABLES; statement). 

To see if it worked and there are tables and data, try running a query -- something like:

```
SELECT first_name, last_name, company FROM customers;
```

and you should be able to see the results:

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
