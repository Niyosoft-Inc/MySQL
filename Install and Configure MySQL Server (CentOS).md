## Install and Configure MySQL Server (CentOS)

Install and Configure MySQL Server (CentOS)
Introduction
MySQL server is one of the most popular and widely-used relational databases. In this Lab, you will be tasked with installing a MySQL server on CentOS 7, and ensuring that it has been properly secured.

Scenario
As database administrators for our company, we have been tasked with performing the initial installation of a MySQL server. In order to perform this task, we will need to download the appropriate RPM files from the MySQL server downloads page. Once we have obtained the RPM files, we will need to install the MySQL server, update the password for the super user, and ensure that the server has been properly secured. To secure the MySQL server, we will need to make sure that anonymous users are removed, remote root login is disabled, the test database has been removed, and that the privilege tables have been reloaded.

Additional Information:
```
.All steps should be performed as cloud_user, using sudo when necessary. For convenience, a password is not required when using sudo
.Our working directory should be /home/cloud_user.
.The URL for the MySQL RPM Bundle tar file is here: https://dev.mysql.com/get/Downloads/MySQL-8.0/mysql-8.0.15-1.el7.x86_64.rpm-bundle.tar
.For grading purposes, we will need to update the password for the root user to Linux4me!
```
