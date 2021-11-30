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
