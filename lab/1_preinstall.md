  
1. Check vm.swappiness on all your nodes  
Set the value to 1 if necessary  
```

[root@ip-172-31-36-60 ~]# sysctl vm.swappiness
vm.swappiness = 1

[root@ip-172-31-36-60 ~]# vi /etc/sysctl.conf  
  > add vm.swappiness = 1 at the end of file.  
  > write & save & quit  
[root@ip-172-31-36-60 ~]# reboot  
[root@ip-172-31-36-60 ~]# sysctl vm.swappiness  
vm.swappiness = 1  
```

2. Show the mount attributes of your volume(s)  
```
[root@ip-172-31-36-60 ~]# mount -v  
/dev/xvde on / type ext4 (rw)  
proc on /proc type proc (rw)  
sysfs on /sys type sysfs (rw)  
devpts on /dev/pts type devpts (rw,gid=5,mode=620)  
tmpfs on /dev/shm type tmpfs (rw,rootcontext="system_u:object_r:tmpfs_t:s0")  
none on /proc/sys/fs/binfmt_misc type binfmt_misc (rw)  
```

3. If you have ext-based volumes, list the reserve space setting  
XFS volumes do not support reserve space  
```
[root@ip-172-31-36-60 ~]# df -h  
Filesystem      Size  Used Avail Use% Mounted on  
/dev/xvde       7.9G  774M  6.8G  11% /  
tmpfs           7.4G     0  7.4G   0% /dev/shm  
  
[root@ip-172-31-36-60 ~]# lsblk  
NAME MAJ:MIN RM SIZE RO TYPE MOUNTPOINT  
xvde 202:64   0  30G  0 disk /  

[root@ip-172-31-36-60 ~]# resize2fs /dev/xvde  
resize2fs 1.41.12 (17-May-2010)  
Filesystem at /dev/xvde is mounted on /; on-line resizing required  
old desc_blocks = 1, new_desc_blocks = 2  
Performing an on-line resize of /dev/xvde to 7864320 (4k) blocks.  
The filesystem on /dev/xvde is now 7864320 blocks long.  
  
[root@ip-172-31-36-60 ~]# df -h  
Filesystem      Size  Used Avail Use% Mounted on  
/dev/xvde        30G  778M   28G   3% /  
tmpfs           7.4G     0  7.4G   0% /dev/shm  
```
4. Disable transparent hugepage support  
   Add transparent_hugepage=never at the end of kernel line in /etc/grub.conf file.  
```
[root@ip-172-31-36-60 ~]# vi /etc/grub.conf
    default=0
    timeout=1

    title CentOS-6.5-x86_64-GA-03 2.6.32-431.el6.x86_64
        root (hd0)
        kernel /boot/vmlinuz-2.6.32-431.el6.x86_64 root=LABEL=centos_root ro transparent_hugepage=never
        initrd /boot/initramfs-2.6.32-431.el6.x86_64.img
```
5. List your network interface configuration   
```
[root@ip-172-31-36-60 ~]# ifconfig  
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
```
6. Show that forward and reverse host lookups are correctly resolved  
For /etc/hosts, use getent  
```
[root@ip-172-31-36-60 ~]# getent hosts  
127.0.0.1       localhost.localdomain localhost  
127.0.0.1       localhost6.localdomain6 localhost6  
```
For DNS, use nslookup
```
[root@ip-172-31-36-60 ~]# yum install bind-utils  
[root@ip-172-31-36-60 ~]# nslookup localhost  
    Server:         172.31.0.2  
    Address:        172.31.0.2#53  
  
    Name:   localhost  
    Address: 127.0.0.1  
```

6. Show the nscd service is running  
```
[root@ip-172-31-36-60 ~]# service nscd status  
nscd: unrecognized service  

[root@ip-172-31-36-60 ~]# yum install nscd  

[root@ip-172-31-36-60 ~]# service nscd start  
Starting nscd:                                             [  OK  ]  

[root@ip-172-31-36-60 ~]# service nscd status  
nscd (pid  1195) is running...  

```

7. Show the ntpd service is running
```
[root@ip-172-31-36-60 ~]# service ntpd status  
ntpd: unrecognized service  

[root@ip-172-31-36-60 ~]# yum install ntp  

[root@ip-172-31-36-60 ~]# service ntpd start  
Starting ntpd:                                             [  OK  ]  

[root@ip-172-31-36-60 ~]# service ntpd status  
ntpd (pid  1171) is running...  
```
  
8. Install cloudera-manager-server  
```
[root@ip-172-31-36-60 ~]# cd /etc/yum.repos.d
[root@ip-172-31-36-60 ~]# yum install wget
[root@ip-172-31-36-60 ~]# wget https://archive.cloudera.com/cm5/redhat/6/x86_64/cm/cloudera-manager.repo
[root@ip-172-31-36-60 ~]# yum install cloudera-manager-daemons cloudera-manager-server  
[root@ip-172-31-36-60 ~]# /usr/share/cmf/schema/scm_prepare_database.sh mysql cm root 123456  
[root@ip-172-31-36-60 ~]# service cloudera-scm-server start  
```
  
Use the below command to check if start failed.
```
[root@ip-172-31-36-60 ~]# tail -f /var/log/cloudera-scm-server/cloudera-scm-server.log
```

Open the browser with URL http://Servername:7180
username:admin,password:admin

9. Other steps  
9.1. Disable SELinux  
```
[root@ip-172-31-36-60 ~]# vi /etc/selinux/config  
SELINUX=disabled  
```
  
9.2. Disable and stop IPTables  
```
[root@ip-172-31-36-60 ~]# chkconfig --level 35 iptables off  
[root@ip-172-31-36-60 ~]# /etc/init.d/iptables stop  
```

9.3 Install java(optional)
[root@ip-172-31-36-60 ~]# yum install oracle-j2sdk1.7

