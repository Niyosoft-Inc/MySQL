## Creating a Database and Table in MySQL.

The Scenario
We've been asked to clean up some out of date information on the server and to prepare for the upcoming sales year. We'll need to delete the bad_data database, which contains incorrect user information. Then we've got to drop the payment_Info table from the 2004_data database, as it contains sensitive and outdated information. Once the incorrect and outdated information has been removed, we need to create a new database named customer_info and a table within that database called payment_info.

Getting Logged In
Use the credentials and server IP in the hands-on lab overview page to log into our lab server. Refer back to that page for other usernames and passwords as we need them. Once we're logged into the server itself, log into MySQL as root:
```
[cloud_user@host]$ mysql -u root -p
```

We're ready to proceed.

We can run a quick ##SHOW DATABASES; from the mysql prompt, to see what we're dealing with.

Delete a Database from the MySQL Server
This deletes the bad_data database:
```
mysql> DROP DATABASE bad_data;
```

Create a Database
This will create a new database, customer_info
```
mysql> CREATE DATABASE customer_info;
```

Delete a Database Table
There's a payment_info table in the 2004_data database. We've first got to switch to the correct database, then delete (drop) the table. We may want to a peek at the tables before we go actually deleting any, in real life:
```
mysql> USE 2004_data;
mysql> SHOW TABLES;
mysql> DROP TABLE payment_info;
```

Create a Database Table
Change the database to customer_info:
```
mysql> USE customer_info;
```

Create the payment_info table:
```
mysql> CREATE TABLE payment_info (cust_id INT AUTO_INCREMENT PRIMARY KEY, user_name VARCHAR(50) UNIQUE, card_number INT, purchase_item VARCHAR(255));
```

Verify that the table was created as expected:
```
mysql> DESCRIBE payment_info;
```

Exit the mysql prompt:
```
mysql> exit
```

Conclusion
That's it! We got into a MySQL server, dropped a database, then a table, and created another one of each. We're done here. Congratulations!
