## Install and Configure MySQL Server (Ubuntu).

Install and Configure MySQL Server (Ubuntu)
Introduction
MySQL server is one of the most popular and widely-used relational databases. In this Lab, you will be tasked with installing a MySQL server on Ubuntu 18.04, and ensuring that it has been properly secured.

Scenario
As database administrators for our company, we have been tasked with performing the initial installation of a MySQL server. In order to perform this task, we will need to download the appropriate .deb files from the MySQL server downloads page. Once we have obtained the files, we will need to install the MySQL server, update the password for the super user, and ensure that the server has been properly secured. To secure the MySQL server, we will need to make sure that anonymous users are removed, remote root login is disabled, the test database has been removed, and that the privilege tables have been reloaded.

Additional Information:

- All steps should be performed as cloud_user, using sudo when necessary. For convenience, a password is not required when using sudo
- Our working directory should be /home/cloud_user.
- The URL for the MySQL Apt repository configuration file is here: https://dev.mysql.com/get/mysql-apt-config_0.8.12-1_all.deb
- For grading purposes, we will need to update the password for the root user to Linux4me!.

### Get Logged In
Use the credentials and server IP in the hands-on lab overview page to log into our lab server. Once that's done, we can get moving.

Download the MySQL APT Repository Configuration File from the MySQL APT Repository Download Page
While in the cloud_user home directory ( run pwd to make sure we're in /home/cloud_user) and then run the following:
```
[cloud_user@host]$ wget https://dev.mysql.com/get/mysql-apt-config_0.8.12-1_all.deb
```

If we run a quick ls when the file is done downloading, we should see listed here.

Install and Configure the Downloaded Release Package
```
[cloud_user@host]$ sudo dpkg -i mysql-apt-config_0.8.12-1_all.deb
```

During the install and package configuration, make sure that the MySQL server and cluster is set to mysql-8.0, and that the MySQL Tools and Connectors is Enabled.
```
MySQL Server & Cluster (Currently selected: mysql-8.0)
MySQL Tools & Connectors (Currently selected: Enabled)
MySQL Preview Packages (Currently selected: Disabled)
Ok
```

Re-synchronize the Package Index Files.
```
[cloud_user@host]$ sudo apt update
```

Install the MySQL Server and Dependencies Using the apt Command
We'll use the apt command to install the MySQL server and dependencies:
```
[cloud_user@host]$ sudo apt install -y mysql-server
```

When we're prompted, enter Linux4me! as root's MySQL password, then select Use Strong Password Encryption (RECOMMENDED).

Check the MySQL Server Status
It should already be running after the install, but check with systemctl:
```
[cloud_user@host]$ sudo systemctl status mysql
```

Now let's log in as the root user, and enter the root password when we're prompted:
```
[cloud_user@host]$ mysql -u root -p
```

We were just checking, so we can get out of the mysql prompt:
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
Setup VALIDATE PASSWORD component? y
Set the level of the password validation password to STRONG: 2
Change the password for root ? n
Remove anonymous users? y
Disallow root login remotely? y
Remove test database and access to it? y
Reload privilege tables now? y
```


Conclusion
We're finished here. We installed MySQL, and have it set up in a secure state, just like we were asked to do. Congratulations!
