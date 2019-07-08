---
published: true
---
## Install Mysql server on ubuntu

First we need to install some ubuntu packages:

1. sudo apt-get install mysql-server mysql-client phpmyadmin
2. If the setup does not run automatically, run: sudo mysql_secure_installation
3. Mysql code:

If phpmyadmin dont work, try:
sudo ln -s /etc/phpmyadmin/apache.conf /etc/apache2/conf-available/phpmyadmin.conf
sudo ln -s /usr/share/phpmyadmin /var/www/html/phpmyadmin
sudo service apache2 restart

now type  localhost/phpmyadmin in web browser address bar

```css 
CREATE DATABASE DB1;

GRANT ALL ON DB1.* TO 'USER'@'%' IDENTIFIED BY 'PASSWORD';

FLUSH PRIVILEGES;
```

4. Edit settings file for remote access. Change bind adress = 127.0.0.0 to 0.0.0.0
The file can be found in either:
sudo nano /etc/mysql/mysql.conf.d/mysql.cnf
sudo nano /etc/mysql/mariadb.conf.d/50-server.cnf

Sudo mysql -u root

5. Enable port forwarding on router.

Try connection in python:
conn = pymysql.connect("192.168.1.95, user="ludvig", passwd="danderydd", db="DB1, connect_timeout=5)
