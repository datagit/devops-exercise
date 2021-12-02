#### How to Install Laravel 5.x with Nginx and PHP-FPM 7.1 on CentOS 7
https://www.howtoforge.com/tutorial/how-to-install-laravel-5x-with-nginx-and-php-fpm-7-on-centos-7/#step-install-and-configure-phpfpm-
```java
// EC2 instance centos on AWS
ssh -i mykeypaire/my_ec2_2.cer ec2-user@54.251.132.38

sudo amazon-linux-extras install epel

yum -y install nginx
systemctl start nginx
systemctl enable nginx

yum -y install net-tools

// php 7.1
rpm -Uvh https://mirror.webtatic.com/yum/el7/webtatic-release.rpm
yum install -y php71w php71w-curl php71w-common php71w-cli php71w-mysql php71w-mbstring php71w-fpm php71w-xml php71w-pdo php71w-zip

// php 7.3
yum install -y https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm
yum install -y http://rpms.remirepo.net/enterprise/remi-release-7.rpm
sudo amazon-linux-extras install php7.3
php -v


```
#### Config Github on EC2 for clone and pull for deploy code automation
```java
// user [ec2-user] includes group [ec2-user]
ssh -i mykeypaire/my_ec2_2.cer ec2-user@54.255.118.184

// on PC client begin
// check exists ssh key
ls -la ~/.ssh/
// generate new a ssh key
ssh-keygen -t rsa -b 4096 -C "datagit@yahoo.com"

// copy content file public key so that put it on server
cat ~/.ssh/id_rsa.pub
ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAACAQCoHW4h3l9ZhS5zN73gIM0ej5d5K6HgC6pGoOB0FH1AHhJTsIckFZLP2CZEPsMslc3W5EgF1++CFb4yTNOPg02R8wCVpFPydbfF2vOSEY9jShGougPWpuG1gt6Y/lUtprkELdaJ6MZJh3q9P/VBFLetOn5DZIpQnigwpM0WRKsX/GDUcIMxXeut9amcTOnKqfnsXpS2gvCIk1rUmhvDytVXrzJq2ut1UXJNt9EJo1mXWtMaF3Nrh6lTO6EI3ZBR9/YJlobnECHQTTgCiMk6yd4KYS+q65whbS+sEaKXaam4u5wwt27S6xf+etSsSuu44dIfpS31wDVHAMO5+J5I84/JsWLF85EKoVWYwT3eWjQzABMLliGrf4OhIr7YQegjGnIj5X8pnUrF+d1gCtVVGU8EbNl/WhtoPQX3LivFquDCLOjIq+jR7otkzY47CVBWoxVPFVDfxLUwSy68Vu2i7bbL1gXjsRrSc+8/16U35A1vr1gGDg8/KzY6SGF4yKepzmzHlPJGVeo6ppvTqBVV3aYtBbNl7NLPVEzF1OxyrmmG9UEak9o5c3dfcTWe+IvWyEOJ+GfdUH/md40LMSMS+jYbiq+WdxnBimfBmO66gEe5O4NGQo8kSMzZASUHH6rgSdafNMxCMkZuEvD3gCVste8r3f4sxMfmIUiv04jjAPMZeQ== datagit@yahoo.com

// check authentication from client to server github.com
ssh -T git@github.com
Hi datagit! You have successfully authenticated, but GitHub does not provide shell access.

// on PC client end

cd /var/www/laravel
// set git remote url by ssh
git remote set-url origin git@github.com:datagit/citicar_web.git

git config user.name "dat dao"
git config user.email "datagit@yahoo.com"

// To view the numerical IDs associated with each group, run the id  command instead:
id
	uid=1000(ec2-user) gid=1000(ec2-user) groups=1000(ec2-user),4(adm),10(wheel),190(systemd-journal)

// to view the user info
id nginx
uid=995(nginx) gid=993(nginx) groups=993(nginx)

cd /var/www/laravel
ls -la app
	total 4
	drwxr-xr-x  8 nginx ec2-user   95 Nov 24 02:46 .
	drwxr-xr-x 15 nginx ec2-user 4096 Dec  2 04:38 ..
	drwxr-xr-x  2 nginx ec2-user   24 Nov 24 02:46 Console
	drwxr-xr-x  2 nginx ec2-user  203 Nov 24 02:46 Enums
	drwxr-xr-x  2 nginx ec2-user   25 Nov 24 02:46 Exceptions
	drwxr-xr-x  5 nginx ec2-user   77 Nov 24 02:46 Http
	drwxr-xr-x  2 nginx ec2-user   98 Nov 24 02:46 Models
	drwxr-xr-x  2 nginx ec2-user  167 Nov 24 02:51 Providers
// owner user is user [nginx]
// owner group is group [ec2-user]

// user login ssh -> owner on folder code /var/www/laravel
// change group owner for resource
// cmd: chown [OPTIONS] USER[:GROUP] FILE(s)
sudo chown :ec2-user -R /var/www/laravel

// // new a group
// sudo groupadd mynewgroup

// // Add an Existing User Account to a Group
// usermod -a -G examplegroup exampleusername

// // For example, to add the user geek to the group sudo , use the following command:
// usermod -a -G sudo geek

git pull

// install with exists a file composer.lock and not check php extension
composer update --lock --ignore-platform-reqs
``
