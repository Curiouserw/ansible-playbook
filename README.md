# Ansible Playbooks

# Playbook说明：
## 1.playbook/sethostname.yml
**`功能`** ：批量设置主机清单中主机的主机名，并修改/etc/hosts文件中IP与域名的映射关系</br>
**`条件`** ：主机清单中主机要提前设置主机名</br>
**`涉及到的文件`** ：playbook/templates/hosts.j2为/etc/hosts的模板文件</br>
**`执行命令`
    ansible-playbook -i inventory playbook/sethostname.yml -k --ask-vault-pass
        参数解释：
               -k：输入root用户SSH连接密码
               --ask-vault-pass：输入inventory主机清单文件加密后的密码

