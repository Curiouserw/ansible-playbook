# A Series Of Ansible Fuction  Playbooks
# 一系列Ansible功能playbook

# Playbook说明：
## 1.playbook/sethostname.yml
<pre>
功能：设置主机清单中主机的主机名，并修改/etc/hosts文件中IP与域名的映射关系
条件：主机清单中主机要提前设置主机名
涉及到的文件：playbook/templates/hosts.j2为/etc/hosts的模板文件
</pre>

# Playbook执行说明
    
    ansible-playbook -i inventory playbook/sethostname.yml
