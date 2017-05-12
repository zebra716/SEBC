The full teragen command and job output  
```
[zhou@ip-172-31-32-20 ~]$ time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar teragen -Dmapreduce.map.memory.mb=1024 -Dmapred.map.tasks=6 -Ddfs.block.size=67108864 65536000 /user/zhou/tgen
17/05/12 02:40:34 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-32-20.us-west-2.compute.internal/172.31.32.20:8032
17/05/12 02:40:34 INFO terasort.TeraSort: Generating 65536000 using 6
17/05/12 02:40:34 INFO mapreduce.JobSubmitter: number of splits:6
17/05/12 02:40:34 INFO Configuration.deprecation: mapred.map.tasks is deprecated. Instead, use mapreduce.job.maps
17/05/12 02:40:34 INFO Configuration.deprecation: dfs.block.size is deprecated.Instead, use dfs.blocksize
17/05/12 02:40:35 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1494555889500_0001
17/05/12 02:40:35 INFO impl.YarnClientImpl: Submitted application application_1494555889500_0001
17/05/12 02:40:35 INFO mapreduce.Job: The url to track the job: http://ip-172-31-32-20.us-west-2.compute.internal:8088/proxy/application_1494555889500_0001/
17/05/12 02:40:35 INFO mapreduce.Job: Running job: job_1494555889500_0001
17/05/12 02:40:43 INFO mapreduce.Job: Job job_1494555889500_0001 running in uber mode : false
17/05/12 02:40:43 INFO mapreduce.Job:  map 0% reduce 0%
17/05/12 02:40:55 INFO mapreduce.Job:  map 5% reduce 0%
17/05/12 02:40:56 INFO mapreduce.Job:  map 9% reduce 0%
17/05/12 02:40:57 INFO mapreduce.Job:  map 15% reduce 0%
17/05/12 02:40:58 INFO mapreduce.Job:  map 19% reduce 0%
17/05/12 02:40:59 INFO mapreduce.Job:  map 20% reduce 0%
17/05/12 02:41:00 INFO mapreduce.Job:  map 26% reduce 0%
17/05/12 02:41:01 INFO mapreduce.Job:  map 29% reduce 0%
17/05/12 02:41:02 INFO mapreduce.Job:  map 30% reduce 0%
17/05/12 02:41:03 INFO mapreduce.Job:  map 32% reduce 0%
17/05/12 02:41:04 INFO mapreduce.Job:  map 33% reduce 0%
17/05/12 02:41:06 INFO mapreduce.Job:  map 35% reduce 0%
17/05/12 02:41:07 INFO mapreduce.Job:  map 37% reduce 0%
17/05/12 02:41:09 INFO mapreduce.Job:  map 40% reduce 0%
17/05/12 02:41:11 INFO mapreduce.Job:  map 41% reduce 0%
17/05/12 02:41:12 INFO mapreduce.Job:  map 42% reduce 0%
17/05/12 02:41:13 INFO mapreduce.Job:  map 44% reduce 0%
17/05/12 02:41:14 INFO mapreduce.Job:  map 45% reduce 0%
17/05/12 02:41:15 INFO mapreduce.Job:  map 46% reduce 0%
17/05/12 02:41:16 INFO mapreduce.Job:  map 49% reduce 0%
17/05/12 02:41:17 INFO mapreduce.Job:  map 50% reduce 0%
17/05/12 02:41:19 INFO mapreduce.Job:  map 52% reduce 0%
17/05/12 02:41:20 INFO mapreduce.Job:  map 54% reduce 0%
17/05/12 02:41:22 INFO mapreduce.Job:  map 56% reduce 0%
17/05/12 02:41:23 INFO mapreduce.Job:  map 57% reduce 0%
17/05/12 02:41:24 INFO mapreduce.Job:  map 58% reduce 0%
17/05/12 02:41:25 INFO mapreduce.Job:  map 60% reduce 0%
17/05/12 02:41:26 INFO mapreduce.Job:  map 62% reduce 0%
17/05/12 02:41:27 INFO mapreduce.Job:  map 64% reduce 0%
17/05/12 02:41:28 INFO mapreduce.Job:  map 66% reduce 0%
17/05/12 02:41:29 INFO mapreduce.Job:  map 68% reduce 0%
17/05/12 02:41:30 INFO mapreduce.Job:  map 69% reduce 0%
17/05/12 02:41:31 INFO mapreduce.Job:  map 70% reduce 0%
17/05/12 02:41:32 INFO mapreduce.Job:  map 72% reduce 0%
17/05/12 02:41:33 INFO mapreduce.Job:  map 73% reduce 0%
17/05/12 02:41:34 INFO mapreduce.Job:  map 75% reduce 0%
17/05/12 02:41:35 INFO mapreduce.Job:  map 76% reduce 0%
17/05/12 02:41:36 INFO mapreduce.Job:  map 77% reduce 0%
17/05/12 02:41:37 INFO mapreduce.Job:  map 79% reduce 0%
17/05/12 02:41:38 INFO mapreduce.Job:  map 81% reduce 0%
17/05/12 02:41:39 INFO mapreduce.Job:  map 82% reduce 0%
17/05/12 02:41:40 INFO mapreduce.Job:  map 85% reduce 0%
17/05/12 02:41:41 INFO mapreduce.Job:  map 86% reduce 0%
17/05/12 02:41:43 INFO mapreduce.Job:  map 89% reduce 0%
17/05/12 02:41:46 INFO mapreduce.Job:  map 92% reduce 0%
17/05/12 02:41:47 INFO mapreduce.Job:  map 93% reduce 0%
17/05/12 02:41:49 INFO mapreduce.Job:  map 95% reduce 0%
17/05/12 02:41:50 INFO mapreduce.Job:  map 96% reduce 0%
17/05/12 02:41:52 INFO mapreduce.Job:  map 98% reduce 0%
17/05/12 02:41:53 INFO mapreduce.Job:  map 99% reduce 0%
17/05/12 02:41:54 INFO mapreduce.Job:  map 100% reduce 0%
17/05/12 02:41:54 INFO mapreduce.Job: Job job_1494555889500_0001 completed successfully
17/05/12 02:41:54 INFO mapreduce.Job: Counters: 31
        File System Counters
                FILE: Number of bytes read=0
                FILE: Number of bytes written=741066
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=511
                HDFS: Number of bytes written=6553600000
                HDFS: Number of read operations=24
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=12
        Job Counters
                Launched map tasks=6
                Other local map tasks=6
                Total time spent by all maps in occupied slots (ms)=375537
                Total time spent by all reduces in occupied slots (ms)=0
                Total time spent by all map tasks (ms)=375537
                Total vcore-seconds taken by all map tasks=375537
                Total megabyte-seconds taken by all map tasks=384549888
        Map-Reduce Framework
                Map input records=65536000
                Map output records=65536000
                Input split bytes=511
                Spilled Records=0
                Failed Shuffles=0
                Merged Map outputs=0
                GC time elapsed (ms)=1223
                CPU time spent (ms)=122060
                Physical memory (bytes) snapshot=1979850752
                Virtual memory (bytes) snapshot=9361956864
                Total committed heap usage (bytes)=1967652864
        org.apache.hadoop.examples.terasort.TeraGen$Counters
                CHECKSUM=140750829423462787
        File Input Format Counters
                Bytes Read=0
        File Output Format Counters
                Bytes Written=6553600000
```  

The result of the time command  
```
real    1m23.911s
user    0m6.467s
sys     0m0.762s
```  

The command and output of hdfs dfs -ls /user/zhou/tgen  
```
[zhou@ip-172-31-32-20 ~]$ hdfs dfs -ls /user/zhou/tgen
Found 7 items
-rw-r--r--   3 zhou zhou          0 2017-05-12 02:41 /user/zhou/tgen/_SUCCESS
-rw-r--r--   3 zhou zhou 1092266700 2017-05-12 02:41 /user/zhou/tgen/part-m-00000
-rw-r--r--   3 zhou zhou 1092266700 2017-05-12 02:41 /user/zhou/tgen/part-m-00001
-rw-r--r--   3 zhou zhou 1092266600 2017-05-12 02:41 /user/zhou/tgen/part-m-00002
-rw-r--r--   3 zhou zhou 1092266700 2017-05-12 02:41 /user/zhou/tgen/part-m-00003
-rw-r--r--   3 zhou zhou 1092266700 2017-05-12 02:41 /user/zhou/tgen/part-m-00004
-rw-r--r--   3 zhou zhou 1092266600 2017-05-12 02:41 /user/zhou/tgen/part-m-00005
```   
