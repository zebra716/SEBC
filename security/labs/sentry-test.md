```
[root@ip-172-31-36-60 ~]# beeline
beeline> !connect jdbc:hive2://ip-172-31-36-60.us-west-2.compute.internal:10000/default;principal=hive/ip-172-31-36-60.us-west-2.compute.internal@HADOOP.COM
Connecting to jdbc:hive2://ip-172-31-36-60.us-west-2.compute.internal:10000/default;principal=hive/ip-172-31-36-60.us-west-2.compute.internal@HADOOP.COM
Connected to: Apache Hive (version 1.1.0-cdh5.11.0)
Driver: Hive JDBC (version 1.1.0-cdh5.11.0)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://ip-172-31-36-60.us-west-2.com> show tables;
INFO  : Compiling command(queryId=hive_20170511040000_6ba7ebe7-1ca9-4bf6-a893-51dde4284e65): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20170511040000_6ba7ebe7-1ca9-4bf6-a893-51dde4284e65); Time taken: 0.76 seconds
INFO  : Executing command(queryId=hive_20170511040000_6ba7ebe7-1ca9-4bf6-a893-51dde4284e65): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170511040000_6ba7ebe7-1ca9-4bf6-a893-51dde4284e65); Time taken: 0.291 seconds
INFO  : OK
+-----------+--+
| tab_name  |
+-----------+--+
+-----------+--+
No rows selected (2.449 seconds)

```
