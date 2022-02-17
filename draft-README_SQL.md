
### ` $ date `
```
Tue Dec 21 07:35:58 PM -03 2021
```

### ` $ mysqld --version `
```
/usr/sbin/mysqld  Ver 8.0.27-0ubuntu0.21.10.1 for Linux on x86_64 ((Ubuntu))
```

### ` $ mysqladmin --version `
```
mysqladmin  Ver 8.0.27-0ubuntu0.21.10.1 for Linux on x86_64 ((Ubuntu))
```

### ` $ which mysqld mysqladmin `
```
/usr/sbin/mysqld
/usr/bin/mysqladmin
```
# Editing the my.cnf file:
### Open the my.cnf file in an editor. You can find the my.cnf file in one of the following locations:
### ` $ cat /etc/mysql/my.cnf `
```
#
# The MySQL database server configuration file.
#
# You can copy this to one of:
# - "/etc/mysql/my.cnf" to set global options,
# - "~/.my.cnf" to set user-specific options.
# 
# One can use all long options that the program supports.
# Run program with --help to get a list of available options and with
# --print-defaults to see which it would actually understand and use.
#
# For explanations see
# http://dev.mysql.com/doc/mysql/en/server-system-variables.html

#
# * IMPORTANT: Additional settings that can override those from this file!
#   The files must end with '.cnf', otherwise they'll be ignored.
#

!includedir /etc/mysql/conf.d/
!includedir /etc/mysql/mysql.conf.d/
```
### Set the options max_allowed_packet and innodb_log_file_size in the [mysqld] section to the values shown:
```
[mysqld]
max_allowed_packet=300M
innodb_log_file_size=768M
```
__Note: Ensure that there are no other values for max_allowed_packet and innodb_log_file_size that override the set value.__
### Restart the MySQL service to apply changes.
### ` $ sudo systemctl mysqld restart `
##
Launch the MySQL Command-Line Client. To launch the client, enter the following command in a Command Prompt window: mysql -u root -p . The -p option is needed only if a root password is defined for MySQL. Enter the password when prompted. But I've noticed that the command below means the same.

### ` $ sudo mysql `
```
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 42
Server version: 8.0.27-0ubuntu0.21.10.1 (Ubuntu)

Copyright (c) 2000, 2021, Oracle and/or its affiliates.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql> 
```
