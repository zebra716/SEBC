1.Check vm.swappiness on all your nodes
  Set the value to 1 if necessary

  > sysctl vm.swappiness
    vm.swappiness = 60
  > vi /etc/sysctl.conf
    1. add vm.swappiness = 1 at the end of file.
    2. write & save
    3. reboot
  > sysctl vm.swappiness
    vm.swappiness = 1

2.Show the mount attributes of your volume(s)
  > mount -v
    /dev/xvde on / type ext4 (rw)
    proc on /proc type proc (rw)
    sysfs on /sys type sysfs (rw)
    devpts on /dev/pts type devpts (rw,gid=5,mode=620)
    tmpfs on /dev/shm type tmpfs (rw,rootcontext="system_u:object_r:tmpfs_t:s0")
    none on /proc/sys/fs/binfmt_misc type binfmt_misc (rw)
  
3.If you have ext-based volumes, list the reserve space setting
  XFS volumes do not support reserve space
  
  > df -h
    Filesystem      Size  Used Avail Use% Mounted on
    /dev/xvde       7.9G  774M  6.8G  11% /
    tmpfs           7.4G     0  7.4G   0% /dev/shm
      
  > lsblk
    NAME MAJ:MIN RM SIZE RO TYPE MOUNTPOINT
    xvde 202:64   0  30G  0 disk /

  > resize2fs /dev/xvde
    resize2fs 1.41.12 (17-May-2010)
    Filesystem at /dev/xvde is mounted on /; on-line resizing required
    old desc_blocks = 1, new_desc_blocks = 2
    Performing an on-line resize of /dev/xvde to 7864320 (4k) blocks.
    The filesystem on /dev/xvde is now 7864320 blocks long.
    
   > df -h
    Filesystem      Size  Used Avail Use% Mounted on
    /dev/xvde        30G  778M   28G   3% /
    tmpfs           7.4G     0  7.4G   0% /dev/shm

4.Disable transparent hugepage support
  Add transparent_hugepage=never at the end of kernel line in /etc/grub.conf file.

  > vi /etc/grub.conf
    default=0
    timeout=1

    title CentOS-6.5-x86_64-GA-03 2.6.32-431.el6.x86_64
        root (hd0)
        kernel /boot/vmlinuz-2.6.32-431.el6.x86_64 root=LABEL=centos_root ro transparent_hugepage=never
        initrd /boot/initramfs-2.6.32-431.el6.x86_64.img

5.List your network interface configuration
  > ifconfig
    eth0      Link encap:Ethernet  HWaddr 06:0F:B4:8C:05:9E
              inet addr:172.31.42.35  Bcast:172.31.47.255  Mask:255.255.240.0
              inet6 addr: fe80::40f:b4ff:fe8c:59e/64 Scope:Link
              UP BROADCAST RUNNING MULTICAST  MTU:9001  Metric:1
              RX packets:19042 errors:0 dropped:0 overruns:0 frame:0
              TX packets:3696 errors:0 dropped:0 overruns:0 carrier:0
              collisions:0 txqueuelen:1000
              RX bytes:27158632 (25.9 MiB)  TX bytes:311399 (304.1 KiB)
              Interrupt:24
    
    lo        Link encap:Local Loopback
              inet addr:127.0.0.1  Mask:255.0.0.0
              inet6 addr: ::1/128 Scope:Host
              UP LOOPBACK RUNNING  MTU:16436  Metric:1
              RX packets:0 errors:0 dropped:0 overruns:0 frame:0
              TX packets:0 errors:0 dropped:0 overruns:0 carrier:0
              collisions:0 txqueuelen:0
              RX bytes:0 (0.0 b)  TX bytes:0 (0.0 b)

6.Show that forward and reverse host lookups are correctly resolved
  For /etc/hosts, use getent
  > getent hosts
    127.0.0.1       localhost.localdomain localhost
    127.0.0.1       localhost6.localdomain6 localhost6

  For DNS, use nslookup
  > yum install bind-utils
  > nslookup localhost
    Server:         172.31.0.2
    Address:        172.31.0.2#53
    
    Name:   localhost
    Address: 127.0.0.1

6.Show the nscd service is running
  > service nscd status
    nscd: unrecognized service
  > yum install nscd
  > service nscd start
    Starting nscd:                                             [  OK  ]
  > service nscd status
    nscd (pid  1195) is running...

7.Show the ntpd service is running
  > service ntpd status
    ntpd: unrecognized service
  > yum install ntp
  > service ntpd start
    Starting ntpd:                                             [  OK  ]
  > service ntpd status
    ntpd (pid  1171) is running...

8.Other steps
8.1.Disable SELinux
  > vi /etc/selinux/config
    SELINUX=disabled 

8.2.Disable and stop IPTables
  > chkconfig --level 35 iptables off
  > /etc/init.d/iptables stop

----------------------------------------------------------

cd /etc/yum.repos.d
yum install wget
wget https://archive.cloudera.com/cm5/redhat/6/x86_64/cm/cloudera-manager.repo
yum install oracle-j2sdk1.7

mkdir /usr/share/java
cd /usr/share/java
wget https://cdn.mysql.com//Downloads/Connector-J/mysql-connector-java-5.1.42.tar.gz

tar zxvf mysql-connector-java-5.1.42.tar.gz
cp ./mysql-connector-java-5.1.42/mysql-connector-java-5.1.42-bin.jar /usr/share/java/oracle-connector-java.jar
cp ./mysql-connector-java-5.1.42/mysql-connector-java-5.1.42-bin.jar /usr/share/java/mysql-connector-java.jar

yum install mysql
yum install mysql-server

/etc/init.d/mysql stop
mysqld_safe --user=mysql --skip-grant-tables --skip-networking &

# mysql -u root mysql
mysql> UPDATE user SET Password=PASSWORD('123456') where USER='root';
mysql> FLUSH PRIVILEGES;
mysql> quit;

# /etc/init.d/mysql restart
# mysql -uroot -p123456

grant all privileges on *.* to root@'%';



yum install cloudera-manager-daemons cloudera-manager-server
yum install cloudera-manager-agent cloudera-manager-daemons

/usr/share/cmf/schema/scm_prepare_database.sh database-type [options] database-name username password
/usr/share/cmf/schema/scm_prepare_database.sh mysql cm root 123456

service cloudera-scm-agent start
service cloudera-scm-server start

tail -f /var/log/cloudera-scm-server/cloudera-scm-server.log

http://Server host:7180
admin/admin

