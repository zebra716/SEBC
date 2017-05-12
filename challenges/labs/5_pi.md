```
[root@ip-172-31-32-20 ~]# su - chen
[chen@ip-172-31-32-20 ~]$ kinit chen
Password for chen@ZEBRA716.CN:
[chen@ip-172-31-32-20 ~]$ time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar pi 8 10
Number of Maps  = 8
Samples per Map = 10
Wrote input for Map #0
Wrote input for Map #1
Wrote input for Map #2
Wrote input for Map #3
Wrote input for Map #4
Wrote input for Map #5
Wrote input for Map #6
Wrote input for Map #7
Starting Job
17/05/12 03:30:47 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-32-20.us-west-2.compute.internal/172.31.32.20:8032
17/05/12 03:30:47 INFO hdfs.DFSClient: Created token for chen: HDFS_DELEGATION_TOKEN owner=chen@ZEBRA716.CN, renewer=yarn, realUser=, issueDate=1494559847322, maxDate=1495164647322, sequenceNumber=2, masterKeyId=2 on 172.31.32.20:8020
17/05/12 03:30:47 INFO security.TokenCache: Got dt for hdfs://ip-172-31-32-20.us-west-2.compute.internal:8020; Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.32.20:8020, Ident: (token for chen: HDFS_DELEGATION_TOKEN owner=chen@ZEBRA716.CN, renewer=yarn, realUser=, issueDate=1494559847322, maxDate=1495164647322, sequenceNumber=2, masterKeyId=2)
17/05/12 03:30:47 INFO input.FileInputFormat: Total input paths to process : 8
17/05/12 03:30:47 INFO mapreduce.JobSubmitter: number of splits:8
17/05/12 03:30:47 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1494559196909_0002
17/05/12 03:30:47 INFO mapreduce.JobSubmitter: Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.32.20:8020, Ident: (token for chen: HDFS_DELEGATION_TOKEN owner=chen@ZEBRA716.CN, renewer=yarn, realUser=, issueDate=1494559847322, maxDate=1495164647322, sequenceNumber=2, masterKeyId=2)
17/05/12 03:30:48 INFO impl.YarnClientImpl: Submitted application application_1494559196909_0002
17/05/12 03:30:48 INFO mapreduce.Job: The url to track the job: http://ip-172-31-32-20.us-west-2.compute.internal:8088/proxy/application_1494559196909_0002/
17/05/12 03:30:48 INFO mapreduce.Job: Running job: job_1494559196909_0002
17/05/12 03:30:58 INFO mapreduce.Job: Job job_1494559196909_0002 running in uber mode : false
17/05/12 03:30:58 INFO mapreduce.Job:  map 0% reduce 0%
17/05/12 03:31:04 INFO mapreduce.Job:  map 13% reduce 0%
17/05/12 03:31:09 INFO mapreduce.Job:  map 63% reduce 0%
17/05/12 03:31:12 INFO mapreduce.Job:  map 100% reduce 0%
17/05/12 03:31:18 INFO mapreduce.Job:  map 100% reduce 100%
17/05/12 03:31:19 INFO mapreduce.Job: Job job_1494559196909_0002 completed successfully
17/05/12 03:31:19 INFO mapreduce.Job: Counters: 49
        File System Counters
                FILE: Number of bytes read=84
                FILE: Number of bytes written=1124859
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=2376
                HDFS: Number of bytes written=215
                HDFS: Number of read operations=35
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=3
        Job Counters
                Launched map tasks=8
                Launched reduce tasks=1
                Data-local map tasks=8
                Total time spent by all maps in occupied slots (ms)=77449
                Total time spent by all reduces in occupied slots (ms)=4028
                Total time spent by all map tasks (ms)=77449
                Total time spent by all reduce tasks (ms)=4028
                Total vcore-seconds taken by all map tasks=77449
                Total vcore-seconds taken by all reduce tasks=4028
                Total megabyte-seconds taken by all map tasks=79307776
                Total megabyte-seconds taken by all reduce tasks=4124672
        Map-Reduce Framework
                Map input records=8
                Map output records=16
                Map output bytes=144
                Map output materialized bytes=271
                Input split bytes=1432
                Combine input records=0
                Combine output records=0
                Reduce input groups=2
                Reduce shuffle bytes=271
                Reduce input records=16
                Reduce output records=0
                Spilled Records=32
                Shuffled Maps =8
                Failed Shuffles=0
                Merged Map outputs=8
                GC time elapsed (ms)=338
                CPU time spent (ms)=7430
                Physical memory (bytes) snapshot=3769966592
                Virtual memory (bytes) snapshot=14121783296
                Total committed heap usage (bytes)=4399824896
        Shuffle Errors
                BAD_ID=0
                CONNECTION=0
                IO_ERROR=0
                WRONG_LENGTH=0
                WRONG_MAP=0
                WRONG_REDUCE=0
        File Input Format Counters
                Bytes Read=944
        File Output Format Counters
                Bytes Written=97
Job Finished in 32.792 seconds
Estimated value of Pi is 3.20000000000000000000

real    0m36.631s
user    0m6.040s
sys     0m0.726s
```  
