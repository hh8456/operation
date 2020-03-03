### msg-server.conf

[program:msg-server]

environment=IMLOGPATH="/home/huanghai/im-server/log", IMCONFIGPATH="/home/huanghai/im-server/config"
command = /home/huanghai/im-server/bin/msg-server
directory=/home/huanghai/im-server/bin
user=huanghai
startsecs=1
stdout_logfile=/home/huanghai/im-server/log/supervisor.log
autostart=false
autorestart=false

在 ubuntu 18 上, msg-server.conf 放在 /etc/supervisor/conf.d 目录下
在 centos 上 , msg-server.conf 需要改名为 msg-server.ini 放在 /etc/supervisord.d/ 目录下

### 用法

supervisorctl start/stop/restart msg-server
supervisorctl reload

### unix:///var/run/supervisor.sock no such file 解决方法

sudo touch /var/run/supervisor.sock
sudo chmod 777 /var/run/supervisor.sock
sudo service supervisor restart

supervisord 进程必须启动
sudo supervisord -c /etc/supervisor/supervisor.conf