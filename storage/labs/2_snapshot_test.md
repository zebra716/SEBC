1. Create a precious directory in HDFS; copy the ZIP course file into it.
  
Put SEBC-Shanghai.zip file into server using psftp
  

```
C:\Windows\System32>psftp s1
  
Using username "root".
  
Remote working directory is /root
  

  
psftp> lcd "C:\Users\BZ186007\Desktop\SEBC-Shanghai"
  
New local directory is C:\Users\BZ186007\Desktop\SEBC-Shanghai
  

  
psftp> cd /tmp
  
Remote directory is now /tmp
  

  
psftp> put SEBC-Shanghai.zip
  
local:SEBC-Shanghai.zip => remote:/tmp/SEBC-Shanghai.zip
  
```

  
Copy SEBC-Shanghai.zip file into the precious directory /user/SEBC
  
```
[root@ip-172-31-36-60 jars]# su - zebra716
  
[zebra716@ip-172-31-36-60 ~]$ hadoop fs -mkdir /user/SEBC
  
[zebra716@ip-172-31-36-60 ~]$ hadoop fs -copyFromLocal /tmp/SEBC-Shanghai.zip /user/SEBC/SEBC-Shanghai.zip
  
```

  
2. Enable snapshots for precious
  
```
[root@ip-172-31-36-60 jars]# su - hdfs
  
[hdfs@ip-172-31-36-60 ~]$ hdfs dfsadmin -allowSnapshot /user/SEBC
  
Allowing snaphot on /user/SEBC succeeded
  
```

  
3. Create a snapshot called sebc-hdfs-test
  
```
[hdfs@ip-172-31-36-60 ~]$ hdfs dfs -createSnapshot /user/SEBC sebc-hdfs-test
  
Created snapshot /user/SEBC/.snapshot/sebc-hdfs-test
  
```

  
4. Delete the directory
  
```
[zebra716@ip-172-31-36-60 ~]$ hadoop fs -rm /user/SEBC/SEBC-Shanghai.zip
  
17/05/09 11:43:48 INFO fs.TrashPolicyDefault: Moved: 'hdfs://ip-172-31-36-60.us-west-2.compute.internal:8020/user/SEBC/SEBC-Shanghai.zip' to trash at: hdfs://ip-172-31-36-60.us-west-2.compute.internal:8020/user/zebra716/.Trash/Current/user/SEBC/SEBC-Shanghai.zip
  
```

  
5. Delete the ZIP file
  
```
[zebra716@ip-172-31-36-60 ~]$ hadoop fs -rmr /user/SEBC
  
rmr: DEPRECATED: Please use 'rm -r' instead.
  
rmr: Failed to move to trash: hdfs://ip-172-31-36-60.us-west-2.compute.internal:8020/user/SEBC: The directory /user/SEBC cannot be deleted since /user/SEBC is snapshottable and already has snapshots
  
```

  
6. Restore the deleted file
  
```
[zebra716@ip-172-31-36-60 ~]$ hdfs dfs -cp /user/SEBC/.snapshot/sebc-hdfs-test/SEBC-Shanghai.zip /user/SEBC
  
[zebra716@ip-172-31-36-60 ~]$ hadoop fs -ls /user/SEBC/
  
Found 1 item
  
-rw-r--r--   3 zebra716 supergroup     474957 2017-05-09 11:47 /user/SEBC/SEBC-Shanghai.zip
  
```

  
7. Capture the NameNode web UI screen that lists snapshots in storage/labs/2_snapshot_list.png.
  
