# Configuring oracle linux 6.5 virtualbox

Installing (virtualbox guest additions)

`````
yum remove kernel-headers

cd /etc/yum.repos.d
wget http://public-yum.oracle.com/public-yum-ol6.repo
uname -a
vi public-yum-ol6.repo

[public_ol6_UEKR3_latest]
name=Latest Unbreakable Enterprise Kernel for Oracle Linux $releasever ($basearch)
baseurl=http://yum.oracle.com/repo/OracleLinux/OL6/UEKR3/latest/$basearch/
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-oracle
gpgcheck=1
enabled=0 #change to 1

kill -9 $(ps aux |grep -i yum |awk {'print $2'}) && yum -y install kernel-uek-devel-$(uname -r)
`````


optional
`````
kill -9 $(ps aux |grep -i yum |awk {'print $2'}) && yum update -y
yum install gcc
yum install kernel-uek-devel -y
`````
