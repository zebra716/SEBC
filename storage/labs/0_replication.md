1. Choose a partner in class  
Due to the lan is private lan in other partners, I can only use myself environment as other partner to verify.  
  
2. Name a source directory after your GitHub handle  
Change user to hdfs  
```
su - hdfs  
  
hadoop fs -mkdir /lab  
hadoop fs -mkdir /lab/zebra716  
```
  
3. Name a target directory after your partner's GitHub handle  
I will use zebra716_parnter to replace my partner's GitHub as target directory.  

```
hadoop fs -mkdir /lab/zebra716_partner  
```
  
4. Use teragen to create a 500 MB file  
```
[hdfs@ip-172-31-36-60 ~]$ hadoop jar /opt/cloudera/parcels/CDH/jars/hadoop-examples.jar teragen -Dmapred.map.tasks=4 5242880 /lab/zebra716/teragen500MB  
17/05/09 10:21:24 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-36-60.us-west-2.compute.internal/172.31.36.60:8032  
17/05/09 10:21:25 INFO terasort.TeraGen: Generating 5242880 using 4  
17/05/09 10:21:25 INFO mapreduce.JobSubmitter: number of splits:4  
17/05/09 10:21:25 INFO Configuration.deprecation: mapred.map.tasks is deprecated. Instead, use mapreduce.job.maps  
17/05/09 10:21:25 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1494308857993_0005  
17/05/09 10:21:25 INFO impl.YarnClientImpl: Submitted application application_1494308857993_0005  
17/05/09 10:21:25 INFO mapreduce.Job: The url to track the job: http://ip-172-31-36-60.us-west-2.compute.internal:8088/proxy/application_1494308857993_0005/  
17/05/09 10:21:25 INFO mapreduce.Job: Running job: job_1494308857993_0005  
17/05/09 10:21:32 INFO mapreduce.Job: Job job_1494308857993_0005 running in uber mode : false  
17/05/09 10:21:32 INFO mapreduce.Job:  map 0% reduce 0%  
17/05/09 10:21:43 INFO mapreduce.Job:  map 75% reduce 0%  
17/05/09 10:21:44 INFO mapreduce.Job:  map 100% reduce 0%  
17/05/09 10:21:45 INFO mapreduce.Job: Job job_1494308857993_0005 completed successfully  
17/05/09 10:21:46 INFO mapreduce.Job: Counters: 33  
        File System Counters  
                FILE: Number of bytes read=0  
                FILE: Number of bytes written=510456  
                FILE: Number of read operations=0  
                FILE: Number of large read operations=0  
                FILE: Number of write operations=0  
                HDFS: Number of bytes read=337  
                HDFS: Number of bytes written=524288000  
                HDFS: Number of read operations=16  
                HDFS: Number of large read operations=0  
                HDFS: Number of write operations=8  
        Job Counters  
                Launched map tasks=4  
                Other local map tasks=4  
                Total time spent by all maps in occupied slots (ms)=38599  
                Total time spent by all reduces in occupied slots (ms)=0  
                Total time spent by all map tasks (ms)=38599  
                Total vcore-milliseconds taken by all map tasks=38599  
                Total megabyte-milliseconds taken by all map tasks=39525376  
        Map-Reduce Framework  
                Map input records=5242880  
                Map output records=5242880  
                Input split bytes=337  
                Spilled Records=0  
                Failed Shuffles=0  
                Merged Map outputs=0  
                GC time elapsed (ms)=580  
                CPU time spent (ms)=22560  
                Physical memory (bytes) snapshot=1451409408  
                Virtual memory (bytes) snapshot=6276456448  
                Total committed heap usage (bytes)=1693450240  
                Peak Map Physical memory (bytes)=370475008  
                Peak Map Virtual memory (bytes)=1575542784  
        org.apache.hadoop.examples.terasort.TeraGen$Counters  
                CHECKSUM=11257830824958050  
        File Input Format Counters  
                Bytes Read=0  
        File Output Format Counters  
                Bytes Written=524288000  
```
  
5. Copy your partner's file to your target directory  
5.1. Let one partner use distCp on the command line  
I will use zebra716_parnter as my partner.  
```
[hdfs@ip-172-31-36-60 ~]$ hadoop distcp hdfs://172.31.36.60:8020/lab/zebra716/teragen500MB hdfs://172.31.36.60:8020/lab/zebra716_parnter/teragen500MB_distcp  
17/05/09 10:22:46 INFO tools.DistCp: Input Options: DistCpOptions{atomicCommit=false, syncFolder=false, deleteMissing=false, ignoreFailures=false, overwrite=false, append=false, useDiff=false, useRdiff=false, fromSnapshot=null, toSnapshot=null, skipCRC=false, blocking=true, numListstatusThreads=0, maxMaps=20, mapBandwidth=100, sslConfigurationFile='null', copyStrategy='uniformsize', preserveStatus=[], preserveRawXattrs=false, atomicWorkPath=null, logPath=null, sourceFileListing=null, sourcePaths=[hdfs://172.31.36.60:8020/lab/zebra716/teragen500MB], targetPath=hdfs://172.31.36.60:8020/lab/zebra716_parnter/teragen500MB_distcp, targetPathExists=false, filtersFile='null'}  
17/05/09 10:22:46 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-36-60.us-west-2.compute.internal/172.31.36.60:8032  
17/05/09 10:22:47 INFO tools.SimpleCopyListing: Paths (files+dirs) cnt = 6; dirCnt = 1  
17/05/09 10:22:47 INFO tools.SimpleCopyListing: Build file listing completed.  
17/05/09 10:22:47 INFO Configuration.deprecation: io.sort.mb is deprecated. Instead, use mapreduce.task.io.sort.mb  
17/05/09 10:22:47 INFO Configuration.deprecation: io.sort.factor is deprecated. Instead, use mapreduce.task.io.sort.factor  
17/05/09 10:22:47 INFO tools.DistCp: Number of paths in the copy list: 6  
17/05/09 10:22:47 INFO tools.DistCp: Number of paths in the copy list: 6  
17/05/09 10:22:47 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-36-60.us-west-2.compute.internal/172.31.36.60:8032  
17/05/09 10:22:47 INFO mapreduce.JobSubmitter: number of splits:5  
17/05/09 10:22:47 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1494308857993_0006  
17/05/09 10:22:47 INFO impl.YarnClientImpl: Submitted application application_1494308857993_0006  
17/05/09 10:22:48 INFO mapreduce.Job: The url to track the job: http://ip-172-31-36-60.us-west-2.compute.internal:8088/proxy/application_1494308857993_0006/  
17/05/09 10:22:48 INFO tools.DistCp: DistCp job-id: job_1494308857993_0006  
17/05/09 10:22:48 INFO mapreduce.Job: Running job: job_1494308857993_0006  
17/05/09 10:22:55 INFO mapreduce.Job: Job job_1494308857993_0006 running in uber mode : false  
17/05/09 10:22:55 INFO mapreduce.Job:  map 0% reduce 0%  
17/05/09 10:23:03 INFO mapreduce.Job:  map 20% reduce 0%  
17/05/09 10:23:05 INFO mapreduce.Job:  map 40% reduce 0%  
17/05/09 10:23:09 INFO mapreduce.Job:  map 60% reduce 0%  
17/05/09 10:23:10 INFO mapreduce.Job:  map 100% reduce 0%  
17/05/09 10:23:10 INFO mapreduce.Job: Job job_1494308857993_0006 completed successfully  
17/05/09 10:23:10 INFO mapreduce.Job: Counters: 35  
        File System Counters  
                FILE: Number of bytes read=0  
                FILE: Number of bytes written=653130  
                FILE: Number of read operations=0  
                FILE: Number of large read operations=0  
                FILE: Number of write operations=0  
                HDFS: Number of bytes read=524290745  
                HDFS: Number of bytes written=524288000  
                HDFS: Number of read operations=89  
                HDFS: Number of large read operations=0  
                HDFS: Number of write operations=21  
        Job Counters  
                Launched map tasks=5  
                Other local map tasks=5  
                Total time spent by all maps in occupied slots (ms)=49511  
                Total time spent by all reduces in occupied slots (ms)=0  
                Total time spent by all map tasks (ms)=49511  
                Total vcore-milliseconds taken by all map tasks=49511  
                Total megabyte-milliseconds taken by all map tasks=50699264  
        Map-Reduce Framework  
                Map input records=6  
                Map output records=0  
                Input split bytes=575  
                Spilled Records=0  
                Failed Shuffles=0  
                Merged Map outputs=0  
                GC time elapsed (ms)=561  
                CPU time spent (ms)=20620  
                Physical memory (bytes) snapshot=1204387840  
                Virtual memory (bytes) snapshot=7882862592  
                Total committed heap usage (bytes)=1678770176  
                Peak Map Physical memory (bytes)=267485184  
                Peak Map Virtual memory (bytes)=1583398912  
        File Input Format Counters  
                Bytes Read=2170  
        File Output Format Counters  
                Bytes Written=0  
        DistCp Counters  
                Bytes Copied=524288000  
                Bytes Expected=524288000  
                Files Copied=6  
```
  
5.2. Let the other use BDR  
  
6. Browse the results  
6.1 Use hdfs fsck <path> -files -blocks on your source and target directories  
```
[hdfs@ip-172-31-36-60 ~]$ hadoop fsck /lab -files -blocks  
DEPRECATED: Use of this script to execute hdfs command is deprecated.  
Instead use the hdfs command for it.  
  
Connecting to namenode via http://ip-172-31-36-60.us-west-2.compute.internal:50070  
FSCK started by hdfs (auth:SIMPLE) from /172.31.36.60 for path /lab at Tue May 09 10:23:47 UTC 2017  
/lab <dir>  
/lab/zebra716 <dir>  
/lab/zebra716/teragen500MB <dir>  
/lab/zebra716/teragen500MB/_SUCCESS 0 bytes, 0 block(s):  OK  
  
/lab/zebra716/teragen500MB/part-m-00000 131072000 bytes, 1 block(s):  Under replicated BP-14498119-172.31.36.60-1494308797466:blk_1073742837_2013. Target Replicas is 3 but found 2 live replica(s), 0 decommissioned replica(s), 0 decommissioning replica(s).  
0. BP-14498119-172.31.36.60-1494308797466:blk_1073742837_2013 len=131072000 Live_repl=2  
  
/lab/zebra716/teragen500MB/part-m-00001 131072000 bytes, 1 block(s):  Under replicated BP-14498119-172.31.36.60-1494308797466:blk_1073742836_2012. Target Replicas is 3 but found 2 live replica(s), 0 decommissioned replica(s), 0 decommissioning replica(s).  
0. BP-14498119-172.31.36.60-1494308797466:blk_1073742836_2012 len=131072000 Live_repl=2  
  
/lab/zebra716/teragen500MB/part-m-00002 131072000 bytes, 1 block(s):  Under replicated BP-14498119-172.31.36.60-1494308797466:blk_1073742835_2011. Target Replicas is 3 but found 2 live replica(s), 0 decommissioned replica(s), 0 decommissioning replica(s).  
0. BP-14498119-172.31.36.60-1494308797466:blk_1073742835_2011 len=131072000 Live_repl=2  
  
/lab/zebra716/teragen500MB/part-m-00003 131072000 bytes, 1 block(s):  Under replicated BP-14498119-172.31.36.60-1494308797466:blk_1073742838_2014. Target Replicas is 3 but found 2 live replica(s), 0 decommissioned replica(s), 0 decommissioning replica(s).  
0. BP-14498119-172.31.36.60-1494308797466:blk_1073742838_2014 len=131072000 Live_repl=2  
  
/lab/zebra716_parnter <dir>  
/lab/zebra716_parnter/teragen500MB_distcp <dir>  
/lab/zebra716_parnter/teragen500MB_distcp/_SUCCESS 0 bytes, 0 block(s):  OK  
  
/lab/zebra716_parnter/teragen500MB_distcp/part-m-00000 131072000 bytes, 1 block(s):  Under replicated BP-14498119-172.31.36.60-1494308797466:blk_1073742855_2031. Target Replicas is 3 but found 2 live replica(s), 0 decommissioned replica(s), 0 decommissioning replica(s).  
0. BP-14498119-172.31.36.60-1494308797466:blk_1073742855_2031 len=131072000 Live_repl=2  
  
/lab/zebra716_parnter/teragen500MB_distcp/part-m-00001 131072000 bytes, 1 block(s):  Under replicated BP-14498119-172.31.36.60-1494308797466:blk_1073742859_2035. Target Replicas is 3 but found 2 live replica(s), 0 decommissioned replica(s), 0 decommissioning replica(s).  
0. BP-14498119-172.31.36.60-1494308797466:blk_1073742859_2035 len=131072000 Live_repl=2  
  
/lab/zebra716_parnter/teragen500MB_distcp/part-m-00002 131072000 bytes, 1 block(s):  Under replicated BP-14498119-172.31.36.60-1494308797466:blk_1073742858_2034. Target Replicas is 3 but found 2 live replica(s), 0 decommissioned replica(s), 0 decommissioning replica(s).  
0. BP-14498119-172.31.36.60-1494308797466:blk_1073742858_2034 len=131072000 Live_repl=2  
  
/lab/zebra716_parnter/teragen500MB_distcp/part-m-00003 131072000 bytes, 1 block(s):  Under replicated BP-14498119-172.31.36.60-1494308797466:blk_1073742857_2033. Target Replicas is 3 but found 2 live replica(s), 0 decommissioned replica(s), 0 decommissioning replica(s).  
0. BP-14498119-172.31.36.60-1494308797466:blk_1073742857_2033 len=131072000 Live_repl=2  
  
/lab/zebra716_partner <dir>  
Status: HEALTHY  
 Total size:    1048576000 B  
 Total dirs:    6  
 Total files:   10  
 Total symlinks:                0  
 Total blocks (validated):      8 (avg. block size 131072000 B)  
 Minimally replicated blocks:   8 (100.0 %)  
 Over-replicated blocks:        0 (0.0 %)  
 Under-replicated blocks:       8 (100.0 %)  
 Mis-replicated blocks:         0 (0.0 %)  
 Default replication factor:    3  
 Average block replication:     2.0  
 Corrupt blocks:                0  
 Missing replicas:              8 (33.333332 %)  
 Number of data-nodes:          2  
 Number of racks:               1  
FSCK ended at Tue May 09 10:23:47 UTC 2017 in 3 milliseconds  
  
  
The filesystem under path '/lab' is HEALTHY  
```
  
6.2 Copy the work for this lab into storage/labs/0_replication.md  
