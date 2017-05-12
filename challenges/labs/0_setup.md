Challenge Setup  
List the cloud provider you are using (AWS, GCE, Azure, other)  
```
AWS
```  

List your instances by their IP address and DNS name  
```
Public DNS (IPv4)	                                   IPv4 Public IP    Private DNS                                    Private IPs  
ec2-54-191-203-73.us-west-2.compute.amazonaws.com    54.191.203.73     ip-172-31-41-99.us-west-2.compute.internal     172.31.41.99
ec2-54-203-128-196.us-west-2.compute.amazonaws.com   54.203.128.196    ip-172-31-32-20.us-west-2.compute.internal     172.31.32.20
ec2-54-203-1-223.us-west-2.compute.amazonaws.com     54.203.1.223      ip-172-31-39-68.us-west-2.compute.internal     172.31.39.68
ec2-54-191-121-114.us-west-2.compute.amazonaws.com   54.191.121.114    ip-172-31-33-100.us-west-2.compute.internal    172.31.33.100
ec2-54-203-204-67.us-west-2.compute.amazonaws.com    54.203.204.67     ip-172-31-42-121.us-west-2.compute.internal    172.31.42.121
```  

List the Linux release you are using  
```
CentOS-6.5-GA-03.3-f4325b48-37b0-405a-9847-236c64622e3e-ami-6be4dc02.2 (ami-b6bdde86)
```  

List the file system capacity for the first node  
```
[root@ip-172-31-41-99 ~]# df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvde        30G  785M   28G   3% /
tmpfs           7.4G     0  7.4G   0% /dev/shm
```  

List the command and output for yum repolist enabled  
```
[root@ip-172-31-41-99 ~]# yum repolist enabled
Loaded plugins: fastestmirror, presto
Loading mirror speeds from cached hostfile
 * base: mirror.chpc.utah.edu
 * extras: mirrors.unifiedlayer.com
 * updates: mirror.pac-12.org
repo id                        repo name                                  status
base                           CentOS-6 - Base                            6,706
extras                         CentOS-6 - Extras                             64
updates                        CentOS-6 - Updates                           270
repolist: 7,040
```  

List the /etc/passwd entries for zhou and chen  
```
[root@ip-172-31-41-99 ~]#  cat /etc/passwd|grep zhou
zhou:x:2800:2800::/home/zhou:/bin/bash
```  

List the /etc/group entries for shanghai and beijing  
```
[root@ip-172-31-41-99 ~]#  cat /etc/passwd|grep chen
chen:x:2900:2900::/home/chen:/bin/bash
```  
