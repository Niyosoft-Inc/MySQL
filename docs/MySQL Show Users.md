## MySQL Show Users

Display Only Unique Usernames in MySQL Database.

In some cases, selecting the user table can have duplicate results (e.g. one user for different hosts, but the users have the same name) – this can create clutter, so you may want to display only unique usernames.

If you want to display only unique usernames that won’t be repeated in more rows, you can use;
```
SELECT DISTINCT User FROM mysql.user;
```

No repeated rows, just like we wanted. This can give you a clean look at what users exist on the database server.

## MySQL User table Information.

There are many fields that you could use to see specific properties of your users. With this next command, you’ll be able to see all of the fields that your MySQL server supports.
To see all the fields in the mysql.user table containing a description related to the user table, run the following MySQL command to query the database.
```
desc mysql.user;
```

## For example, if you want to return the list of users and their update privileges, you can run this command:
```
SELECT User, Update_priv FROM mysql.user;
```

Just replace “Update_priv” with any fields that you might need.
