
Anthony@Anthonys-MBP downloads % ssh -i "darey-ec2.pem" ubuntu@ec2-3-16-47-6.us-east-2.compute.amazonaws.com
The authenticity of host 'ec2-3-16-47-6.us-east-2.compute.amazonaws.com (3.16.47.6)' can't be established.
ECDSA key fingerprint is SHA256:DpP9Nks+F+dEOpqaJv2Nk6tPRblqIjK8jZA9NnuyFQg.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added 'ec2-3-16-47-6.us-east-2.compute.amazonaws.com,3.16.47.6' (ECDSA) to the list of known hosts.
Welcome to Ubuntu 22.04.2 LTS (GNU/Linux 5.15.0-1031-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

  System information as of Sat Apr  1 17:07:43 UTC 2023

  System load:  0.498046875       Processes:             102
  Usage of /:   20.2% of 7.57GB   Users logged in:       0
  Memory usage: 20%               IPv4 address for eth0: 172.31.8.86
  Swap usage:   0%

Expanded Security Maintenance for Applications is not enabled.

0 updates can be applied immediately.

Enable ESM Apps to receive additional future security updates.
See https://ubuntu.com/esm or run: sudo pro status


The list of available updates is more than a week old.
To check for new updates run: sudo apt update


The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.

To run a command as administrator (user "root"), use "sudo <command>".
See "man sudo_root" for details.

ubuntu@ip-172-31-8-86:~$ sudo apt update
Hit:1 http://us-east-2.ec2.archive.ubuntu.com/ubuntu jammy InRelease
Get:2 http://us-east-2.ec2.archive.ubuntu.com/ubuntu jammy-updates InRelease [119 kB]
Get:3 http://us-east-2.ec2.archive.ubuntu.com/ubuntu jammy-backports InRelease [108 kB]
Get:4 http://security.ubuntu.com/ubuntu jammy-security InRelease [110 kB]  
Get:5 http://us-east-2.ec2.archive.ubuntu.com/ubuntu jammy/universe amd64 Packages [14.1 MB]
Get:6 http://us-east-2.ec2.archive.ubuntu.com/ubuntu jammy/universe Translation-en [5652 kB]
Get:7 http://us-east-2.ec2.archive.ubuntu.com/ubuntu jammy/universe amd64 c-n-f Metadata [286 kB]
Get:8 http://us-east-2.ec2.archive.ubuntu.com/ubuntu jammy/multiverse amd64 Packages [217 kB]
Get:9 http://us-east-2.ec2.archive.ubuntu.com/ubuntu jammy/multiverse Translation-en [112 kB]
Get:10 http://us-east-2.ec2.archive.ubuntu.com/ubuntu jammy/multiverse amd64 c-n-f Metadata [8372 B]
Get:11 http://us-east-2.ec2.archive.ubuntu.com/ubuntu jammy-updates/main amd64 Packages [989 kB]
Get:12 http://us-east-2.ec2.archive.ubuntu.com/ubuntu jammy-updates/main Translation-en [210 kB]
Get:13 http://us-east-2.ec2.archive.ubuntu.com/ubuntu jammy-updates/main amd64 c-n-f Metadata [13.9 kB]
Get:14 http://us-east-2.ec2.archive.ubuntu.com/ubuntu jammy-updates/restricted amd64 Packages [743 kB]
Get:15 http://us-east-2.ec2.archive.ubuntu.com/ubuntu jammy-updates/restricted Translation-en [115 kB]
Get:16 http://us-east-2.ec2.archive.ubuntu.com/ubuntu jammy-updates/restricted amd64 c-n-f Metadata [588 B]
Get:17 http://us-east-2.ec2.archive.ubuntu.com/ubuntu jammy-updates/universe amd64 Packages [898 kB]
Get:18 http://us-east-2.ec2.archive.ubuntu.com/ubuntu jammy-updates/universe Translation-en [180 kB]
Get:19 http://us-east-2.ec2.archive.ubuntu.com/ubuntu jammy-updates/universe amd64 c-n-f Metadata [18.5 kB]
Get:20 http://us-east-2.ec2.archive.ubuntu.com/ubuntu jammy-updates/multiverse amd64 Packages [24.1 kB]
Get:21 http://us-east-2.ec2.archive.ubuntu.com/ubuntu jammy-updates/multiverse Translation-en [6312 B]
Get:22 http://us-east-2.ec2.archive.ubuntu.com/ubuntu jammy-updates/multiverse amd64 c-n-f Metadata [444 B]
Get:23 http://us-east-2.ec2.archive.ubuntu.com/ubuntu jammy-backports/main amd64 Packages [40.6 kB]
Get:24 http://us-east-2.ec2.archive.ubuntu.com/ubuntu jammy-backports/main Translation-en [9800 B]
Get:25 http://us-east-2.ec2.archive.ubuntu.com/ubuntu jammy-backports/main amd64 c-n-f Metadata [388 B]
Get:26 http://us-east-2.ec2.archive.ubuntu.com/ubuntu jammy-backports/restricted amd64 c-n-f Metadata [116 B]
Get:27 http://us-east-2.ec2.archive.ubuntu.com/ubuntu jammy-backports/universe amd64 Packages [20.3 kB]
Get:28 http://us-east-2.ec2.archive.ubuntu.com/ubuntu jammy-backports/universe Translation-en [14.4 kB]
Get:29 http://us-east-2.ec2.archive.ubuntu.com/ubuntu jammy-backports/universe amd64 c-n-f Metadata [480 B]
Get:30 http://us-east-2.ec2.archive.ubuntu.com/ubuntu jammy-backports/multiverse amd64 c-n-f Metadata [116 B]
Get:31 http://security.ubuntu.com/ubuntu jammy-security/main amd64 Packages [728 kB]
Get:32 http://security.ubuntu.com/ubuntu jammy-security/main Translation-en [147 kB]
Get:33 http://security.ubuntu.com/ubuntu jammy-security/main amd64 c-n-f Metadata [9016 B]
Get:34 http://security.ubuntu.com/ubuntu jammy-security/restricted amd64 Packages [701 kB]
Get:35 http://security.ubuntu.com/ubuntu jammy-security/restricted Translation-en [109 kB]
Get:36 http://security.ubuntu.com/ubuntu jammy-security/restricted amd64 c-n-f Metadata [588 B]
Get:37 http://security.ubuntu.com/ubuntu jammy-security/universe amd64 Packages [715 kB]
Get:38 http://security.ubuntu.com/ubuntu jammy-security/universe Translation-en [118 kB]
Get:39 http://security.ubuntu.com/ubuntu jammy-security/universe amd64 c-n-f Metadata [14.1 kB]
Get:40 http://security.ubuntu.com/ubuntu jammy-security/multiverse amd64 Packages [19.4 kB]
Get:41 http://security.ubuntu.com/ubuntu jammy-security/multiverse Translation-en [4068 B]
Get:42 http://security.ubuntu.com/ubuntu jammy-security/multiverse amd64 c-n-f Metadata [228 B]
Fetched 26.6 MB in 5s (5741 kB/s)               
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
6 packages can be upgraded. Run 'apt list --upgradable' to see them.
ubuntu@ip-172-31-8-86:~$ sudo apt upgrade
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
Calculating upgrade... Done
The following NEW packages will be installed:
  linux-aws-5.19-headers-5.19.0-1022 linux-headers-5.19.0-1022-aws linux-image-5.19.0-1022-aws linux-modules-5.19.0-1022-aws
The following packages will be upgraded:
  bind9-dnsutils bind9-host bind9-libs linux-aws linux-headers-aws linux-image-aws
6 upgraded, 4 newly installed, 0 to remove and 0 not upgraded.
3 standard LTS security updates
Need to get 54.2 MB of archives.
After this operation, 282 MB of additional disk space will be used.
Do you want to continue? [Y/n] Y
Get:1 http://us-east-2.ec2.archive.ubuntu.com/ubuntu jammy-updates/main amd64 bind9-host amd64 1:9.18.12-0ubuntu0.22.04.1 [52.4 kB]
Get:2 http://us-east-2.ec2.archive.ubuntu.com/ubuntu jammy-updates/main amd64 bind9-dnsutils amd64 1:9.18.12-0ubuntu0.22.04.1 [157 kB]
Get:3 http://us-east-2.ec2.archive.ubuntu.com/ubuntu jammy-updates/main amd64 bind9-libs amd64 1:9.18.12-0ubuntu0.22.04.1 [1240 kB]
Get:4 http://us-east-2.ec2.archive.ubuntu.com/ubuntu jammy-updates/main amd64 linux-modules-5.19.0-1022-aws amd64 5.19.0-1022.23~22.04.1 [24.7 MB]
Get:5 http://us-east-2.ec2.archive.ubuntu.com/ubuntu jammy-updates/main amd64 linux-image-5.19.0-1022-aws amd64 5.19.0-1022.23~22.04.1 [12.0 MB]
Get:6 http://us-east-2.ec2.archive.ubuntu.com/ubuntu jammy-updates/main amd64 linux-aws amd64 5.19.0.1022.23~22.04.6 [1726 B]
Get:7 http://us-east-2.ec2.archive.ubuntu.com/ubuntu jammy-updates/main amd64 linux-image-aws amd64 5.19.0.1022.23~22.04.6 [2306 B]
Get:8 http://us-east-2.ec2.archive.ubuntu.com/ubuntu jammy-updates/main amd64 linux-aws-5.19-headers-5.19.0-1022 all 5.19.0-1022.23~22.04.1 [12.7 MB]
Get:9 http://us-east-2.ec2.archive.ubuntu.com/ubuntu jammy-updates/main amd64 linux-headers-5.19.0-1022-aws amd64 5.19.0-1022.23~22.04.1 [3408 kB]
Get:10 http://us-east-2.ec2.archive.ubuntu.com/ubuntu jammy-updates/main amd64 linux-headers-aws amd64 5.19.0.1022.23~22.04.6 [2230 B]
Fetched 54.2 MB in 1s (51.7 MB/s)       
(Reading database ... 63657 files and directories currently installed.)
Preparing to unpack .../0-bind9-host_1%3a9.18.12-0ubuntu0.22.04.1_amd64.deb ...
Unpacking bind9-host (1:9.18.12-0ubuntu0.22.04.1) over (1:9.18.1-1ubuntu1.3) ...
Preparing to unpack .../1-bind9-dnsutils_1%3a9.18.12-0ubuntu0.22.04.1_amd64.deb ...
Unpacking bind9-dnsutils (1:9.18.12-0ubuntu0.22.04.1) over (1:9.18.1-1ubuntu1.3) ...
Preparing to unpack .../2-bind9-libs_1%3a9.18.12-0ubuntu0.22.04.1_amd64.deb ...
Unpacking bind9-libs:amd64 (1:9.18.12-0ubuntu0.22.04.1) over (1:9.18.1-1ubuntu1.3) ...
Selecting previously unselected package linux-modules-5.19.0-1022-aws.
Preparing to unpack .../3-linux-modules-5.19.0-1022-aws_5.19.0-1022.23~22.04.1_amd64.deb ...
Unpacking linux-modules-5.19.0-1022-aws (5.19.0-1022.23~22.04.1) ...
Selecting previously unselected package linux-image-5.19.0-1022-aws.
Preparing to unpack .../4-linux-image-5.19.0-1022-aws_5.19.0-1022.23~22.04.1_amd64.deb ...
Unpacking linux-image-5.19.0-1022-aws (5.19.0-1022.23~22.04.1) ...
Preparing to unpack .../5-linux-aws_5.19.0.1022.23~22.04.6_amd64.deb ...
Unpacking linux-aws (5.19.0.1022.23~22.04.6) over (5.15.0.1031.29) ...
Preparing to unpack .../6-linux-image-aws_5.19.0.1022.23~22.04.6_amd64.deb ...
Unpacking linux-image-aws (5.19.0.1022.23~22.04.6) over (5.15.0.1031.29) ...
Selecting previously unselected package linux-aws-5.19-headers-5.19.0-1022.
Preparing to unpack .../7-linux-aws-5.19-headers-5.19.0-1022_5.19.0-1022.23~22.04.1_all.deb ...
Unpacking linux-aws-5.19-headers-5.19.0-1022 (5.19.0-1022.23~22.04.1) ...
Selecting previously unselected package linux-headers-5.19.0-1022-aws.
Preparing to unpack .../8-linux-headers-5.19.0-1022-aws_5.19.0-1022.23~22.04.1_amd64.deb ...
Unpacking linux-headers-5.19.0-1022-aws (5.19.0-1022.23~22.04.1) ...
Preparing to unpack .../9-linux-headers-aws_5.19.0.1022.23~22.04.6_amd64.deb ...
Unpacking linux-headers-aws (5.19.0.1022.23~22.04.6) over (5.15.0.1031.29) ...
Setting up bind9-libs:amd64 (1:9.18.12-0ubuntu0.22.04.1) ...
Setting up linux-aws-5.19-headers-5.19.0-1022 (5.19.0-1022.23~22.04.1) ...
Setting up bind9-host (1:9.18.12-0ubuntu0.22.04.1) ...
Setting up linux-headers-5.19.0-1022-aws (5.19.0-1022.23~22.04.1) ...
Setting up linux-headers-aws (5.19.0.1022.23~22.04.6) ...
Setting up bind9-dnsutils (1:9.18.12-0ubuntu0.22.04.1) ...
Setting up linux-image-5.19.0-1022-aws (5.19.0-1022.23~22.04.1) ...
I: /boot/vmlinuz is now a symlink to vmlinuz-5.19.0-1022-aws
I: /boot/initrd.img is now a symlink to initrd.img-5.19.0-1022-aws
Setting up linux-modules-5.19.0-1022-aws (5.19.0-1022.23~22.04.1) ...
Setting up linux-image-aws (5.19.0.1022.23~22.04.6) ...
Setting up linux-aws (5.19.0.1022.23~22.04.6) ...
Processing triggers for man-db (2.10.2-1) ...
Processing triggers for libc-bin (2.35-0ubuntu3.1) ...
Processing triggers for linux-image-5.19.0-1022-aws (5.19.0-1022.23~22.04.1) ...
/etc/kernel/postinst.d/initramfs-tools:
update-initramfs: Generating /boot/initrd.img-5.19.0-1022-aws
/etc/kernel/postinst.d/zz-update-grub:
Sourcing file `/etc/default/grub'
Sourcing file `/etc/default/grub.d/40-force-partuuid.cfg'
Sourcing file `/etc/default/grub.d/50-cloudimg-settings.cfg'
Sourcing file `/etc/default/grub.d/init-select.cfg'
Generating grub configuration file ...
GRUB_FORCE_PARTUUID is set, will attempt initrdless boot
Found linux image: /boot/vmlinuz-5.19.0-1022-aws
Found initrd image: /boot/microcode.cpio /boot/initrd.img-5.19.0-1022-aws
Found linux image: /boot/vmlinuz-5.15.0-1031-aws
Found initrd image: /boot/microcode.cpio /boot/initrd.img-5.15.0-1031-aws
Warning: os-prober will not be executed to detect other bootable partitions.
Systems on them will not be added to the GRUB boot configuration.
Check GRUB_DISABLE_OS_PROBER documentation entry.
done
Scanning processes...                                                                                                                                                                                     
Scanning linux images...                                                                                                                                                                                  

No services need to be restarted.

No containers need to be restarted.

No user sessions are running outdated binaries.

No VM guests are running outdated hypervisor (qemu) binaries on this host.
ubuntu@ip-172-31-8-86:~$ Connection to ec2-3-16-47-6.us-east-2.compute.amazonaws.com closed by remote host.
Connection to ec2-3-16-47-6.us-east-2.compute.amazonaws.com closed.
Anthony@Anthonys-MBP downloads % ssh -i "darey-ec2.pem" ubuntu@ec2-3-16-47-6.us-east-2.compute.amazonaws.com
Welcome to Ubuntu 22.04.2 LTS (GNU/Linux 5.19.0-1022-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

  System information as of Sat Apr  1 17:14:06 UTC 2023

  System load:  0.46923828125     Processes:             100
  Usage of /:   27.4% of 7.57GB   Users logged in:       0
  Memory usage: 23%               IPv4 address for eth0: 172.31.8.86
  Swap usage:   0%


Expanded Security Maintenance for Applications is not enabled.

0 updates can be applied immediately.

Enable ESM Apps to receive additional future security updates.
See https://ubuntu.com/esm or run: sudo pro status


Last login: Sat Apr  1 17:07:44 2023 from 2.31.18.143
ubuntu@ip-172-31-8-86:~$ curl -fsSL https://deb.nodesource.com/setup_18.x | sudo -E bash -

## Installing the NodeSource Node.js 18.x repo...


## Populating apt-get cache...

+ apt-get update
Hit:1 http://us-east-2.ec2.archive.ubuntu.com/ubuntu jammy InRelease
Get:2 http://us-east-2.ec2.archive.ubuntu.com/ubuntu jammy-updates InRelease [119 kB]
Get:3 http://us-east-2.ec2.archive.ubuntu.com/ubuntu jammy-backports InRelease [108 kB]
Hit:4 http://security.ubuntu.com/ubuntu jammy-security InRelease
Fetched 226 kB in 1s (361 kB/s)
Reading package lists... Done

## Confirming "jammy" is supported...

+ curl -sLf -o /dev/null 'https://deb.nodesource.com/node_18.x/dists/jammy/Release'

## Adding the NodeSource signing key to your keyring...

+ curl -s https://deb.nodesource.com/gpgkey/nodesource.gpg.key | gpg --dearmor | tee /usr/share/keyrings/nodesource.gpg >/dev/null

## Creating apt sources list file for the NodeSource Node.js 18.x repo...

+ echo 'deb [signed-by=/usr/share/keyrings/nodesource.gpg] https://deb.nodesource.com/node_18.x jammy main' > /etc/apt/sources.list.d/nodesource.list
+ echo 'deb-src [signed-by=/usr/share/keyrings/nodesource.gpg] https://deb.nodesource.com/node_18.x jammy main' >> /etc/apt/sources.list.d/nodesource.list

## Running `apt-get update` for you...

+ apt-get update
Hit:1 http://us-east-2.ec2.archive.ubuntu.com/ubuntu jammy InRelease
Get:2 http://us-east-2.ec2.archive.ubuntu.com/ubuntu jammy-updates InRelease [119 kB]                 
Hit:3 http://us-east-2.ec2.archive.ubuntu.com/ubuntu jammy-backports InRelease                                                         
Hit:4 http://security.ubuntu.com/ubuntu jammy-security InRelease                                                            
Get:5 https://deb.nodesource.com/node_18.x jammy InRelease [4563 B]     
Get:6 https://deb.nodesource.com/node_18.x jammy/main amd64 Packages [776 B]
Fetched 124 kB in 1s (165 kB/s)
Reading package lists... Done

## Run `sudo apt-get install -y nodejs` to install Node.js 18.x and npm
## You may also need development tools to build native addons:
     sudo apt-get install gcc g++ make
## To install the Yarn package manager, run:
     curl -sL https://dl.yarnpkg.com/debian/pubkey.gpg | gpg --dearmor | sudo tee /usr/share/keyrings/yarnkey.gpg >/dev/null
     echo "deb [signed-by=/usr/share/keyrings/yarnkey.gpg] https://dl.yarnpkg.com/debian stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
     sudo apt-get update && sudo apt-get install yarn


ubuntu@ip-172-31-8-86:~$ sudo apt install -y nodejs
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following NEW packages will be installed:
  nodejs
0 upgraded, 1 newly installed, 0 to remove and 0 not upgraded.
Need to get 28.7 MB of archives.
After this operation, 187 MB of additional disk space will be used.
Get:1 https://deb.nodesource.com/node_18.x jammy/main amd64 nodejs amd64 18.15.0-deb-1nodesource1 [28.7 MB]
Fetched 28.7 MB in 1s (36.5 MB/s) 
Selecting previously unselected package nodejs.
(Reading database ... 93040 files and directories currently installed.)
Preparing to unpack .../nodejs_18.15.0-deb-1nodesource1_amd64.deb ...
Unpacking nodejs (18.15.0-deb-1nodesource1) ...
Setting up nodejs (18.15.0-deb-1nodesource1) ...
Processing triggers for man-db (2.10.2-1) ...
Scanning processes...                                                                                                                                                                                     
Scanning linux images...                                                                                                                                                                                  

Running kernel seems to be up-to-date.

No services need to be restarted.

No containers need to be restarted.

No user sessions are running outdated binaries.

No VM guests are running outdated hypervisor (qemu) binaries on this host.
ubuntu@ip-172-31-8-86:~$ node -v
v18.15.0
ubuntu@ip-172-31-8-86:~$ npm -v
9.5.0
ubuntu@ip-172-31-8-86:~$ mkdir Todo
ubuntu@ip-172-31-8-86:~$ ls
Todo
ubuntu@ip-172-31-8-86:~$ cd Todo
ubuntu@ip-172-31-8-86:~/Todo$ npm init
This utility will walk you through creating a package.json file.
It only covers the most common items, and tries to guess sensible defaults.

See `npm help init` for definitive documentation on these fields
and exactly what they do.

Use `npm install <pkg>` afterwards to install a package and
save it as a dependency in the package.json file.

Press ^C at any time to quit.
package name: (todo) 
version: (1.0.0) 
description: 
entry point: (index.js) 
test command: 
git repository: 
keywords: 
author: 
license: (ISC) 
About to write to /home/ubuntu/Todo/package.json:

{
  "name": "todo",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "author": "",
  "license": "ISC"
}


Is this OK? (yes) 
npm notice 
npm notice New minor version of npm available! 9.5.0 -> 9.6.3
npm notice Changelog: https://github.com/npm/cli/releases/tag/v9.6.3
npm notice Run npm install -g npm@9.6.3 to update!
npm notice 
ubuntu@ip-172-31-8-86:~/Todo$ ls
package.json
ubuntu@ip-172-31-8-86:~/Todo$ npm install express

added 57 packages, and audited 58 packages in 2s

7 packages are looking for funding
  run `npm fund` for details

found 0 vulnerabilities
ubuntu@ip-172-31-8-86:~/Todo$ touch index.js
ubuntu@ip-172-31-8-86:~/Todo$ ls
index.js  node_modules  package-lock.json  package.json
ubuntu@ip-172-31-8-86:~/Todo$ npm install dotenv

added 1 package, and audited 59 packages in 535ms

7 packages are looking for funding
  run `npm fund` for details

found 0 vulnerabilities
Anthony@Anthonys-MBP ~ % cd downloads/
Anthony@Anthonys-MBP downloads % ssh -i "darey-ec2.pem" ubuntu@ec2-3-16-47-6.us-east-2.compute.amazonaws.com
Welcome to Ubuntu 22.04.2 LTS (GNU/Linux 5.19.0-1022-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

  System information as of Sat Apr  1 18:03:38 UTC 2023

  System load:  0.0               Processes:             97
  Usage of /:   29.9% of 7.57GB   Users logged in:       0
  Memory usage: 25%               IPv4 address for eth0: 172.31.8.86
  Swap usage:   0%


 * Introducing Expanded Security Maintenance for Applications.
   Receive updates to over 25,000 software packages with your
   Ubuntu Pro subscription. Free for personal use.

     https://ubuntu.com/aws/pro

Expanded Security Maintenance for Applications is not enabled.

0 updates can be applied immediately.

Enable ESM Apps to receive additional future security updates.
See https://ubuntu.com/esm or run: sudo pro status


Last login: Sat Apr  1 17:14:07 2023 from 2.31.18.143
ubuntu@ip-172-31-8-86:~$ cd Todo
ubuntu@ip-172-31-8-86:~/Todo$ vim index.js
ubuntu@ip-172-31-8-86:~/Todo$ node index.js
/home/ubuntu/Todo/index.js:20
});const express = require('express');
         ^

SyntaxError: Identifier 'express' has already been declared
    at internalCompileFunction (node:internal/vm:73:18)
    at wrapSafe (node:internal/modules/cjs/loader:1176:20)
    at Module._compile (node:internal/modules/cjs/loader:1218:27)
    at Module._extensions..js (node:internal/modules/cjs/loader:1308:10)
    at Module.load (node:internal/modules/cjs/loader:1117:32)
    at Module._load (node:internal/modules/cjs/loader:958:12)
    at Function.executeUserEntryPoint [as runMain] (node:internal/modules/run_main:81:12)
    at node:internal/main/run_main_module:23:47

Node.js v18.15.0
ubuntu@ip-172-31-8-86:~/Todo$ mkdir routes
ubuntu@ip-172-31-8-86:~/Todo$ cd routes
ubuntu@ip-172-31-8-86:~/Todo/routes$ touch api.js
ubuntu@ip-172-31-8-86:~/Todo/routes$ vim api.js
ubuntu@ip-172-31-8-86:~/Todo/routes$ 
ubuntu@ip-172-31-8-86:~/Todo/routes$ cd Todo
-bash: cd: Todo: No such file or directory
ubuntu@ip-172-31-8-86:~/Todo/routes$ cd ..
ubuntu@ip-172-31-8-86:~/Todo$ npm install mongoose

added 24 packages, and audited 83 packages in 3s

8 packages are looking for funding
  run `npm fund` for details

found 0 vulnerabilities
ubuntu@ip-172-31-8-86:~/Todo$ mkdir models
ubuntu@ip-172-31-8-86:~/Todo$ cd models
ubuntu@ip-172-31-8-86:~/Todo/models$ touch todo.js
ubuntu@ip-172-31-8-86:~/Todo/models$ vim todo.js
ubuntu@ip-172-31-8-86:~/Todo/models$ cd routes
-bash: cd: routes: No such file or directory
ubuntu@ip-172-31-8-86:~/Todo/models$ cd ..
ubuntu@ip-172-31-8-86:~/Todo$ cd routes
ubuntu@ip-172-31-8-86:~/Todo/routes$ vim api.js
ubuntu@ip-172-31-8-86:~/Todo/routes$ cd ..
ubuntu@ip-172-31-8-86:~/Todo$ touch .env
ubuntu@ip-172-31-8-86:~/Todo$ vi .env
ubuntu@ip-172-31-8-86:~$ cd Todo
ubuntu@ip-172-31-8-86:~/Todo$ touch .env
vi .env
ubuntu@ip-172-31-8-86:~/Todo$ vim index.js
ubuntu@ip-172-31-8-86:~/Todo$ node index.js
Server running on port 5000
Database connected successfully

<img width="795" alt="Screenshot 2023-04-01 at 18 54 23" src="https://user-images.githubusercontent.com/116417007/229679760-b3d4787b-997e-4fd5-b820-f6303c5edbc5.png">
![Screenshot 2023-04-04 at 03 47 30](https://user-images.githubusercontent.com/116417007/229679865-54158fdd-1ec8-427f-97f9-871489770366.png)
![Screenshot 2023-04-04 at 04 01 31](https://user-images.githubusercontent.com/116417007/229679903-462d5ffa-08bb-4fba-9efd-e05d144989ed.png)
![Screenshot 2023-04-04 at 04 24 31](https://user-images.githubusercontent.com/116417007/229679919-5a4fa56e-a13d-4e50-8042-ade8e333927a.png)

^C
ubuntu@ip-172-31-8-86:~/Todo$ npx create-react-app client
Need to install the following packages:
  create-react-app@5.0.1
Ok to proceed? (y) y
npm WARN deprecated tar@2.2.2: This version of tar is no longer supported, and will not receive security updates. Please upgrade asap.

Creating a new React app in /home/ubuntu/Todo/client.

Installing packages. This might take a couple of minutes.
Installing react, react-dom, and react-scripts with cra-template...


added 1423 packages in 59s

233 packages are looking for funding
  run `npm fund` for details

Initialized a git repository.

Installing template dependencies using npm...

added 62 packages, and changed 1 package in 8s

233 packages are looking for funding
  run `npm fund` for details
Removing template package using npm...


removed 1 package, and audited 1485 packages in 5s

233 packages are looking for funding
  run `npm fund` for details

6 high severity vulnerabilities

To address all issues (including breaking changes), run:
  npm audit fix --force

Run `npm audit` for details.

Created git commit.

Success! Created client at /home/ubuntu/Todo/client
Inside that directory, you can run several commands:

  npm start
    Starts the development server.

  npm run build
    Bundles the app into static files for production.

  npm test
    Starts the test runner.

  npm run eject
    Removes this tool and copies build dependencies, configuration files
    and scripts into the app directory. If you do this, you can’t go back!

We suggest that you begin by typing:

  cd client
  npm start

Happy hacking!
ubuntu@ip-172-31-8-86:~/Todo$ cd client
ubuntu@ip-172-31-8-86:~/Todo/client$ npm install concurrently --save-dev

added 15 packages, and audited 1500 packages in 16s

235 packages are looking for funding
  run `npm fund` for details

6 high severity vulnerabilities

To address all issues (including breaking changes), run:
  npm audit fix --force

Run `npm audit` for details.
ubuntu@ip-172-31-8-86:~/Todo/client$ npm install nodemon --save-dev

added 11 packages, and audited 1511 packages in 5s

236 packages are looking for funding
  run `npm fund` for details

6 high severity vulnerabilities

To address all issues (including breaking changes), run:
  npm audit fix --force

Run `npm audit` for details.
ubuntu@ip-172-31-8-86:~/Todo/client$ cd ..
ubuntu@ip-172-31-8-86:~/Todo$ vim package.json
ubuntu@ip-172-31-8-86:~/Todo$ vim package.json
ubuntu@ip-172-31-8-86:~/Todo$ cd client
ubuntu@ip-172-31-8-86:~/Todo/client$ vi package.json
ubuntu@ip-172-31-8-86:~/Todo/client$ cd ..
ubuntu@ip-172-31-8-86:~/Todo$ npm run dev

> todo@1.0.0 dev
> concurrently "npm run start-watch" "cd client && npm start"

sh: 1: concurrently: not found
ubuntu@ip-172-31-8-86:~/Todo$ cd client
ubuntu@ip-172-31-8-86:~/Todo/client$ ls
README.md  node_modules  package-lock.json  package.json  public  src
ubuntu@ip-172-31-8-86:~/Todo/client$ cd ..
ubuntu@ip-172-31-8-86:~/Todo$ npm install concurrently --save-dev

added 28 packages, and audited 111 packages in 12s

15 packages are looking for funding
  run `npm fund` for details

found 0 vulnerabilities
ubuntu@ip-172-31-8-86:~/Todo$ npm install nodemon --save-dev

added 32 packages, and audited 143 packages in 1s

18 packages are looking for funding
  run `npm fund` for details

found 0 vulnerabilities
ubuntu@ip-172-31-8-86:~/Todo$ npm run dev

> todo@1.0.0 dev
> concurrently "npm run start-watch" "cd client && npm start"

[0] 
[0] > todo@1.0.0 start-watch
[0] > nodemon index.js
[0] 
[1] 
[1] > client@0.1.0 start
[1] > react-scripts start
[1] 
[0] [nodemon] 2.0.22
[0] [nodemon] to restart at any time, enter `rs`
[0] [nodemon] watching path(s): *.*
[0] [nodemon] watching extensions: js,mjs,json
[0] [nodemon] starting `node index.js`
[0] Server running on port 5000
[0] Database connected successfully
[1] (node:1478) [DEP_WEBPACK_DEV_SERVER_ON_AFTER_SETUP_MIDDLEWARE] DeprecationWarning: 'onAfterSetupMiddleware' option is deprecated. Please use the 'setupMiddlewares' option.
[1] (Use `node --trace-deprecation ...` to show where the warning was created)
[1] (node:1478) [DEP_WEBPACK_DEV_SERVER_ON_BEFORE_SETUP_MIDDLEWARE] DeprecationWarning: 'onBeforeSetupMiddleware' option is deprecated. Please use the 'setupMiddlewares' option.
[1] Starting the development server...
[1] 
[1] Compiled successfully!
[1] 
[1] You can now view client in the browser.
[1] 
[1]   Local:            http://localhost:3000
[1]   On Your Network:  http://172.31.8.86:3000
[1] 
[1] Note that the development build is not optimized.
[1] To create a production build, use npm run build. 
[1] webpack compiled successfully
^C[0] npm run start-watch exited with code SIGINT
[1] cd client && npm start exited with code SIGINT

ubuntu@ip-172-31-8-86:~/Todo$ cd client
ubuntu@ip-172-31-8-86:~/Todo/client$ cd src
ubuntu@ip-172-31-8-86:~/Todo/client/src$ mkdir components
ubuntu@ip-172-31-8-86:~/Todo/client/src$ cd components
ubuntu@ip-172-31-8-86:~/Todo/client/src/components$ touch Input.js ListTodo.js Todo.js
ubuntu@ip-172-31-8-86:~/Todo/client/src/components$ vi Input.js
ubuntu@ip-172-31-8-86:~/Todo/client/src/components$ cd ..
ubuntu@ip-172-31-8-86:~/Todo/client/src$ cd ..
ubuntu@ip-172-31-8-86:~/Todo/client$ npm install axios

added 3 packages, and audited 1514 packages in 6s

236 packages are looking for funding
  run `npm fund` for details

6 high severity vulnerabilities

To address all issues (including breaking changes), run:
  npm audit fix --force

Run `npm audit` for details.
ubuntu@ip-172-31-8-86:~/Todo/client$ cd src/components
ubuntu@ip-172-31-8-86:~/Todo/client/src/components$ vi ListTodo.js
ubuntu@ip-172-31-8-86:~/Todo/client/src/components$ cd ..
ubuntu@ip-172-31-8-86:~/Todo/client/src$ vi App.js
ubuntu@ip-172-31-8-86:~/Todo/client/src$ vi App.css
ubuntu@ip-172-31-8-86:~/Todo/client/src$ vim index.css
ubuntu@ip-172-31-8-86:~/Todo/client/src$ cd ../ ..
-bash: cd: too many arguments
ubuntu@ip-172-31-8-86:~/Todo/client/src$ cd ../..
ubuntu@ip-172-31-8-86:~/Todo$ npm run dev

> todo@1.0.0 dev
> concurrently "npm run start-watch" "cd client && npm start"

[0] 
[0] > todo@1.0.0 start-watch
[0] > nodemon index.js
[0] 
[1] 
[1] > client@0.1.0 start
[1] > react-scripts start
[1] 
[0] [nodemon] 2.0.22
[0] [nodemon] to restart at any time, enter `rs`
[0] [nodemon] watching path(s): *.*
[0] [nodemon] watching extensions: js,mjs,json
[0] [nodemon] starting `node index.js`
[0] Server running on port 5000
[0] Database connected successfully
[1] (node:1638) [DEP_WEBPACK_DEV_SERVER_ON_AFTER_SETUP_MIDDLEWARE] DeprecationWarning: 'onAfterSetupMiddleware' option is deprecated. Please use the 'setupMiddlewares' option.
[1] (Use `node --trace-deprecation ...` to show where the warning was created)
[1] (node:1638) [DEP_WEBPACK_DEV_SERVER_ON_BEFORE_SETUP_MIDDLEWARE] DeprecationWarning: 'onBeforeSetupMiddleware' option is deprecated. Please use the 'setupMiddlewares' option.
[1] Starting the development server...
[1] 
[1] Compiled successfully!
[1] 
[1] You can now view client in the browser.
[1] 
[1]   Local:            http://localhost:3000
[1]   On Your Network:  http://172.31.8.86:3000
[1] 
[1] Note that the development build is not optimized.
[1] To create a production build, use npm run build.
[1] 
[1] webpack compiled successfully


