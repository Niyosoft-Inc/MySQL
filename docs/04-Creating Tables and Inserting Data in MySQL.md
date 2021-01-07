## Creating Tables and Inserting Data in MySQL.

The Scenario
Our company needs a couple more tables in the corporate database. We've got to create them, then insert some data into each one.

Getting Logged In
Use the credentials and server IP in the hands-on lab overview page to log into our lab server. Refer back to that page for other usernames and passwords as we need them.

Surveying the Landscape
Let's get into MySQL and peek around:
```
[cloud_user@host]$ mysql -u root -p

mysql> SHOW DATABASES;
```

This should list out several databases. The one we're going to use is corporate, so from the prompt, type:
```
mysql> USE corporate;
```

Create Tables
Now we're going to create a products table, then an orders table:
```
mysql> CREATE TABLE products (productID INT PRIMARY KEY, productType VARCHAR(50), operatingSystem VARCHAR(50));
mysql> mysql> CREATE TABLE orders (orderID INT PRIMARY KEY, userName VARCHAR(50) UNIQUE, orderType VARCHAR(255), purchaseDate DATE);
```

We can check them both, to see if they got built properly:
```
mysql> DESCRIBE products;
mysql> DESCRIBE orders;
```

Insert Data
Insert Some Products
```
mysql> INSERT INTO products (productID,productType,operatingSystem) VALUES (1,'laptop','ubuntu'),(2,'desktop','windows'),(3,'server','rhel');`
mysql> SELECT * FROM products;
```

The SELECT statement in there will show us whether we got our data inserted properly or not.

Insert Order Data
```
mysql> INSERT INTO orders (orderID,userName,orderType,purchaseDate) VALUES (1,'aaron','laptop','2018-02-23'),(2,'stosh','desktop','2018-01-25'),(3,'kenny','server','2019-12-10');`
mysql> SELECT * FROM orders;
```

We should see three rows of data in the orders table now.

Conclusion
We did it. We created two new database tables, and populated them with some information. Congratulations!
