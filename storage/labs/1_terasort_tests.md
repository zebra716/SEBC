1. Create an end-user Linux account named with your GitHub handle  
1.1 Make sure this Linux account is added to all cluster nodes  
```
useradd -m zebra716 -d /home/zebra716 -e 12/31/2999 -s /bin/bash  
[root@ip-172-31-36-60 jars]# passwd zebra716  
Changing password for user zebra716.  
New password:  
BAD PASSWORD: it is too simplistic/systematic  
BAD PASSWORD: is too simple  
Retype new password:  
passwd: all authentication tokens updated successfully.  
```
  
1.2 Create an HDFS directory under /user  
```
su - hdfs  
hadoop fs -chmod 777 /user  
  
exit  
  
su - zebra716  
hadoop fs -mkdir /user/zebra716  
```
  
1.3 Run the following exercises under this user account  
  
2. Create a 10 GB file using teragen  
2.1 Set the number of mappers to four  
2.2 Limit the block size to 32 MB  
2.3 Land the output in your user's home directory  
2.4 Use the time command to report the job's duration  
```
  
[root@ip-172-31-36-60 jars]# date  
Tue May  9 10:45:58 UTC 2017  
[root@ip-172-31-36-60 jars]# hadoop jar /opt/cloudera/parcels/CDH/jars/hadoop-examples.jar teragen -Dmapred.map.tasks=4 -D dfs.blocksize=33554432 107374180 /user/zebra716/teragen10GB  
17/05/09 10:46:02 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-36-60.us-west-2.compute.internal/172.31.36.60:8032  
17/05/09 10:46:03 INFO terasort.TeraGen: Generating 107374180 using 4  
17/05/09 10:46:03 INFO mapreduce.JobSubmitter: number of splits:4  
17/05/09 10:46:03 INFO Configuration.deprecation: mapred.map.tasks is deprecated. Instead, use mapreduce.job.maps  
17/05/09 10:46:04 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1494308857993_0007  
17/05/09 10:46:04 INFO impl.YarnClientImpl: Submitted application application_1494308857993_0007  
17/05/09 10:46:04 INFO mapreduce.Job: The url to track the job: http://ip-172-31-36-60.us-west-2.compute.internal:8088/proxy/application_1494308857993_0007/  
17/05/09 10:46:04 INFO mapreduce.Job: Running job: job_1494308857993_0007  
17/05/09 10:46:11 INFO mapreduce.Job: Job job_1494308857993_0007 running in uber mode : false  
17/05/09 10:46:11 INFO mapreduce.Job:  map 0% reduce 0%  
17/05/09 10:46:31 INFO mapreduce.Job:  map 9% reduce 0%  
17/05/09 10:46:32 INFO mapreduce.Job:  map 17% reduce 0%  
17/05/09 10:46:37 INFO mapreduce.Job:  map 20% reduce 0%  
17/05/09 10:46:38 INFO mapreduce.Job:  map 24% reduce 0%  
17/05/09 10:46:44 INFO mapreduce.Job:  map 27% reduce 0%  
17/05/09 10:46:45 INFO mapreduce.Job:  map 30% reduce 0%  
17/05/09 10:46:50 INFO mapreduce.Job:  map 33% reduce 0%  
17/05/09 10:46:51 INFO mapreduce.Job:  map 36% reduce 0%  
17/05/09 10:46:56 INFO mapreduce.Job:  map 39% reduce 0%  
17/05/09 10:46:57 INFO mapreduce.Job:  map 40% reduce 0%  
17/05/09 10:47:02 INFO mapreduce.Job:  map 43% reduce 0%  
17/05/09 10:47:03 INFO mapreduce.Job:  map 45% reduce 0%  
17/05/09 10:47:08 INFO mapreduce.Job:  map 47% reduce 0%  
17/05/09 10:47:09 INFO mapreduce.Job:  map 49% reduce 0%  
17/05/09 10:47:14 INFO mapreduce.Job:  map 52% reduce 0%  
17/05/09 10:47:15 INFO mapreduce.Job:  map 54% reduce 0%  
17/05/09 10:47:19 INFO mapreduce.Job:  map 55% reduce 0%  
17/05/09 10:47:20 INFO mapreduce.Job:  map 57% reduce 0%  
17/05/09 10:47:21 INFO mapreduce.Job:  map 59% reduce 0%  
17/05/09 10:47:25 INFO mapreduce.Job:  map 60% reduce 0%  
17/05/09 10:47:26 INFO mapreduce.Job:  map 61% reduce 0%  
17/05/09 10:47:27 INFO mapreduce.Job:  map 64% reduce 0%  
17/05/09 10:47:31 INFO mapreduce.Job:  map 66% reduce 0%  
17/05/09 10:47:32 INFO mapreduce.Job:  map 67% reduce 0%  
17/05/09 10:47:33 INFO mapreduce.Job:  map 68% reduce 0%  
17/05/09 10:47:37 INFO mapreduce.Job:  map 71% reduce 0%  
17/05/09 10:47:38 INFO mapreduce.Job:  map 73% reduce 0%  
17/05/09 10:47:43 INFO mapreduce.Job:  map 75% reduce 0%  
17/05/09 10:47:44 INFO mapreduce.Job:  map 78% reduce 0%  
17/05/09 10:47:49 INFO mapreduce.Job:  map 80% reduce 0%  
17/05/09 10:47:50 INFO mapreduce.Job:  map 82% reduce 0%  
17/05/09 10:47:55 INFO mapreduce.Job:  map 84% reduce 0%  
17/05/09 10:47:56 INFO mapreduce.Job:  map 87% reduce 0%  
17/05/09 10:48:01 INFO mapreduce.Job:  map 89% reduce 0%  
17/05/09 10:48:02 INFO mapreduce.Job:  map 92% reduce 0%  
17/05/09 10:48:07 INFO mapreduce.Job:  map 94% reduce 0%  
17/05/09 10:48:08 INFO mapreduce.Job:  map 96% reduce 0%  
17/05/09 10:48:09 INFO mapreduce.Job:  map 97% reduce 0%  
17/05/09 10:48:13 INFO mapreduce.Job:  map 98% reduce 0%  
17/05/09 10:48:14 INFO mapreduce.Job:  map 100% reduce 0%  
17/05/09 10:48:16 INFO mapreduce.Job: Job job_1494308857993_0007 completed successfully  
17/05/09 10:48:16 INFO mapreduce.Job: Counters: 33  
        File System Counters  
                FILE: Number of bytes read=0  
                FILE: Number of bytes written=510476  
                FILE: Number of read operations=0  
                FILE: Number of large read operations=0  
                FILE: Number of write operations=0  
                HDFS: Number of bytes read=344  
                HDFS: Number of bytes written=10737418000  
                HDFS: Number of read operations=16  
                HDFS: Number of large read operations=0  
                HDFS: Number of write operations=8  
        Job Counters  
                Launched map tasks=4  
                Other local map tasks=4  
                Total time spent by all maps in occupied slots (ms)=469668  
                Total time spent by all reduces in occupied slots (ms)=0  
                Total time spent by all map tasks (ms)=469668  
                Total vcore-milliseconds taken by all map tasks=469668  
                Total megabyte-milliseconds taken by all map tasks=480940032  
        Map-Reduce Framework  
                Map input records=107374180  
                Map output records=107374180  
                Input split bytes=344  
                Spilled Records=0  
                Failed Shuffles=0  
                Merged Map outputs=0  
                GC time elapsed (ms)=1694  
                CPU time spent (ms)=173490  
                Physical memory (bytes) snapshot=1027657728  
                Virtual memory (bytes) snapshot=6266068992  
                Total committed heap usage (bytes)=847773696  
                Peak Map Physical memory (bytes)=385757184  
                Peak Map Virtual memory (bytes)=1571057664  
        org.apache.hadoop.examples.terasort.TeraGen$Counters  
                CHECKSUM=230593858507236407  
        File Input Format Counters  
                Bytes Read=0  
        File Output Format Counters  
                Bytes Written=10737418000  
[root@ip-172-31-36-60 jars]# date  
Tue May  9 10:49:38 UTC 2017  
```
  
3. Run the terasort command on this file  
3.1 Use the time command to report the job's duration  
3.2 Land the result under your user's home directory  
```

[root@ip-172-31-36-60 jars]# date  
Tue May  9 10:50:41 UTC 2017  
  
[root@ip-172-31-36-60 jars]# hadoop jar /opt/cloudera/parcels/CDH/jars/hadoop-examples.jar terasort /user/zebra716/teragen10GB /user/zebra716/teragen10GB_terasort  
17/05/09 10:50:42 INFO terasort.TeraSort: starting  
17/05/09 10:50:44 INFO input.FileInputFormat: Total input paths to process : 4  
Spent 288ms computing base-splits.  
Spent 6ms computing TeraScheduler splits.  
Computing input splits took 295ms  
Sampling 10 splits of 320  
Making 4 from 100000 sampled records  
Computing parititions took 1123ms  
Spent 1422ms computing partitions.  
17/05/09 10:50:45 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-36-60.us-west-2.compute.internal/172.31.36.60:8032  
17/05/09 10:50:45 INFO mapreduce.JobSubmitter: number of splits:320  
17/05/09 10:50:46 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1494308857993_0008  
17/05/09 10:50:46 INFO impl.YarnClientImpl: Submitted application application_1494308857993_0008  
17/05/09 10:50:46 INFO mapreduce.Job: The url to track the job: http://ip-172-31-36-60.us-west-2.compute.internal:8088/proxy/application_1494308857993_0008/  
17/05/09 10:50:46 INFO mapreduce.Job: Running job: job_1494308857993_0008  
17/05/09 10:50:54 INFO mapreduce.Job: Job job_1494308857993_0008 running in uber mode : false  
17/05/09 10:50:54 INFO mapreduce.Job:  map 0% reduce 0%  
17/05/09 10:51:07 INFO mapreduce.Job:  map 1% reduce 0%  
17/05/09 10:51:09 INFO mapreduce.Job:  map 2% reduce 0%  
17/05/09 10:51:19 INFO mapreduce.Job:  map 3% reduce 0%  
17/05/09 10:51:23 INFO mapreduce.Job:  map 4% reduce 0%  
17/05/09 10:51:30 INFO mapreduce.Job:  map 5% reduce 0%  
17/05/09 10:51:35 INFO mapreduce.Job:  map 6% reduce 0%  
17/05/09 10:51:37 INFO mapreduce.Job:  map 7% reduce 0%  
17/05/09 10:51:42 INFO mapreduce.Job:  map 8% reduce 0%  
17/05/09 10:51:51 INFO mapreduce.Job:  map 9% reduce 0%  
17/05/09 10:51:54 INFO mapreduce.Job:  map 10% reduce 0%  
17/05/09 10:52:04 INFO mapreduce.Job:  map 11% reduce 0%  
17/05/09 10:52:07 INFO mapreduce.Job:  map 12% reduce 0%  
17/05/09 10:52:17 INFO mapreduce.Job:  map 13% reduce 0%  
17/05/09 10:52:18 INFO mapreduce.Job:  map 14% reduce 0%  
17/05/09 10:52:30 INFO mapreduce.Job:  map 16% reduce 0%  
17/05/09 10:52:42 INFO mapreduce.Job:  map 17% reduce 0%  
17/05/09 10:52:43 INFO mapreduce.Job:  map 18% reduce 0%  
17/05/09 10:52:54 INFO mapreduce.Job:  map 20% reduce 0%  
17/05/09 10:52:58 INFO mapreduce.Job:  map 21% reduce 0%  
17/05/09 10:53:06 INFO mapreduce.Job:  map 22% reduce 0%  
17/05/09 10:53:12 INFO mapreduce.Job:  map 23% reduce 0%  
17/05/09 10:53:19 INFO mapreduce.Job:  map 24% reduce 0%  
17/05/09 10:53:23 INFO mapreduce.Job:  map 25% reduce 0%  
17/05/09 10:53:30 INFO mapreduce.Job:  map 26% reduce 0%  
17/05/09 10:53:35 INFO mapreduce.Job:  map 27% reduce 0%  
17/05/09 10:53:42 INFO mapreduce.Job:  map 28% reduce 0%  
17/05/09 10:53:49 INFO mapreduce.Job:  map 29% reduce 0%  
17/05/09 10:53:54 INFO mapreduce.Job:  map 30% reduce 0%  
17/05/09 10:54:01 INFO mapreduce.Job:  map 31% reduce 0%  
17/05/09 10:54:03 INFO mapreduce.Job:  map 32% reduce 0%  
17/05/09 10:54:14 INFO mapreduce.Job:  map 33% reduce 0%  
17/05/09 10:54:18 INFO mapreduce.Job:  map 34% reduce 0%  
17/05/09 10:54:19 INFO mapreduce.Job:  map 35% reduce 0%  
17/05/09 10:54:31 INFO mapreduce.Job:  map 36% reduce 0%  
17/05/09 10:54:32 INFO mapreduce.Job:  map 37% reduce 0%  
17/05/09 10:54:41 INFO mapreduce.Job:  map 38% reduce 0%  
17/05/09 10:54:46 INFO mapreduce.Job:  map 39% reduce 0%  
17/05/09 10:54:52 INFO mapreduce.Job:  map 40% reduce 0%  
17/05/09 10:54:57 INFO mapreduce.Job:  map 41% reduce 0%  
17/05/09 10:55:03 INFO mapreduce.Job:  map 42% reduce 0%  
17/05/09 10:55:05 INFO mapreduce.Job:  map 43% reduce 0%  
17/05/09 10:55:14 INFO mapreduce.Job:  map 44% reduce 0%  
17/05/09 10:55:16 INFO mapreduce.Job:  map 45% reduce 0%  
17/05/09 10:55:26 INFO mapreduce.Job:  map 46% reduce 0%  
17/05/09 10:55:27 INFO mapreduce.Job:  map 47% reduce 0%  
17/05/09 10:55:37 INFO mapreduce.Job:  map 48% reduce 0%  
17/05/09 10:55:41 INFO mapreduce.Job:  map 49% reduce 0%  
17/05/09 10:55:48 INFO mapreduce.Job:  map 50% reduce 0%  
17/05/09 10:55:54 INFO mapreduce.Job:  map 51% reduce 0%  
17/05/09 10:55:57 INFO mapreduce.Job:  map 52% reduce 0%  
17/05/09 10:56:08 INFO mapreduce.Job:  map 53% reduce 0%  
17/05/09 10:56:09 INFO mapreduce.Job:  map 54% reduce 0%  
17/05/09 10:56:13 INFO mapreduce.Job:  map 55% reduce 0%  
17/05/09 10:56:21 INFO mapreduce.Job:  map 56% reduce 0%  
17/05/09 10:56:22 INFO mapreduce.Job:  map 57% reduce 0%  
17/05/09 10:56:32 INFO mapreduce.Job:  map 58% reduce 0%  
17/05/09 10:56:35 INFO mapreduce.Job:  map 59% reduce 0%  
17/05/09 10:56:43 INFO mapreduce.Job:  map 60% reduce 0%  
17/05/09 10:56:49 INFO mapreduce.Job:  map 61% reduce 0%  
17/05/09 10:56:53 INFO mapreduce.Job:  map 62% reduce 0%  
17/05/09 10:57:00 INFO mapreduce.Job:  map 63% reduce 0%  
17/05/09 10:57:06 INFO mapreduce.Job:  map 64% reduce 0%  
17/05/09 10:57:13 INFO mapreduce.Job:  map 65% reduce 0%  
17/05/09 10:57:16 INFO mapreduce.Job:  map 66% reduce 0%  
17/05/09 10:57:19 INFO mapreduce.Job:  map 67% reduce 0%  
17/05/09 10:57:28 INFO mapreduce.Job:  map 68% reduce 0%  
17/05/09 10:57:32 INFO mapreduce.Job:  map 69% reduce 0%  
17/05/09 10:57:39 INFO mapreduce.Job:  map 70% reduce 0%  
17/05/09 10:57:42 INFO mapreduce.Job:  map 71% reduce 0%  
17/05/09 10:57:50 INFO mapreduce.Job:  map 72% reduce 0%  
17/05/09 10:57:55 INFO mapreduce.Job:  map 73% reduce 0%  
17/05/09 10:58:00 INFO mapreduce.Job:  map 74% reduce 0%  
17/05/09 10:58:09 INFO mapreduce.Job:  map 75% reduce 0%  
17/05/09 10:58:10 INFO mapreduce.Job:  map 76% reduce 0%  
17/05/09 10:58:17 INFO mapreduce.Job:  map 77% reduce 0%  
17/05/09 10:58:23 INFO mapreduce.Job:  map 78% reduce 0%  
17/05/09 10:58:31 INFO mapreduce.Job:  map 79% reduce 0%  
17/05/09 10:58:34 INFO mapreduce.Job:  map 80% reduce 0%  
17/05/09 10:58:36 INFO mapreduce.Job:  map 81% reduce 0%  
17/05/09 10:58:44 INFO mapreduce.Job:  map 82% reduce 0%  
17/05/09 10:58:50 INFO mapreduce.Job:  map 83% reduce 0%  
17/05/09 10:59:03 INFO mapreduce.Job:  map 83% reduce 5%  
17/05/09 10:59:04 INFO mapreduce.Job:  map 83% reduce 8%  
17/05/09 10:59:05 INFO mapreduce.Job:  map 84% reduce 8%  
17/05/09 10:59:09 INFO mapreduce.Job:  map 84% reduce 11%  
17/05/09 10:59:10 INFO mapreduce.Job:  map 84% reduce 13%  
17/05/09 10:59:15 INFO mapreduce.Job:  map 84% reduce 15%  
17/05/09 10:59:16 INFO mapreduce.Job:  map 84% reduce 17%  
17/05/09 10:59:17 INFO mapreduce.Job:  map 85% reduce 17%  
17/05/09 10:59:19 INFO mapreduce.Job:  map 86% reduce 17%  
17/05/09 10:59:22 INFO mapreduce.Job:  map 86% reduce 19%  
17/05/09 10:59:23 INFO mapreduce.Job:  map 86% reduce 20%  
17/05/09 10:59:28 INFO mapreduce.Job:  map 86% reduce 21%  
17/05/09 10:59:33 INFO mapreduce.Job:  map 87% reduce 21%  
17/05/09 10:59:34 INFO mapreduce.Job:  map 87% reduce 22%  
17/05/09 10:59:43 INFO mapreduce.Job:  map 88% reduce 22%  
17/05/09 10:59:50 INFO mapreduce.Job:  map 89% reduce 22%  
17/05/09 10:59:55 INFO mapreduce.Job:  map 90% reduce 22%  
17/05/09 10:59:59 INFO mapreduce.Job:  map 90% reduce 23%  
17/05/09 11:00:07 INFO mapreduce.Job:  map 91% reduce 23%  
17/05/09 11:00:12 INFO mapreduce.Job:  map 92% reduce 23%  
17/05/09 11:00:18 INFO mapreduce.Job:  map 93% reduce 23%  
17/05/09 11:00:29 INFO mapreduce.Job:  map 94% reduce 23%  
17/05/09 11:00:34 INFO mapreduce.Job:  map 94% reduce 24%  
17/05/09 11:00:40 INFO mapreduce.Job:  map 95% reduce 24%  
17/05/09 11:00:41 INFO mapreduce.Job:  map 96% reduce 24%  
17/05/09 11:00:51 INFO mapreduce.Job:  map 97% reduce 24%  
17/05/09 11:01:01 INFO mapreduce.Job:  map 98% reduce 24%  
17/05/09 11:01:04 INFO mapreduce.Job:  map 98% reduce 25%  
17/05/09 11:01:09 INFO mapreduce.Job:  map 99% reduce 25%  
17/05/09 11:01:13 INFO mapreduce.Job:  map 100% reduce 25%  
17/05/09 11:01:17 INFO mapreduce.Job:  map 100% reduce 27%  
17/05/09 11:01:22 INFO mapreduce.Job:  map 100% reduce 44%  
17/05/09 11:01:23 INFO mapreduce.Job:  map 100% reduce 51%  
17/05/09 11:01:28 INFO mapreduce.Job:  map 100% reduce 53%  
17/05/09 11:01:29 INFO mapreduce.Job:  map 100% reduce 58%  
17/05/09 11:01:34 INFO mapreduce.Job:  map 100% reduce 60%  
17/05/09 11:01:35 INFO mapreduce.Job:  map 100% reduce 62%  
17/05/09 11:01:40 INFO mapreduce.Job:  map 100% reduce 65%  
17/05/09 11:01:41 INFO mapreduce.Job:  map 100% reduce 68%  
17/05/09 11:01:46 INFO mapreduce.Job:  map 100% reduce 70%  
17/05/09 11:01:47 INFO mapreduce.Job:  map 100% reduce 73%  
17/05/09 11:01:52 INFO mapreduce.Job:  map 100% reduce 75%  
17/05/09 11:01:53 INFO mapreduce.Job:  map 100% reduce 85%  
17/05/09 11:01:58 INFO mapreduce.Job:  map 100% reduce 87%  
17/05/09 11:01:59 INFO mapreduce.Job:  map 100% reduce 90%  
17/05/09 11:02:05 INFO mapreduce.Job:  map 100% reduce 91%  
17/05/09 11:02:06 INFO mapreduce.Job:  map 100% reduce 94%  
17/05/09 11:02:12 INFO mapreduce.Job:  map 100% reduce 96%  
17/05/09 11:02:18 INFO mapreduce.Job:  map 100% reduce 98%  
17/05/09 11:02:24 INFO mapreduce.Job:  map 100% reduce 99%  
17/05/09 11:02:27 INFO mapreduce.Job:  map 100% reduce 100%  
17/05/09 11:02:27 INFO mapreduce.Job: Job job_1494308857993_0008 completed successfully  
17/05/09 11:02:27 INFO mapreduce.Job: Counters: 53  
        File System Counters  
                FILE: Number of bytes read=4822147604  
                FILE: Number of bytes written=9561483465  
                FILE: Number of read operations=0  
                FILE: Number of large read operations=0  
                FILE: Number of write operations=0  
                HDFS: Number of bytes read=10737468560  
                HDFS: Number of bytes written=10737418000  
                HDFS: Number of read operations=972  
                HDFS: Number of large read operations=0  
                HDFS: Number of write operations=8  
        Job Counters  
                Launched map tasks=320  
                Launched reduce tasks=4  
                Data-local map tasks=320  
                Total time spent by all maps in occupied slots (ms)=3523019  
                Total time spent by all reduces in occupied slots (ms)=676970  
                Total time spent by all map tasks (ms)=3523019  
                Total time spent by all reduce tasks (ms)=676970  
                Total vcore-milliseconds taken by all map tasks=3523019  
                Total vcore-milliseconds taken by all reduce tasks=676970  
                Total megabyte-milliseconds taken by all map tasks=3607571456  
                Total megabyte-milliseconds taken by all reduce tasks=693217280  
        Map-Reduce Framework  
                Map input records=107374180  
                Map output records=107374180  
                Map output bytes=10952166360  
                Map output materialized bytes=4697507323  
                Input split bytes=50560  
                Combine input records=0  
                Combine output records=0  
                Reduce input groups=107374180  
                Reduce shuffle bytes=4697507323  
                Reduce input records=107374180  
                Reduce output records=107374180  
                Spilled Records=214748360  
                Shuffled Maps =1280  
                Failed Shuffles=0  
                Merged Map outputs=1280  
                GC time elapsed (ms)=44235  
                CPU time spent (ms)=1692050  
                Physical memory (bytes) snapshot=160400609280  
                Virtual memory (bytes) snapshot=509256716288  
                Total committed heap usage (bytes)=183847354368  
                Peak Map Physical memory (bytes)=523812864  
                Peak Map Virtual memory (bytes)=1588215808  
                Peak Reduce Physical memory (bytes)=986750976  
                Peak Reduce Virtual memory (bytes)=1586716672  
        Shuffle Errors  
                BAD_ID=0  
                CONNECTION=0  
                IO_ERROR=0  
                WRONG_LENGTH=0  
                WRONG_MAP=0  
                WRONG_REDUCE=0  
        File Input Format Counters  
                Bytes Read=10737418000  
        File Output Format Counters  
                Bytes Written=10737418000  
17/05/09 11:02:27 INFO terasort.TeraSort: done  
You have new mail in /var/spool/mail/root  
  
[root@ip-172-31-36-60 jars]# date  
Tue May  9 11:02:46 UTC 2017  
```
  
4. Report your work in storage/labs/1_terasort_tests.md, including:  
4.1 The full teragen and command you used and the job output  
4.2 The same for terasort  
4.3 Include the time result of each job  
