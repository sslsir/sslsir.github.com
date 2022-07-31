aaPanel 宝塔面板国际版

![宝塔面板国际版](https://sslsir.github.io/assets/images/aapanel.png)

## aaPanel 安装脚本

Centos：
```markdown
yum install -y wget && wget -O install.sh http://www.aapanel.com/script/install_6.0_en.sh && bash install.sh aapanel
```

Ubuntu/Deepin：
```markdown
wget -O install.sh http://www.aapanel.com/script/install-ubuntu_6.0_en.sh && sudo bash install.sh aapanel
```

Debian：
```markdown
wget -O install.sh http://www.aapanel.com/script/install-ubuntu_6.0_en.sh && bash install.sh aapanel
```

注意：确保是干净的操作系统，没有安装Apache/Nginx/php/MySQL的其他环境（现有环境不能安装）
建议使用Chrome、Firefox、edge浏览器访问面板登录地址

## aaPanel 管理脚本

###面板管理###

Stop：
```markdown
service bt stop
```

Start：
```markdown
service bt start
```

Restart：
```markdown
service bt restart
```

Uninstall
```markdown
service bt stop && chkconfig --del bt && rm -f /etc/init.d/bt && rm -rf /www/server/panel
```

View current port of control panel
```markdown
cat /www/server/panel/data/port.pl
```

Change port of control panel，e.g. 8881（centos 6 Operation System）
```markdown
echo '8881' > /www/server/panel/data/port.pl && service bt restart iptables -I INPUT -p tcp -m state --state NEW -m tcp --dport 8881 -j ACCEPT service iptables save service iptables restart
```

Change port of control panel，e.g. 8881（centos 7 Operation System）
```markdown
echo '8881' > /www/server/panel/data/port.pl && service bt restart firewall-cmd --permanent --zone=public --add-port=8881/tcp firewall-cmd --reload
```

Force to change MySQL manager (root) Password，e.g. 123456
```markdown
cd /www/server/panel && python tools.py root 123456
```

Change control Panel login password，e.g. 123456
```markdown
cd /www/server/panel && python tools.py panel 123456
```

Site Configuration location
```markdown
/www/server/panel/vhost
```
Delete banding domain of control panel
```markdown
rm -f /www/server/panel/data/domain.conf
```
Clean login restriction
```markdown
rm -f /www/server/panel/data/*.login
```
View control panel authorization IP
```markdown
cat /www/server/panel/data/limitip.conf
```
Stop access restriction
```markdown
rm -f /www/server/panel/data/limitip.conf
```
View permission domain
```markdown
cat /www/server/panel/data/domain.conf
```
Turn off control panel SSL
```markdown
rm -f /www/server/panel/data/ssl.pl && /etc/init.d/bt restart
```
View control panel error logs
```markdown
cat /tmp/panelBoot
```
View database error log
```markdown
cat /www/server/data/*.err
```
Site Configuration directory(nginx)
```markdown
/www/server/panel/vhost/nginx
```
Site Configuration directory(apache)
```markdown
/www/server/panel/vhost/apache
```
Site default directory
```markdown
/www/wwwroot
```
Database backup directory
```markdown
/www/backup/database
```
Site backup directory
```markdown
/www/backup/site
```
Site logs
```markdown
/www/wwwlogs
```


###Nginx###

nginx installation directory
```markdown
/www/server/nginx
```
Start
```markdown
service nginx start
```
Stop
```markdown
service nginx stop
```
Restart
```markdown
service nginx restart
```
Reload
```markdown
service nginx reload
```
nginx Configuration
```markdown
/www/server/nginx/conf/nginx.conf
```


###Apache###

apache installation directory
```markdown
/www/server/httpd
```
Start
```markdown
service httpd start
```
Stop
```markdown
service httpd stop
```
Restart
```markdown
service httpd restart
```
Reload
```markdown
service httpd reload
```
apache Configuration
```markdown
/www/server/apache/conf/httpd.conf
```


###MySQL###

mysql installation directory
```markdown
/www/server/mysql
```
phpmyadmin installation directory
```markdown
/www/server/phpmyadmin
```
Data storage directory
```markdown
/www/server/data mysql
```
Start
```markdown
service mysqld start
```
Stop
```markdown
service mysqld stop
```
Restart
```markdown
service mysqld restart
```
Reload
```markdown
service mysqld reload
```
mysql Configuration
```markdown
/etc/my.cnf
```


###FTP###

ftp installation directory
```markdown
/www/server/pure-ftpd
```
Start
```markdown
service pure-ftpd start
```
Stop
```markdown
service pure-ftpd stop
```
Restart
```markdown
service pure-ftpd restart
```
ftp Configuration
```markdown
/www/server/pure-ftpd/etc/pure-ftpd
```


###PHP###

php installation directory
```markdown
/www/server/php
```
Start(Please modify by PHP version, e.g. service php-fpm-54 start)
```markdown
servicephp-fpm-{52|53|54|55|56|70|71|72|73|74|80|81} start
```
Stop(Please modify by PHP version, e.g. service php-fpm-54 stop)
```markdown
service php-fpm-{52|53|54|55|56|70|71|72|73|74|80|81} stop
```
Restart(Please modify by PHP version, e.g. service php-fpm-54 restart)
```markdown
service php-fpm-{52|53|54|55|56|70|71|72|73|74|80|81} restart
```
Reload(Please modify by PHP version, e.g. service php-fpm-54 reload)
```markdown
service php-fpm-{52|53|54|55|56|70|71|72|73|74|80|81} reload
```
Configuration(Please modify by PHP version, e.g. /www/server/php/52/etc/php.ini)
```markdown
/www/server/php/{52|53|54|55|56|70|71|72|73|74|80|81}/etc/php.ini
```


###Redis###

redis installation directory
```markdown
/www/server/redis
```
Start
```markdown
service redis start
```
Stop
```markdown
service redis stop
```
redis Configuration
```markdown
/www/server/redis/redis.conf
```

###Memcached###

memcached installation directory
```markdown
/usr/local/memcached
```
Start
```markdown
service memcached start
```
Stop
```markdown
service memcached stop
```
Restart
```markdown
service memcached restart
```
Reload
```markdown
service memcached reload
```

[Install aaPanel for free](https://sslsir.github.io/aaPanel/install.mhtml)
