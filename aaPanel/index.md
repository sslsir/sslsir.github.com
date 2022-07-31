宝塔面板国际版安装

## aaPanel 安装脚本

```markdown
Centos：yum install -y wget && wget -O install.sh http://www.aapanel.com/script/install_6.0_en.sh && bash install.sh aapanel
Ubuntu/Deepin：wget -O install.sh http://www.aapanel.com/script/install-ubuntu_6.0_en.sh && sudo bash install.sh aapanel
Debian：wget -O install.sh http://www.aapanel.com/script/install-ubuntu_6.0_en.sh && bash install.sh aapanel
```
`注意：确保是干净的操作系统，没有安装Apache/Nginx/php/MySQL的其他环境（现有环境不能安装）
建议使用Chrome、Firefox、edge浏览器访问面板登录地址`

## aaPanel 管理脚本

**面板管理**

```markdown
Stop：   service bt stop
Start：  service bt start
Restart：service bt restart
```

[Install aaPanel for free](https://sslsir.github.io/aaPanel/install.mhtml)