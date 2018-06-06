# Ansible Playbooks

# Playbook说明：
## 1.playbook/sethostname.yml
**`功能`** ：批量设置主机清单中主机的主机名，并修改/etc/hosts文件中IP与域名的映射关系</br>
**`条件`** ：主机清单中主机要提前设置主机名</br>
**`涉及到的文件`** ：playbook/templates/hosts.j2为/etc/hosts的模板文件</br>
**`执行命令`**:

    ansible-playbook -i inventory playbook/sethostname.yml -k --ask-vault-pass
    参数解释：
        -k：输入root用户SSH连接密码
        --ask-vault-pass：输入inventory主机清单文件加密后的密码
## 2.playbook/dockerlvmstorage.yml
**`功能`** ： 安装docker，设置docker storage为某个LVM类型的磁盘
**`条件`** ： 受托管主机提供一个未格式化、没有文件系统的磁盘或磁盘分区，例如:/dev/vdc，/dev/vdc1
**`涉及到的文件`**： playbook/templates/docker-storage-setup.j2为docker的/etc/sysconfig/docker-storage-setup模板文件
**`执行命令`**:

    ansible-playbook -i inventory playbook/dockerlvmstorage.yml -k --ask-vault-pass
    #命令说明：会要求输入root用户SSH连接密码、inventory主机清单文件加密后的密码和一个未格式化、没有文件系统磁盘设备名
