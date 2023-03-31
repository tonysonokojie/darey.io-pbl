##WEB STACK IMPLEMENTATION (LEMP STACK)

In this project you will implement a similar stack, but with an alternative Web Server – NGINX, which is also very popular and widely used by many websites in the Internet.

Create a new instance for project 2 and ssh into the instance

Last login: Fri Mar 31 01:23:22 on ttys001
Anthony@Anthonys-MBP ~ % cd downloads/
Anthony@Anthonys-MBP downloads % ssh -i "darey-ec2.pem" ubuntu@ec2-3-142-55-17.us-east-2.compute.amazonaws.com
The authenticity of host 'ec2-3-142-55-17.us-east-2.compute.amazonaws.com (3.142.55.17)' can't be established.
ECDSA key fingerprint is SHA256:PzmvK7ekdyP/DggfJU+leZ1TkXlbFX9RtUOdJ6naG2Y.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added 'ec2-3-142-55-17.us-east-2.compute.amazonaws.com,3.142.55.17' (ECDSA) to the list of known hosts.
Welcome to Ubuntu 22.04.2 LTS (GNU/Linux 5.15.0-1031-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

  System information as of Fri Mar 31 07:39:11 UTC 2023

  System load:  0.5615234375      Processes:             106
  Usage of /:   30.7% of 7.57GB   Users logged in:       0
  Memory usage: 58%               IPv4 address for eth0: 172.31.7.128
  Swap usage:   0%


 * Introducing Expanded Security Maintenance for Applications.
   Receive updates to over 25,000 software packages with your
   Ubuntu Pro subscription. Free for personal use.

     https://ubuntu.com/aws/pro

Expanded Security Maintenance for Applications is not enabled.

7 updates can be applied immediately.
7 of these updates are standard security updates.
To see these additional updates run: apt list --upgradable

Enable ESM Apps to receive additional future security updates.
See https://ubuntu.com/esm or run: sudo pro status


Last login: Fri Mar 31 00:23:42 2023 from 2.31.18.203
ubuntu@ip-172-31-7-128:~$ sudo apt update
Hit:1 http://us-east-2.ec2.archive.ubuntu.com/ubuntu jammy InRelease
Get:2 http://us-east-2.ec2.archive.ubuntu.com/ubuntu jammy-updates InRelease [119 kB]
Get:3 http://us-east-2.ec2.archive.ubuntu.com/ubuntu jammy-backports InRelease [108 kB]
Get:4 http://security.ubuntu.com/ubuntu jammy-security InRelease [110 kB]
Get:5 http://us-east-2.ec2.archive.ubuntu.com/ubuntu jammy-updates/main amd64 Packages [990 kB]
Get:6 http://us-east-2.ec2.archive.ubuntu.com/ubuntu jammy-updates/universe amd64 Packages [898 kB]
Get:7 http://us-east-2.ec2.archive.ubuntu.com/ubuntu jammy-backports/main amd64 Packages [64.0 kB]
Get:8 http://us-east-2.ec2.archive.ubuntu.com/ubuntu jammy-backports/main amd64 c-n-f Metadata [388 B]
Get:9 http://us-east-2.ec2.archive.ubuntu.com/ubuntu jammy-backports/universe amd64 Packages [24.3 kB]
Get:10 http://us-east-2.ec2.archive.ubuntu.com/ubuntu jammy-backports/universe amd64 c-n-f Metadata [480 B]
Fetched 2314 kB in 1s (2298 kB/s)              
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
6 packages can be upgraded. Run 'apt list --upgradable' to see them.
ubuntu@ip-172-31-7-128:~$ sudo apt install nginx
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
nginx is already the newest version (1.18.0-6ubuntu14.3).
0 upgraded, 0 newly installed, 0 to remove and 6 not upgraded.
2 not fully installed or removed.
After this operation, 0 B of additional disk space will be used.
Do you want to continue? [Y/n] Y
Setting up mysql-server-8.0 (8.0.32-0ubuntu0.22.04.2) ...
Renaming removed key_buffer and myisam-recover options (if present)
mysqld will log errors to /var/log/mysql/error.log
mysqld is running as pid 1535
Setting up mysql-server (8.0.32-0ubuntu0.22.04.2) ...
Scanning processes...                                                                                                                                                                                     
Scanning linux images...                                                                                                                                                                                  

Running kernel seems to be up-to-date.

No services need to be restarted.

No containers need to be restarted.

No user sessions are running outdated binaries.

No VM guests are running outdated hypervisor (qemu) binaries on this host.
ubuntu@ip-172-31-7-128:~$ sudo systemctl status nginx
● nginx.service - A high performance web server and a reverse proxy server
     Loaded: loaded (/lib/systemd/system/nginx.service; enabled; vendor preset: enabled)
     Active: active (running) since Fri 2023-03-31 07:37:32 UTC; 13min ago
       Docs: man:nginx(8)
   Main PID: 512 (nginx)
      Tasks: 2 (limit: 1141)
     Memory: 3.6M
        CPU: 30ms
     CGroup: /system.slice/nginx.service
             ├─512 "nginx: master process /usr/sbin/nginx -g daemon on; master_process on;"
             └─516 "nginx: worker process" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" ""

Mar 31 07:37:31 ip-172-31-7-128 systemd[1]: Starting A high performance web server and a reverse proxy server...
Mar 31 07:37:32 ip-172-31-7-128 systemd[1]: Started A high performance web server and a reverse proxy server.
ubuntu@ip-172-31-7-128:~$ curl http://localhost:80
<!DOCTYPE html>
<html>
<head>
<title>Welcome to nginx!</title>
<style>
    body {
        width: 35em;
        margin: 0 auto;
        font-family: Tahoma, Verdana, Arial, sans-serif;
    }
</style>
</head>
<body>
<h1>Welcome to nginx!</h1>
<p>If you see this page, the nginx web server is successfully installed and
working. Further configuration is required.</p>

<p>For online documentation and support please refer to
<a href="http://nginx.org/">nginx.org</a>.<br/>
Commercial support is available at
<a href="http://nginx.com/">nginx.com</a>.</p>

<p><em>Thank you for using nginx.</em></p>
</body>
</html>
ubuntu@ip-172-31-7-128:~$ curl -s http://169.254.169.254/latest/meta-data/public-ipv4
ubuntu@ip-172-31-7-128:~$ sudo apt install mysql-server
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
mysql-server is already the newest version (8.0.32-0ubuntu0.22.04.2).
0 upgraded, 0 newly installed, 0 to remove and 6 not upgraded.
ubuntu@ip-172-31-7-128:~$ sudo mysql
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 8
Server version: 8.0.32-0ubuntu0.22.04.2 (Ubuntu)

Copyright (c) 2000, 2023, Oracle and/or its affiliates.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql> ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'PassWord.1';
Query OK, 0 rows affected (0.03 sec)

mysql> exit
Bye
ubuntu@ip-172-31-7-128:~$ sudo mysql_secure_installation

Securing the MySQL server deployment.

Enter password for user root: 

VALIDATE PASSWORD COMPONENT can be used to test passwords
and improve security. It checks the strength of password
and allows the users to set only those passwords which are
secure enough. Would you like to setup VALIDATE PASSWORD component?

Press y|Y for Yes, any other key for No: y

There are three levels of password validation policy:

LOW    Length >= 8
MEDIUM Length >= 8, numeric, mixed case, and special characters
STRONG Length >= 8, numeric, mixed case, special characters and dictionary                  file

Please enter 0 = LOW, 1 = MEDIUM and 2 = STRONG: 1
Using existing password for root.

Estimated strength of the password: 100 
Change the password for root ? ((Press y|Y for Yes, any other key for No) : y

New password: 

Re-enter new password: 

Estimated strength of the password: 100 
Do you wish to continue with the password provided?(Press y|Y for Yes, any other key for No) : y
By default, a MySQL installation has an anonymous user,
allowing anyone to log into MySQL without having to have
a user account created for them. This is intended only for
testing, and to make the installation go a bit smoother.
You should remove them before moving into a production
environment.

Remove anonymous users? (Press y|Y for Yes, any other key for No) : y
Success.


Normally, root should only be allowed to connect from
'localhost'. This ensures that someone cannot guess at
the root password from the network.

Disallow root login remotely? (Press y|Y for Yes, any other key for No) : y
Success.

By default, MySQL comes with a database named 'test' that
anyone can access. This is also intended only for testing,
and should be removed before moving into a production
environment.


Remove test database and access to it? (Press y|Y for Yes, any other key for No) : y
 - Dropping test database...
Success.

 - Removing privileges on test database...
Success.

Reloading the privilege tables will ensure that all changes
made so far will take effect immediately.

Reload privilege tables now? (Press y|Y for Yes, any other key for No) : y
Success.

All done! 
ubuntu@ip-172-31-7-128:~$ sudo mysql -p
Enter password: 
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 11
Server version: 8.0.32-0ubuntu0.22.04.2 (Ubuntu)

Copyright (c) 2000, 2023, Oracle and/or its affiliates.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql> exit
Bye
ubuntu@ip-172-31-7-128:~$ sudo apt install php-fpm php-mysql
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following additional packages will be installed:
  bzip2 mailcap mime-support php-common php8.1-cli php8.1-common php8.1-fpm
  php8.1-mysql php8.1-opcache php8.1-readline
Suggested packages:
  bzip2-doc php-pear
The following NEW packages will be installed:
  bzip2 mailcap mime-support php-common php-fpm php-mysql php8.1-cli
  php8.1-common php8.1-fpm php8.1-mysql php8.1-opcache php8.1-readline
0 upgraded, 12 newly installed, 0 to remove and 3 not upgraded.
Need to get 5388 kB of archives.
After this operation, 22.2 MB of additional disk space will be used.
Do you want to continue? [Y/n] Y
Get:1 http://us-east-2.ec2.archive.ubuntu.com/ubuntu jammy/main amd64 bzip2 amd64 1.0.8-5build1 [34.8 kB]
Get:2 http://us-east-2.ec2.archive.ubuntu.com/ubuntu jammy/main amd64 mailcap all 3.70+nmu1ubuntu1 [23.8 kB]
Get:3 http://us-east-2.ec2.archive.ubuntu.com/ubuntu jammy/main amd64 mime-support all 3.66 [3696 B]
Get:4 http://us-east-2.ec2.archive.ubuntu.com/ubuntu jammy/main amd64 php-common all 2:92ubuntu1 [12.4 kB]
Get:5 http://us-east-2.ec2.archive.ubuntu.com/ubuntu jammy-updates/main amd64 php8.1-common amd64 8.1.2-1ubuntu2.11 [1126 kB]
Get:6 http://us-east-2.ec2.archive.ubuntu.com/ubuntu jammy-updates/main amd64 php8.1-opcache amd64 8.1.2-1ubuntu2.11 [365 kB]
Get:7 http://us-east-2.ec2.archive.ubuntu.com/ubuntu jammy-updates/main amd64 php8.1-readline amd64 8.1.2-1ubuntu2.11 [13.5 kB]
Get:8 http://us-east-2.ec2.archive.ubuntu.com/ubuntu jammy-updates/main amd64 php8.1-cli amd64 8.1.2-1ubuntu2.11 [1833 kB]
Get:9 http://us-east-2.ec2.archive.ubuntu.com/ubuntu jammy-updates/universe amd64 php8.1-fpm amd64 8.1.2-1ubuntu2.11 [1840 kB]
Get:10 http://us-east-2.ec2.archive.ubuntu.com/ubuntu jammy/universe amd64 php-fpm all 2:8.1+92ubuntu1 [2838 B]
Get:11 http://us-east-2.ec2.archive.ubuntu.com/ubuntu jammy-updates/main amd64 php8.1-mysql amd64 8.1.2-1ubuntu2.11 [130 kB]
Get:12 http://us-east-2.ec2.archive.ubuntu.com/ubuntu jammy/main amd64 php-mysql all 2:8.1+92ubuntu1 [1834 B]
Fetched 5388 kB in 0s (51.8 MB/s)
Selecting previously unselected package bzip2.
(Reading database ... 93884 files and directories currently installed.)
Preparing to unpack .../00-bzip2_1.0.8-5build1_amd64.deb ...
Unpacking bzip2 (1.0.8-5build1) ...
Selecting previously unselected package mailcap.
Preparing to unpack .../01-mailcap_3.70+nmu1ubuntu1_all.deb ...
Unpacking mailcap (3.70+nmu1ubuntu1) ...
Selecting previously unselected package mime-support.
Preparing to unpack .../02-mime-support_3.66_all.deb ...
Unpacking mime-support (3.66) ...
Selecting previously unselected package php-common.
Preparing to unpack .../03-php-common_2%3a92ubuntu1_all.deb ...
Unpacking php-common (2:92ubuntu1) ...
Selecting previously unselected package php8.1-common.
Preparing to unpack .../04-php8.1-common_8.1.2-1ubuntu2.11_amd64.deb ...
Unpacking php8.1-common (8.1.2-1ubuntu2.11) ...
Selecting previously unselected package php8.1-opcache.
Preparing to unpack .../05-php8.1-opcache_8.1.2-1ubuntu2.11_amd64.deb ...
Unpacking php8.1-opcache (8.1.2-1ubuntu2.11) ...
Selecting previously unselected package php8.1-readline.
Preparing to unpack .../06-php8.1-readline_8.1.2-1ubuntu2.11_amd64.deb ...
Unpacking php8.1-readline (8.1.2-1ubuntu2.11) ...
Selecting previously unselected package php8.1-cli.
Preparing to unpack .../07-php8.1-cli_8.1.2-1ubuntu2.11_amd64.deb ...
Unpacking php8.1-cli (8.1.2-1ubuntu2.11) ...
Selecting previously unselected package php8.1-fpm.
Preparing to unpack .../08-php8.1-fpm_8.1.2-1ubuntu2.11_amd64.deb ...
Unpacking php8.1-fpm (8.1.2-1ubuntu2.11) ...
Selecting previously unselected package php-fpm.
Preparing to unpack .../09-php-fpm_2%3a8.1+92ubuntu1_all.deb ...
Unpacking php-fpm (2:8.1+92ubuntu1) ...
Selecting previously unselected package php8.1-mysql.
Preparing to unpack .../10-php8.1-mysql_8.1.2-1ubuntu2.11_amd64.deb ...
Unpacking php8.1-mysql (8.1.2-1ubuntu2.11) ...
Selecting previously unselected package php-mysql.
Preparing to unpack .../11-php-mysql_2%3a8.1+92ubuntu1_all.deb ...
Unpacking php-mysql (2:8.1+92ubuntu1) ...
Setting up php-common (2:92ubuntu1) ...
Created symlink /etc/systemd/system/timers.target.wants/phpsessionclean.timer → /lib/systemd/system/phpsessionclean.timer.
Setting up php8.1-common (8.1.2-1ubuntu2.11) ...

Creating config file /etc/php/8.1/mods-available/calendar.ini with new version

Creating config file /etc/php/8.1/mods-available/ctype.ini with new version

Creating config file /etc/php/8.1/mods-available/exif.ini with new version

Creating config file /etc/php/8.1/mods-available/fileinfo.ini with new version

Creating config file /etc/php/8.1/mods-available/ffi.ini with new version

Creating config file /etc/php/8.1/mods-available/ftp.ini with new version

Creating config file /etc/php/8.1/mods-available/gettext.ini with new version

Creating config file /etc/php/8.1/mods-available/iconv.ini with new version

Creating config file /etc/php/8.1/mods-available/pdo.ini with new version

Creating config file /etc/php/8.1/mods-available/phar.ini with new version

Creating config file /etc/php/8.1/mods-available/posix.ini with new version

Creating config file /etc/php/8.1/mods-available/shmop.ini with new version

Creating config file /etc/php/8.1/mods-available/sockets.ini with new version

Creating config file /etc/php/8.1/mods-available/sysvmsg.ini with new version

Creating config file /etc/php/8.1/mods-available/sysvsem.ini with new version

Creating config file /etc/php/8.1/mods-available/sysvshm.ini with new version

Creating config file /etc/php/8.1/mods-available/tokenizer.ini with new version
Setting up bzip2 (1.0.8-5build1) ...
Setting up php8.1-mysql (8.1.2-1ubuntu2.11) ...

Creating config file /etc/php/8.1/mods-available/mysqlnd.ini with new version

Creating config file /etc/php/8.1/mods-available/mysqli.ini with new version

Creating config file /etc/php/8.1/mods-available/pdo_mysql.ini with new version
Setting up php8.1-readline (8.1.2-1ubuntu2.11) ...

Creating config file /etc/php/8.1/mods-available/readline.ini with new version
Setting up mailcap (3.70+nmu1ubuntu1) ...
Setting up php8.1-opcache (8.1.2-1ubuntu2.11) ...

Creating config file /etc/php/8.1/mods-available/opcache.ini with new version
Setting up php-mysql (2:8.1+92ubuntu1) ...
Setting up mime-support (3.66) ...
Setting up php8.1-cli (8.1.2-1ubuntu2.11) ...
update-alternatives: using /usr/bin/php8.1 to provide /usr/bin/php (php) in auto mode
update-alternatives: using /usr/bin/phar8.1 to provide /usr/bin/phar (phar) in auto mode
update-alternatives: using /usr/bin/phar.phar8.1 to provide /usr/bin/phar.phar (phar.phar) in auto mode

Creating config file /etc/php/8.1/cli/php.ini with new version
Setting up php8.1-fpm (8.1.2-1ubuntu2.11) ...

Creating config file /etc/php/8.1/fpm/php.ini with new version
Created symlink /etc/systemd/system/multi-user.target.wants/php8.1-fpm.service → /lib/systemd/system/php8.1-fpm.service.
Setting up php-fpm (2:8.1+92ubuntu1) ...
Processing triggers for man-db (2.10.2-1) ...
Processing triggers for php8.1-cli (8.1.2-1ubuntu2.11) ...
Processing triggers for php8.1-fpm (8.1.2-1ubuntu2.11) ...
Scanning processes...                                                           
Scanning linux images...                                                        
ubuntu@ip-172-31-7-128:~$ sudo ln -s /etc/nginx/sites-available/projectLEMP /etc/nginx/sites-enabled/
ubuntu@ip-172-31-7-128:~$ sudo nginx -t
nginx: the configuration file /etc/nginx/nginx.conf syntax is ok
nginx: configuration file /etc/nginx/nginx.conf test is successful
ubuntu@ip-172-31-7-128:~$ sudo unlink /etc/nginx/sites-enabled/default
ubuntu@ip-172-31-7-128:~$ sudo systemctl reload nginx
ubuntu@ip-172-31-7-128:~$ sudo echo 'Hello LEMP from hostname' $(curl -s http://169.254.169.254/latest/meta-data/public-hostname) 'with public IP' $(curl -s http://169.254.169.254/latest/meta-data/public-ipv4) > /var/www/projectLEMP/index.html
ubuntu@ip-172-31-7-128:~$ sudo nano /var/www/projectLEMP/info.php
ubuntu@ip-172-31-7-128:~$ sudo rm /var/www/your_domain/info.php
rm: cannot remove '/var/www/your_domain/info.php': No such file or directory
ubuntu@ip-172-31-7-128:~$

ubuntu@ip-172-31-7-128:~$ mysql -u example_user -p
Enter password: 
ERROR 1045 (28000): Access denied for user 'example_user'@'localhost' (using password: YES)
ubuntu@ip-172-31-7-128:~$ mysql -u example_user -p
Enter password: 
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 9
Server version: 8.0.32-0ubuntu0.22.04.2 (Ubuntu)

Copyright (c) 2000, 2023, Oracle and/or its affiliates.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql> mysql> SHOW DATABASES;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'mysql> SHOW DATABASES' at line 1
mysql> show databases;
+--------------------+
| Database           |
+--------------------+
| example_database   |
| information_schema |
| performance_schema |
+--------------------+
3 rows in set (0.00 sec)

mysql> CREATE TABLE example_database.todo_list (
    -> item_id INT AUTO_INCREMENT,
    -> content VARCHAR(255),
    -> PRIMARY KEY(item_id)
    -> );
Query OK, 0 rows affected (0.02 sec)

mysql> INSERT INTO example_database.todo_list (content) VALUES ("My first important item");
Query OK, 1 row affected (0.02 sec)

mysql> SELECT * FROM example_database.todo_list;
+---------+-------------------------+
| item_id | content                 |
+---------+-------------------------+
|       1 | My first important item |
+---------+-------------------------+
1 row in set (0.00 sec)

mysql> exist
    -> ;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'exist' at line 1
mysql> exit
Bye
ubuntu@ip-172-31-7-128:~$ mysql -u example_user -p
Enter password: 
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 10
Server version: 8.0.32-0ubuntu0.22.04.2 (Ubuntu)

Copyright (c) 2000, 2023, Oracle and/or its affiliates.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql> INSERT INTO example_database.todo_list (content) VALUES ("Mysecond important item");
Query OK, 1 row affected (0.00 sec)

mysql> INSERT INTO example_database.todo_list (content) VALUE ("My Third important item");
Query OK, 1 row affected (0.00 sec)

mysql> INSERT INTO Example_database.todo_list (content) VALUE ( "and this one more thing");
ERROR 1142 (42000): INSERT command denied to user 'example_user'@'localhost' for table 'todo_list'
mysql> INSERT INTO example_database.todo_list (content) VALUE ("and this one more thing");
Query OK, 1 row affected (0.01 sec)

mysql> SELECT * FROM example_database.todo_list;
+---------+-------------------------+
| item_id | content                 |
+---------+-------------------------+
|       1 | My first important item |
|       2 | Mysecond important item |
|       3 | My Third important item |
|       4 | and this one more thing |
+---------+-------------------------+
4 rows in set (0.00 sec)

mysql> exit
Bye
ubuntu@ip-172-31-7-128:~$ nano /var/www/projectLEMP/todo_list.php
ubuntu@ip-172-31-7-128:~$ 

<img width="288" alt="Screenshot 2023-03-31 at 15 37 35" src="https://user-images.githubusercontent.com/116417007/229151207-286b7d6c-fbe5-433b-a0df-ede0c2ebc6ef.png">

That means your PHP environment is ready to connect and interact with your MySQL server.

Congratulations!
In this guide, we have built a flexible foundation for serving PHP websites and applications to your visitors, using Nginx as web server and MySQL as database management system.
