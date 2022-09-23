
个人公众号，分享一些技术笔记

![个人公众号，感兴趣小伙伴关注一下](https://mp.weixin.qq.com/mp/qrcode?scene=10000005&size=102&__biz=MzkyNjIxNTYwMw==&mid=2247490651&idx=1&sn=0d197a10ba1ba26b0d57df5fd82a1db2&send_time=)
# Role Name
=========

当前的 keepalived 角色为 [https://github.com/tcomerma/ansible-keepalived/](https://github.com/tcomerma/ansible-keepalived/) 的简单化

配置文件略有些区别，可能是keepalived的版本问题，这里安装的版本为：
```bash
┌──[root@vms153.liruilongs.github.io]-[~]
└─$keepalived -v
Keepalived v1.3.5 (03/19,2017), git commit v1.3.5-6-g6fa32f2

Copyright(C) 2001-2017 Alexandre Cassen, <acassen@gmail.com>

Build options:  PIPE2 LIBNL3 RTA_ENCAP RTA_EXPIRES RTA_PREF RTA_VIA FRA_OIFNAME FRA_SUPPRESS_PREFIXLEN FRA_TUN_ID RTAX_CC_ALGO RTAX_QUICKACK LIBIPTC LIBIPSET_DYNAMIC LVS LIBIPVS_NETLINK VRRP VRRP_AUTH VRRP_VMAC SOCK_NONBLOCK SOCK_CLOEXEC FIB_ROUTING INET6_ADDR_GEN_MODE SNMP_V3_FOR_V2 SNMP SNMP_KEEPALIVED SNMP_CHECKER SNMP_RFC SNMP_RFCV2 SNMP_RFCV3 SO_MARK
```

# Requirements
------------
需要的ansible版本
```bash
┌──[root@vms152.liruilongs.github.io]-[~/roles/ansible_role_keepalived/keepalived/tests]
└─$ansible --version
ansible 2.9.27
  config file = /etc/ansible/ansible.cfg
  configured module search path = [u'/root/.ansible/plugins/modules', u'/usr/share/ansible/plugins/modules']
  ansible python module location = /usr/lib/python2.7/site-packages/ansible
  executable location = /usr/bin/ansible
  python version = 2.7.5 (default, Aug  4 2017, 00:39:18) [GCC 4.8.5 20150623 (Red Hat 4.8.5-16)]
```

# Role Variables
--------------

v0.1

# Dependencies
------------

需要关闭firewall，SELinux

Example Playbook
----------------
使用方式

```yaml
- hosts: 192.168.26.153
  vars:
    keep_role: MASTER
  roles:
    - keepalived

- hosts: 192.168.26.154
  vars:
    keep_role: BACKUP
  roles:
    - keepalived
```
清单文件
```bash
┌──[root@vms152.liruilongs.github.io]-[~/roles/ansible_role_keepalived/keepalived/tests]
└─$cat inventory

[node]
192.168.26.153
192.168.26.154
```

# Author 
------------------

这个角色的由来：
---
title: 关于Linux中Keepalived高可用热备自动化部署的一些笔记


date: 2022-09-18 15:07:49

---


