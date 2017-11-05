---
layout: post
title: Ansible, Docker & Octopussy
---

For my [first participation to Hacktoberfest](https://sebthebert.github.io/Hacktoberfest-2017/), 
I decided to work on an [Ansible Role][octopussy_role] for my [Octopussy][octopussy] Project.

My motivations:
  * improve/update my [Installation Documentation][octopussy_doc_install]
  * provide a better/easy way to install [Octopussy][octopussy]
  * improve my knowledge about Ansible

I thought it would be easy because: 
  * my [existing documentation][octopussy_doc_install] already contains almost everything to know (enven if outdated) for major Linux Distributions
  * [Ansible][ansible] is easy (at least for simple things)
  * Docker ...

It was really really more complicated than I thought first...

I chose 2 versions for 4 distributions:
  * CentOS 6 & 7
  * Debian 8 & 9
  * Fedora 25 & 26
  * Ubuntu 14.04 & 16.05
  
## Docker

Some images don't have python
 
## Ansible & Python versions

## Systemd

Remove majority of systemd
```
RUN (cd /lib/systemd/system/sysinit.target.wants/; for i in *; do [ $i == systemd-tmpfiles-setup.service ] || rm -f $i; done); 
    rm -f /lib/systemd/system/multi-user.target.wants/*;
    rm -f /etc/systemd/system/*.wants/*;
    rm -f /lib/systemd/system/local-fs.target.wants/*; 
    rm -f /lib/systemd/system/sockets.target.wants/*udev*; 
    rm -f /lib/systemd/system/sockets.target.wants/*initctl*; 
    rm -f /lib/systemd/system/basic.target.wants/*;
    rm -f /lib/systemd/system/anaconda.target.wants/*;
```

Run container with `
```
–privileged -ti -v /sys/fs/cgroup:/sys/fs/cgroup:ro
```

## Apache 2.2 & 2.4
httpd vs apache2
 
## MySQL 5.6 & 5.7 & MariaDB

systemd on centos:
    https://hub.docker.com/_/centos/

python on ubuntu

systemd on ubuntu

on centos7
MySQL 5.7 => 
password -> authentication_string
https://stackoverflow.com/questions/30692812/mysql-user-db-does-not-have-password-columns-installing-mysql-on-osx 
==> TO FIX in ansible-role !!!

docker container
tmpfs => ansible 2.4
https://linuxconfig.org/ansible-installation-on-centos-7-linux




[ansible]: https://www.ansible.com
[octopussy]: https://github.com/Octopussy-Project/Octopussy
[octopussy_doc_install]: https://github.com/Octopussy-Project/Octopussy_Documentation/blob/master/01_Installation.md
[octopussy_role]: https://github.com/Octopussy-Project/ansible-role-octopussy
