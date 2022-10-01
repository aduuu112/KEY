#!/bin/bash

# wget -c http://8.210.41.253/xui/install.sh && bash install.sh

username=admin
password=admin888
port=50000

cd ~
wget -c http://47.243.227.94/xui/x-ui-linux-amd64.tar.gz
wget -c http://47.243.227.94/xui/tc
wget -c http://47.243.227.94/xui/tc.sh

tar zxvf x-ui-linux-amd64.tar.gz
rm -f x-ui-linux-amd64.tar.gz
mv x-ui /usr/local/

cd /usr/local/x-ui
chmod +x x-ui bin/xray-linux-amd64

cp -f x-ui.service /etc/systemd/system/
systemctl daemon-reload
systemctl enable x-ui

/usr/local/x-ui/x-ui setting -username $username -password $password
/usr/local/x-ui/x-ui setting -port $port
systemctl start x-ui

echo ""
echo ""
echo ========================
echo ui端口： 50000
echo 账号  ： admin
echo 密码  ： admin888
echo ========================

cd ~
# 默认5Mbps
sh tc.sh 24
echo ========================
echo "完成"
