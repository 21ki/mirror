# 使用vault
```shell
yum clean all
yum makecache
rpm -e --nodeps centos-release
yum -y install http://mirrors.cloud.tencent.com/centos/7/os/x86_64/Packages/centos-release-7-9.2009.0.el7.centos.x86_64.rpm
yum clean all
yum makecache
rpm -e --nodeps epel-release
yum -y install https://archives.fedoraproject.org/pub/archive/epel/7/x86_64/Packages/e/epel-release-7-14.noarch.rpm
yum clean all
yum makecache
sed -i -e '/^mirrorlist/d;/^#baseurl=/{s,^#,,;s,/mirror,/vault,;}' /etc/yum.repos.d/CentOS*.repo
```