# 使用vault
```shell
yum clean all
yum makecache
rpm -e --nodeps centos-release
yum -y install http://mirrors.cloud.tencent.com/centos/7/os/x86_64/Packages/centos-release-7-9.2009.0.el7.centos.x86_64.rpm
yum clean all
yum makecache
rpm -e --nodeps epel-release
yum -y install https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm
yum clean all
yum makecache
sed -i -e '/^mirrorlist/d;/^#baseurl=/{s,^#,,;s,/epel,/archive/epel,;}' /etc/yum.repos.d/epel*.repo


sed -i -e '/^mirrorlist/d;/^#baseurl=/{s,^#,,;s,/mirror,/vault,;}' /etc/yum.repos.d/CentOS*.repo
```