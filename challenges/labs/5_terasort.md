```
[root@ip-172-31-32-20 ~]# su - zhou
[zhou@ip-172-31-32-20 ~]$ kinit zhou
Password for zhou@ZEBRA716.CN:
[zhou@ip-172-31-32-20 ~]$ time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar terasort -Dmapred.reduce.tasks=6 /user/zhou/tgen /user/zhou/terasort
17/05/12 03:24:04 INFO terasort.TeraSort: starting
17/05/12 03:24:07 INFO hdfs.DFSClient: Created token for zhou: HDFS_DELEGATION_TOKEN owner=zhou@ZEBRA716.CN, renewer=yarn, realUser=, issueDate=1494559447820, maxDate=1495164247820, sequenceNumber=1, masterKeyId=2 on 172.31.32.20:8020
17/05/12 03:24:07 INFO security.TokenCache: Got dt for hdfs://ip-172-31-32-20.us-west-2.compute.internal:8020; Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.32.20:8020, Ident: (token for zhou: HDFS_DELEGATION_TOKEN owner=zhou@ZEBRA716.CN, renewer=yarn, realUser=, issueDate=1494559447820, maxDate=1495164247820, sequenceNumber=1, masterKeyId=2)
17/05/12 03:24:08 INFO input.FileInputFormat: Total input paths to process : 6
Spent 522ms computing base-splits.
Spent 5ms computing TeraScheduler splits.
Computing input splits took 528ms
Sampling 10 splits of 102
Making 6 from 100000 sampled records
Computing parititions took 1127ms
Spent 1658ms computing partitions.
17/05/12 03:24:09 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-32-20.us-west-2.compute.internal/172.31.32.20:8032
17/05/12 03:24:10 INFO mapreduce.JobSubmitter: number of splits:102
17/05/12 03:24:10 INFO Configuration.deprecation: mapred.reduce.tasks is deprecated. Instead, use mapreduce.job.reduces
17/05/12 03:24:10 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1494559196909_0001
17/05/12 03:24:10 INFO mapreduce.JobSubmitter: Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.32.20:8020, Ident: (token for zhou: HDFS_DELEGATION_TOKEN owner=zhou@ZEBRA716.CN, renewer=yarn, realUser=, issueDate=1494559447820, maxDate=1495164247820, sequenceNumber=1, masterKeyId=2)
17/05/12 03:24:11 INFO impl.YarnClientImpl: Submitted application application_1494559196909_0001
17/05/12 03:24:11 INFO mapreduce.Job: The url to track the job: http://ip-172-31-32-20.us-west-2.compute.internal:8088/proxy/application_1494559196909_0001/
17/05/12 03:24:11 INFO mapreduce.Job: Running job: job_1494559196909_0001
17/05/12 03:24:23 INFO mapreduce.Job: Job job_1494559196909_0001 running in uber mode : false
17/05/12 03:24:23 INFO mapreduce.Job:  map 0% reduce 0%
17/05/12 03:24:31 INFO mapreduce.Job:  map 1% reduce 0%
17/05/12 03:24:38 INFO mapreduce.Job:  map 3% reduce 0%
17/05/12 03:24:39 INFO mapreduce.Job:  map 4% reduce 0%
17/05/12 03:24:42 INFO mapreduce.Job:  map 6% reduce 0%
17/05/12 03:24:43 INFO mapreduce.Job:  map 10% reduce 0%
17/05/12 03:24:47 INFO mapreduce.Job:  map 11% reduce 0%
17/05/12 03:24:48 INFO mapreduce.Job:  map 13% reduce 0%
17/05/12 03:24:54 INFO mapreduce.Job:  map 14% reduce 0%
17/05/12 03:24:55 INFO mapreduce.Job:  map 20% reduce 0%
17/05/12 03:24:58 INFO mapreduce.Job:  map 22% reduce 0%
17/05/12 03:25:02 INFO mapreduce.Job:  map 23% reduce 0%
17/05/12 03:25:06 INFO mapreduce.Job:  map 26% reduce 0%
17/05/12 03:25:07 INFO mapreduce.Job:  map 30% reduce 0%
17/05/12 03:25:09 INFO mapreduce.Job:  map 31% reduce 0%
17/05/12 03:25:16 INFO mapreduce.Job:  map 33% reduce 0%
17/05/12 03:25:17 INFO mapreduce.Job:  map 35% reduce 0%
17/05/12 03:25:18 INFO mapreduce.Job:  map 37% reduce 0%
17/05/12 03:25:19 INFO mapreduce.Job:  map 39% reduce 0%
17/05/12 03:25:20 INFO mapreduce.Job:  map 40% reduce 0%
17/05/12 03:25:24 INFO mapreduce.Job:  map 41% reduce 0%
17/05/12 03:25:25 INFO mapreduce.Job:  map 43% reduce 0%
17/05/12 03:25:28 INFO mapreduce.Job:  map 44% reduce 0%
17/05/12 03:25:30 INFO mapreduce.Job:  map 47% reduce 0%
17/05/12 03:25:31 INFO mapreduce.Job:  map 49% reduce 0%
17/05/12 03:25:32 INFO mapreduce.Job:  map 50% reduce 0%
17/05/12 03:25:34 INFO mapreduce.Job:  map 52% reduce 0%
17/05/12 03:25:40 INFO mapreduce.Job:  map 54% reduce 0%
17/05/12 03:25:41 INFO mapreduce.Job:  map 55% reduce 0%
17/05/12 03:25:42 INFO mapreduce.Job:  map 58% reduce 0%
17/05/12 03:25:43 INFO mapreduce.Job:  map 59% reduce 0%
17/05/12 03:25:44 INFO mapreduce.Job:  map 61% reduce 0%
17/05/12 03:25:46 INFO mapreduce.Job:  map 62% reduce 0%
17/05/12 03:25:52 INFO mapreduce.Job:  map 63% reduce 0%
17/05/12 03:25:53 INFO mapreduce.Job:  map 64% reduce 0%
17/05/12 03:25:54 INFO mapreduce.Job:  map 69% reduce 0%
17/05/12 03:25:55 INFO mapreduce.Job:  map 71% reduce 0%
17/05/12 03:26:01 INFO mapreduce.Job:  map 72% reduce 0%
17/05/12 03:26:03 INFO mapreduce.Job:  map 74% reduce 0%
17/05/12 03:26:04 INFO mapreduce.Job:  map 75% reduce 0%
17/05/12 03:26:06 INFO mapreduce.Job:  map 77% reduce 0%
17/05/12 03:26:07 INFO mapreduce.Job:  map 79% reduce 0%
17/05/12 03:26:08 INFO mapreduce.Job:  map 80% reduce 0%
17/05/12 03:26:13 INFO mapreduce.Job:  map 82% reduce 0%
17/05/12 03:26:15 INFO mapreduce.Job:  map 83% reduce 0%
17/05/12 03:26:16 INFO mapreduce.Job:  map 85% reduce 0%
17/05/12 03:26:18 INFO mapreduce.Job:  map 87% reduce 0%
17/05/12 03:26:20 INFO mapreduce.Job:  map 89% reduce 0%
17/05/12 03:26:22 INFO mapreduce.Job:  map 91% reduce 0%
17/05/12 03:26:24 INFO mapreduce.Job:  map 91% reduce 4%
17/05/12 03:26:27 INFO mapreduce.Job:  map 92% reduce 4%
17/05/12 03:26:29 INFO mapreduce.Job:  map 93% reduce 7%
17/05/12 03:26:30 INFO mapreduce.Job:  map 93% reduce 8%
17/05/12 03:26:31 INFO mapreduce.Job:  map 95% reduce 8%
17/05/12 03:26:32 INFO mapreduce.Job:  map 95% reduce 15%
17/05/12 03:26:34 INFO mapreduce.Job:  map 95% reduce 17%
17/05/12 03:26:35 INFO mapreduce.Job:  map 96% reduce 22%
17/05/12 03:26:37 INFO mapreduce.Job:  map 97% reduce 23%
17/05/12 03:26:38 INFO mapreduce.Job:  map 98% reduce 25%
17/05/12 03:26:41 INFO mapreduce.Job:  map 100% reduce 26%
17/05/12 03:26:42 INFO mapreduce.Job:  map 100% reduce 29%
17/05/12 03:26:44 INFO mapreduce.Job:  map 100% reduce 41%
17/05/12 03:26:46 INFO mapreduce.Job:  map 100% reduce 52%
17/05/12 03:26:48 INFO mapreduce.Job:  map 100% reduce 59%
17/05/12 03:26:49 INFO mapreduce.Job:  map 100% reduce 65%
17/05/12 03:26:51 INFO mapreduce.Job:  map 100% reduce 67%
17/05/12 03:26:52 INFO mapreduce.Job:  map 100% reduce 69%
17/05/12 03:26:54 INFO mapreduce.Job:  map 100% reduce 72%
17/05/12 03:26:55 INFO mapreduce.Job:  map 100% reduce 75%
17/05/12 03:26:57 INFO mapreduce.Job:  map 100% reduce 78%
17/05/12 03:26:58 INFO mapreduce.Job:  map 100% reduce 85%
17/05/12 03:27:00 INFO mapreduce.Job:  map 100% reduce 88%
17/05/12 03:27:01 INFO mapreduce.Job:  map 100% reduce 91%
17/05/12 03:27:02 INFO mapreduce.Job:  map 100% reduce 93%
17/05/12 03:27:03 INFO mapreduce.Job:  map 100% reduce 95%
17/05/12 03:27:04 INFO mapreduce.Job:  map 100% reduce 96%
17/05/12 03:27:07 INFO mapreduce.Job:  map 100% reduce 98%
17/05/12 03:27:10 INFO mapreduce.Job:  map 100% reduce 99%
17/05/12 03:27:12 INFO mapreduce.Job:  map 100% reduce 100%
17/05/12 03:27:13 INFO mapreduce.Job: Job job_1494559196909_0001 completed successfully
17/05/12 03:27:13 INFO mapreduce.Job: Counters: 49
        File System Counters
                FILE: Number of bytes read=2934892106
                FILE: Number of bytes written=5821522875
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=6553614994
                HDFS: Number of bytes written=6553600000
                HDFS: Number of read operations=324
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=12
        Job Counters
                Launched map tasks=102
                Launched reduce tasks=6
                Data-local map tasks=102
                Total time spent by all maps in occupied slots (ms)=1002412
                Total time spent by all reduces in occupied slots (ms)=252479
                Total time spent by all map tasks (ms)=1002412
                Total time spent by all reduce tasks (ms)=252479
                Total vcore-seconds taken by all map tasks=1002412
                Total vcore-seconds taken by all reduce tasks=252479
                Total megabyte-seconds taken by all map tasks=1026469888
                Total megabyte-seconds taken by all reduce tasks=258538496
        Map-Reduce Framework
                Map input records=65536000
                Map output records=65536000
                Map output bytes=6684672000
                Map output materialized bytes=2873051907
                Input split bytes=14994
                Combine input records=0
                Combine output records=0
                Reduce input groups=65536000
                Reduce shuffle bytes=2873051907
                Reduce input records=65536000
                Reduce output records=65536000
                Spilled Records=131072000
                Shuffled Maps =612
                Failed Shuffles=0
                Merged Map outputs=612
                GC time elapsed (ms)=16040
                CPU time spent (ms)=728050
                Physical memory (bytes) snapshot=56690835456
                Virtual memory (bytes) snapshot=168939081728
                Total committed heap usage (bytes)=66724560896
        Shuffle Errors
                BAD_ID=0
                CONNECTION=0
                IO_ERROR=0
                WRONG_LENGTH=0
                WRONG_MAP=0
                WRONG_REDUCE=0
        File Input Format Counters
                Bytes Read=6553600000
        File Output Format Counters
                Bytes Written=6553600000
17/05/12 03:27:13 INFO terasort.TeraSort: done

real    3m10.563s
user    0m9.971s
sys     0m1.167s
```  

