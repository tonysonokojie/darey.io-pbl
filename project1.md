WEB STACK IMPLEMENTATION (LAMP STACK) IN AWS

What is a Technology stack?

A technology stack is a set of frameworks and tools used to develop a software product. This set of frameworks and tools are very specifically chosen to work together in creating a well-functioning software. They are acronymns for individual technologies used together for a specific technology product. some examples are…

LAMP (Linux, Apache, MySQL, PHP or Python, or Perl)
LEMP (Linux, Nginx, MySQL, PHP or Python, or Perl)
MERN (MongoDB, ExpressJS, ReactJS, NodeJS)
MEAN (MongoDB, ExpressJS, AngularJS, NodeJS

#Connecting to EC2 terminal

Anthony@Anthonys-MBP downloads % cd downloads/
cd: no such file or directory: downloads/
Anthony@Anthonys-MBP downloads % ls
AWSCLIV2.pkg
Anthony Okojie's CV-2.docx
Anthony Okojie's CV.docx
CamScanner 12-08-2022 18.45_1.jpg
CamScanner 12-08-2022 18.45_2.jpg
Install Norton Security.localized
Install Norton Security.localized 2
Microsoft_Office_16.65.22091101_BusinessPro_Installer.pkg
Microsoft_Office_16.65.22091101_BusinessPro_Installer.pkg-2.download
OnVUE.app
Postman.app
VirtualBox-7.0.6-155176-OSX.dmg
Zoom.pkg
apache-maven-3.6.3
archive
catpipeline-arch-stage4.pdf
ec2instance.yaml
ec2key.pem
googlechrome.dmg
ideaIC-2020.3.3.dmg
jdk-11.0.10_osx-x64_bin.dmg
payment-receipt.pdf
postgresql-13.2-1-osx.dmg
pycharm-community-2021.3.3.dmg
python-3.10.4-macos11.pkg
saveYourReturn-2.html
saveYourReturn.html
setup.zip
Anthony@Anthonys-MBP downloads % ssh -i "ec2key.pem" ubuntu@ec2-3-138-119-231.us-east-2.compute.amazonaws.com
The authenticity of host 'ec2-3-138-119-231.us-east-2.compute.amazonaws.com (3.138.119.231)' can't be established.
ECDSA key fingerprint is SHA256:Ft3GHgTkN/V4f44y5m96SAYMoKSmPIbG25YLGzGvw5A.
Are you sure you want to continue connecting (yes/no/[fingerprint])? y
Please type 'yes', 'no' or the fingerprint: yes
Warning: Permanently added 'ec2-3-138-119-231.us-east-2.compute.amazonaws.com,3.138.119.231' (ECDSA) to the list of known hosts.
Welcome to Ubuntu 20.04.6 LTS (GNU/Linux 5.15.0-1031-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

  System information as of Thu Mar 30 01:38:16 UTC 2023

  System load:  0.88              Processes:             113
  Usage of /:   33.4% of 7.57GB   Users logged in:       0
  Memory usage: 60%               IPv4 address for eth0: 172.31.2.174
  Swap usage:   0%


Expanded Security Maintenance for Applications is enabled.

7 updates can be applied immediately.
7 of these updates are standard security updates.
To see these additional updates run: apt list --upgradable




Last login: Wed Mar 29 00:54:48 2023 from 2.31.18.203
ubuntu@ip-172-31-2-174:~$ ls
ubuntu@ip-172-31-2-174:~$ ls -la
total 36
drwxr-xr-x 4 ubuntu ubuntu 4096 Mar 29 01:27 .
drwxr-xr-x 3 root   root   4096 Mar 28 21:12 ..
-rw------- 1 ubuntu ubuntu 2027 Mar 29 01:54 .bash_history
-rw-r--r-- 1 ubuntu ubuntu  220 Feb 25  2020 .bash_logout
-rw-r--r-- 1 ubuntu ubuntu 3771 Feb 25  2020 .bashrc
drwx------ 2 ubuntu ubuntu 4096 Mar 28 21:31 .cache
-rw-r--r-- 1 ubuntu ubuntu  807 Feb 25  2020 .profile
drwx------ 2 ubuntu ubuntu 4096 Mar 28 21:12 .ssh
-rw-r--r-- 1 ubuntu ubuntu    0 Mar 28 22:35 .sudo_as_admin_successful
-rw------- 1 ubuntu ubuntu 1777 Mar 29 01:27 .viminfo
ubuntu@ip-172-31-2-174:~$ 

Linux Server in the Cloud

![Screenshot 2023-03-30 at 02 52 04](https://user-images.githubusercontent.com/116417007/228708422-93ef4ce7-5f27-4432-8f0a-c4da5ee7ab45.png)

STEP 1 — INSTALLING APACHE AND UPDATING THE FIREWALL

What exactly is Apache?

Apache HTTP Server is the most widely used web server software. Developed and maintained by Apache Software Foundation, Apache is an open source software available for free. It runs on 67% of all webservers in the world. It is fast, reliable, and secure. It can be highly customized to meet the needs of many different environments by using extensions and modules. Most WordPress hosting providers use Apache as their web server software. However, websites and other applications can run on other web server software as well. Such as Nginx, Microsoft’s IIS, etc.

The Apache web server is among the most popular web servers in the world. It’s well documented, has an active community of users, and has been in wide use for much of the history of the web, which makes it a great default choice for hosting a website.

Install Apache using Ubuntu’s package manager ‘apt’:

ubuntu@ip-172-31-2-174:~$ sudo apt update
Hit:1 http://us-east-2.ec2.archive.ubuntu.com/ubuntu focal InRelease
Get:2 http://us-east-2.ec2.archive.ubuntu.com/ubuntu focal-updates InRelease [114 kB]                
Get:3 http://us-east-2.ec2.archive.ubuntu.com/ubuntu focal-backports InRelease [108 kB]              
Get:4 http://security.ubuntu.com/ubuntu focal-security InRelease [114 kB]                            
Get:5 https://esm.ubuntu.com/apps/ubuntu focal-apps-security InRelease [7556 B]    
Get:6 http://us-east-2.ec2.archive.ubuntu.com/ubuntu focal-updates/main amd64 Packages [2463 kB]
Get:7 https://esm.ubuntu.com/apps/ubuntu focal-apps-updates InRelease [7459 B]
Get:8 http://us-east-2.ec2.archive.ubuntu.com/ubuntu focal-updates/main amd64 c-n-f Metadata [16.4 kB]
Get:9 http://us-east-2.ec2.archive.ubuntu.com/ubuntu focal-updates/restricted amd64 Packages [1714 kB]
Get:10 https://esm.ubuntu.com/infra/ubuntu focal-infra-security InRelease [7453 B]
Get:11 http://us-east-2.ec2.archive.ubuntu.com/ubuntu focal-updates/universe amd64 Packages [1046 kB]
Get:12 https://esm.ubuntu.com/infra/ubuntu focal-infra-updates InRelease [7452 B]
Get:13 http://us-east-2.ec2.archive.ubuntu.com/ubuntu focal-updates/universe Translation-en [246 kB]
Get:14 http://us-east-2.ec2.archive.ubuntu.com/ubuntu focal-updates/universe amd64 c-n-f Metadata [24.1 kB]
Get:15 http://security.ubuntu.com/ubuntu focal-security/main amd64 Packages [2082 kB]
Get:16 http://security.ubuntu.com/ubuntu focal-security/main Translation-en [338 kB]
Get:17 http://security.ubuntu.com/ubuntu focal-security/main amd64 c-n-f Metadata [12.5 kB]
Get:18 http://security.ubuntu.com/ubuntu focal-security/universe amd64 Packages [820 kB]
Get:19 http://security.ubuntu.com/ubuntu focal-security/universe Translation-en [164 kB]
Get:20 http://security.ubuntu.com/ubuntu focal-security/universe amd64 c-n-f Metadata [17.6 kB]
Fetched 9309 kB in 3s (2760 kB/s)                           
Reading package lists... Done
Building dependency tree       
Reading state information... Done
3 packages can be upgraded. Run 'apt list --upgradable' to see them.
ubuntu@ip-172-31-2-174:~$ sudo apt install apache2
Reading package lists... Done
Building dependency tree       
Reading state information... Done
apache2 is already the newest version (2.4.41-4ubuntu3.14).
0 upgraded, 0 newly installed, 0 to remove and 3 not upgraded.
ubuntu@ip-172-31-2-174:~$ sudo systemctl status apache2
● apache2.service - The Apache HTTP Server
     Loaded: loaded (/lib/systemd/system/apache2.service; enabled; vendor preset: enabled)
     Active: active (running) since Thu 2023-03-30 01:36:58 UTC; 36min ago
       Docs: https://httpd.apache.org/docs/2.4/
   Main PID: 604 (apache2)
      Tasks: 6 (limit: 1141)
     Memory: 10.1M
     CGroup: /system.slice/apache2.service
             ├─604 /usr/sbin/apache2 -k start
             ├─632 /usr/sbin/apache2 -k start
             ├─633 /usr/sbin/apache2 -k start
             ├─634 /usr/sbin/apache2 -k start
             ├─657 /usr/sbin/apache2 -k start
             └─658 /usr/sbin/apache2 -k start

Mar 30 01:36:56 ip-172-31-2-174 systemd[1]: Starting The Apache HTTP Server...
Mar 30 01:36:58 ip-172-31-2-174 systemd[1]: Started The Apache HTTP Server.
ubuntu@ip-172-31-2-174:~$ curl -s http://169.254.169.254/latest/meta-data/public-ipv4
3.138.119.231ubuntu@ip-172-31-2-174:~$ 

<img width="1301" alt="Public-IP-Address" src="https://user-images.githubusercontent.com/116417007/228711045-064f0f87-82df-42df-9781-e39d7b4d5dd0.png">

STEP 2 — INSTALLING MYSQL

Now that you have a web server up and running, you need to install a Database Management System (DBMS) to be able to store and manage data for your site in a relational database. MySQL is a popular relational database management system used within PHP environments, so we will use it in our project.

3.138.119.231ubuntu@ip-172 sudo mysql -p
Enter password: 
ERROR 1045 (28000): Access denied for user 'root'@'localhost' (using password: YES)
ubuntu@ip-172-31-2-174:~$ sudo mysql -p
Enter password: 
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 9
Server version: 8.0.32-0ubuntu0.20.04.2 (Ubuntu)

Copyright (c) 2000, 2023, Oracle and/or its affiliates.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql> exit
Bye
ubuntu@ip-172-31-2-174:~$ 

STEP 3 — INSTALLING PHP

You have Apache installed to serve your content and MySQL installed to store and manage your data. PHP is the component of our setup that will process code to display dynamic content to the end user. In addition to the php package, you’ll need php-mysql, a PHP module that allows PHP to communicate with MySQL-based databases. You’ll also need libapache2-mod-php to enable Apache to handle PHP files. Core PHP packages will automatically be installed as dependencies.

To install these 3 packages at once, run:

ubuntu@ip-172-31-2-174:~$ php -v
PHP 7.4.3-4ubuntu2.18 (cli) (built: Feb 23 2023 12:43:23) ( NTS )
Copyright (c) The PHP Group
Zend Engine v3.4.0, Copyright (c) Zend Technologies
    with Zend OPcache v7.4.3-4ubuntu2.18, Copyright (c), by Zend Technologies
ubuntu@ip-172-31-2-174:~$ 

At this point, the LAMP stack is completely installed and fully operational.

Linux (Ubuntu)
Apache HTTP Server
MySQL
PHP

STEP 4 — CREATING A VIRTUAL HOST FOR YOUR WEBSITE USING APACHE

In this project, you will set up a domain called projectlamp, but you can replace this with any domain of your choice.

Apache on Ubuntu 20.04 has one server block enabled by default that is configured to serve documents from the /var/www/html directory.
We will leave this configuration as is and will add our own directory next next to the default one.

Create the directory for projectlamp using ‘mkdir’ command as follows:

ubuntu@ip-172-31-2-174:~$ sudo ls /etc/apache2/sites-available
000-default.conf  default-ssl.conf  projectlamp.conf
ubuntu@ip-172-31-2-174:~$ sudo a2ensite projectlamp
Site projectlamp already enabled
ubuntu@ip-172-31-2-174:~$ sudo apache2ctl configtest
Syntax OK
ubuntu@ip-172-31-2-174:~$ sudo systemctl reload apache2
ubuntu@ip-172-31-2-174:~$ sudo echo 'Hello LAMP from hostname' $(curl -s http://169.254.169.254/latest/meta-data/public-hostname) 'with public IP' $(curl -s http://169.254.169.254/latest/meta-data/public-ipv4) > /var/www/projectlamp/index.html

<img width="793" alt="Screenshot 2023-03-30 at 03 46 42" src="https://user-images.githubusercontent.com/116417007/228715242-de27c8e4-1da7-4f8a-920e-d2eee77a8ae6.png">

<img width="780" alt="Screenshot 2023-03-30 at 04 05 33" src="https://user-images.githubusercontent.com/116417007/228717989-7dd15562-3481-41d8-9039-3a3a91841d44.png">

STEP 5 — ENABLE PHP ON THE WEBSITE

With the default DirectoryIndex settings on Apache, a file named index.html will always take precedence over an index.php file. This is useful for setting up maintenance pages in PHP applications, by creating a temporary index.html file containing an informative message to visitors. Because this page will take precedence over the index.php page, it will then become the landing page for the application. Once maintenance is over, the index.html is renamed or removed from the document root, bringing back the regular application page.

ubuntu@ip-172-31-2-174:~$ sudo vim /etc/apache2/mods-enabled/dir.conf
ubuntu@ip-172-31-2-174:~$ sudo systemctl reload apache2
ubuntu@ip-172-31-2-174:~$ vim /var/www/projectlamp/index.php
ubuntu@ip-172-31-2-174:~$ vim /var/www/projectlamp/index.php

<?php
phpinfo();
~                                                                                                                                                                                                         
~                                                                                                                                                                                                         
~                                                                                                                                                                                                         
~                                                                                                                                                                                                         
~                                                                                                                                                                                                         
~                                                                                                                                                                                                         
~                                                                                                                                                                                                         
~                                                                                                                                                                                                         
~                                                                                                                                                                                                         
~                                                                                                                                                                                                         
~                                                                                                                                                                                                         
~                                                                                                                                                                                                         
~                                                                                                                                                                                                         
~                                                                                                                                                                                                         
~                                                                                                                                                                                                         
~                                                                                                                                                                                                         
~                                                                                                                                                                                                         
~                                                                                                                                                                                                         
~                                                                                                                                                                                                         
~                                                                                                                                                                                                         
~                                                                                                                                                                                                         
~                                                                                                                                                                                                         
~                                                                                                                                                                                                         
~                                                                                                                                                                                                         
~                                                                                                                                                                                                         
~                                                                                                                                                                                                         
~                                                                                                                                                                                                         
~                                                                                                                                                                                                         
~                                                                                                                                                                                                         
~                                                                                                                                                                                                         
~                                                                                                                                                                                                         
~                                                                                                                                                                                                         
~                                                                                                                                                                                                         
~                                                                                                                                                                                                         
~                                                                                                                                                                                                         
~                                                                                                                                                                                                         
~                                                                                                                                                                                                         
~                                                                                                                                                                                                         
~                                                                                                                                                                                                         
~                                                                                                                                                                                                         
~                                                                                                                                                                                                         
~                                                                                                                                                                                                         
~                                                                                                                                                                                                         
~                                                                                                                                                                                                         
~                                                                                                                                                                                                         
~                                                                                                                                                                                                         
~                                                                                                                                                                                                         
~                                                                                                                                                                                                         
~                                                                                                                                                                                                         
~                                                                                                                                                                                                         
~                                                                                                                                                                                                         
~                                                                                                                                                                                                         
~                                                                                                                                                                                                         
~                                                                                                                                                                                                         
~                                                                                                                                                                                                         
~                                                                                                                                                                                                         
~                                                                                                                                                                                                         
~                                                                                                                                                                                                         
~                                                                                                                                                                                                         
~                                                                                                                                                                                                         
"/var/www/projectlamp/index.php" 2L, 17C                                                                                                                                                2,10          All


<img width="780" alt="Screenshot 2023-03-30 at 04 05 33" src="https://user-images.githubusercontent.com/116417007/228717989-7dd15562-3481-41d8-9039-3a3a91841d44.png">

ubuntu@ip-172-31-2-174:~$ sudo rm /var/www/projectlamp/index.php
ubuntu@ip-172-31-2-174:~$ 

REAL LIFE PROJECT by deploying a LAMP stack website in AWS Cloud completed






