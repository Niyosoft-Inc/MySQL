## Install and Configure MySQL Server (CentOS)

Install and Configure MySQL Server (CentOS)
Introduction
MySQL server is one of the most popular and widely-used relational databases. In this Lab, you will be tasked with installing a MySQL server on CentOS 7, and ensuring that it has been properly secured.

Scenario
As database administrators for our company, we have been tasked with performing the initial installation of a MySQL server. In order to perform this task, we will need to download the appropriate RPM files from the MySQL server downloads page. Once we have obtained the RPM files, we will need to install the MySQL server, update the password for the super user, and ensure that the server has been properly secured. To secure the MySQL server, we will need to make sure that anonymous users are removed, remote root login is disabled, the test database has been removed, and that the privilege tables have been reloaded.

Additional Information:

- All steps should be performed as cloud_user, using sudo when necessary. For convenience, a password is not required when using sudo
- Our working directory should be /home/cloud_user.
- The URL for the MySQL RPM Bundle tar file is here: https://dev.mysql.com/get/Downloads/MySQL-8.0/mysql-8.0.15-1.el7.x86_64.rpm-bundle.tar
- For grading purposes, we will need to update the password for the root user to Linux4me!

## Get Logged In
Use the credentials and server IP in the hands-on lab overview page to log into our lab server. Once that's done, we can get moving.

Download the MySQL RPM Bundle tar File from the MySQL Community Server Downloads Page
While in the cloud_user home directory ( run pwd to make sure we're in /home/cloud_user) and then run the following:
```
[cloud_user@host]$ wget https://dev.mysql.com/get/Downloads/MySQL-8.0/mysql-8.0.15-1.el7.x86_64.rpm-bundle.tar
```

If we run a quick ls when the file is done downloading, we should see listed here.

Extract the RPM Files from the MySQL Bundle tar File
In the cloud_user’s home directory, Use the tar command to extract the RPM files from the bundle tar file:
```
[cloud_user@host]$ tar -xvf mysql-8.0.15-1.el7.x86_64.rpm-bundle.tar
```

We can run ls again to see everything that got extracted.

Install the MySQL Server and Dependencies Using the rpm Command
In cloud_user’s home directory, use the rpm command to install the MySQL server and dependencies:
```
[cloud_user@host]$ sudo rpm -Uvh mysql-community-{server,client,common,libs}-*
```

Start up the MySQL Server
Use systemctl to start up the mysqld service, and check its state:
```
[cloud_user@host]$ sudo systemctl start mysqld
[cloud_user@host]$ sudo systemctl status mysqld
```

Update the Password for the MySQL Superuser Account
Locate the temporary password for the superuser:
```
[cloud_user@host]$ sudo grep 'temporary password' /var/log/mysqld.log
```

Using the temporary password, log into the MySQL server as the root user:
```
[cloud_user@host]$ # mysql -u root -p
```

Update the password for the root user:
```
mysql> ALTER USER 'root'@'localhost' IDENTIFIED BY '<NEW_PASSWORD>';
```

For grading purposes, make sure NEW_PASSWORD is Linux4me!.

Exit the mysql prompt:
```
mysql> exit
```

Secure the MySQL Server Installation
Begin the installation by running the mysql_secure_installation command:
```
cloud_user@host]$ mysql_secure_installation
```

Answer the following questions to complete the secure installation:
```
Change the password for root ? n
Remove anonymous users? y
Disallow root login remotely? y
Remove test database and access to it? y
Reload privilege tables now? y
```

Conclusion
We're finished here. We installed MySQL, and have it set up in a secure state, just like we were asked to do. Congratulations!
