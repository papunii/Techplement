## Step-1 : Setup Linux VM (UBUNTU)

1) Login into AWS Cloud account
2) Launch Linux VM using EC2 service   
     - AMI :  ubuntu
     - Instance Type :  t2-micro 
4) Connect to VM using MobaXterm

## Step-2 : Update Linux VM

```
sudo apt update

```
## Step-3 : Install apache
```
sudo apt install apache2
```
## Step-4 :  Install PHP
```
sudo apt install php libapache2-mod-php php-mysql
```
## Step-5 : Install MySql
```
sudo apt install mysql-server
```

## Step-6: Login to MySql
```
 sudo mysql -u root
```
1-Change authentication plugin to mysql_native_password (change the password to something strong)
```
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password by 'Satya@123';
```

2-Create a new database user for wordpress (change the password to something strong)
```
CREATE USER 'satya_user'@localhost IDENTIFIED BY 'Satya@123';
```

3-Create a database for Wordpress
```
CREATE DATABASE wp;
```

4-Grant all privilges on the database 'wp' to the newly created user
```
GRANT ALL PRIVILEGES ON wp.* TO 'satya_user'@localhost;
```

## Step-7: Change directory to tmp
```
 cd /tmp
```
## Step-8: Download Wordpress
```
wget https://wordpress.org/wordpress-6.7.2.tar.gz
```
## Step-9: Extract tar file
```
 tar -xvf wordpress-6.7.2.tar.gz
```
## Step-10: Move wordpress to html directory
```
 sudo mv wordpress/ /var/www/html
```
## Step-11: Change directory to wordpress
```
cd /var/www/html/wordpress
```

Now login to using https//publicip/wordpress
Your wordpress is now ready up and running

