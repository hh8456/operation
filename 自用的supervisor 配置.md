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

�� ubuntu 18 ��, msg-server.conf ���� /etc/supervisor/conf.d Ŀ¼��
�� centos �� , msg-server.conf ��Ҫ����Ϊ msg-server.ini ���� /etc/supervisord.d/ Ŀ¼��

### �÷�

supervisorctl start/stop/restart msg-server
supervisorctl reload

### unix:///var/run/supervisor.sock no such file �������

sudo touch /var/run/supervisor.sock
sudo chmod 777 /var/run/supervisor.sock
sudo service supervisor restart

supervisord ���̱�������
sudo supervisord -c /etc/supervisor/supervisor.conf