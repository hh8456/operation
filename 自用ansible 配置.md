���� ucloud ���������� ip 127.0.0.1, �û����� ubuntu, ���� 123

/etc/ansible/hosts �м�������

[ucloud]

127.0.0.1 ansible_ssh_user='ubuntu' ansible_become=true ansible_become_user=root ansible_become_pass='123'

�ն�������

// �����ļ�

ansible ucloud -m copy -a "src=/home/username/im/bin/server dest=/root/ubuntu/im/bin/server mode=0777"

// �����ļ���

ansible ucloud -m copy -a "src=/home/username/im/bin/ dest=/root/ubuntu/im/bin/ mode=0777"

// �� "supervisorctl restart xxx" ����Զ���ն˲�ִ��

ansible ucloud -a "supervisorctl restart xxx"