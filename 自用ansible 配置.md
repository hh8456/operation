假设 ucloud 云主机外网 ip 127.0.0.1, 用户名是 ubuntu, 密码 123

/etc/ansible/hosts 中加入配置

[ucloud]

127.0.0.1 ansible_ssh_user='ubuntu' ansible_become=true ansible_become_user=root ansible_become_pass='123'

终端中输入

// 拷贝文件

ansible ucloud -m copy -a "src=/home/username/im/bin/server dest=/root/ubuntu/im/bin/server mode=0777"

// 拷贝文件夹

ansible ucloud -m copy -a "src=/home/username/im/bin/ dest=/root/ubuntu/im/bin/ mode=0777"

// 把 "supervisorctl restart xxx" 传入远程终端并执行

ansible ucloud -a "supervisorctl restart xxx"