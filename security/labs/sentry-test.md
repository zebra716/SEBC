Verify user privileges  
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

Create a Sentry role with full authorization  
In beeline:  
```
0: jdbc:hive2://ip-172-31-36-60.us-west-2.com> CREATE ROLE sentry_admin;
INFO  : Compiling command(queryId=hive_20170511040404_cc9b6239-fa28-47b9-b9fb-796764ead911): CREATE ROLE sentry_admin
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20170511040404_cc9b6239-fa28-47b9-b9fb-796764ead911); Time taken: 0.076 seconds
INFO  : Executing command(queryId=hive_20170511040404_cc9b6239-fa28-47b9-b9fb-796764ead911): CREATE ROLE sentry_admin
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170511040404_cc9b6239-fa28-47b9-b9fb-796764ead911); Time taken: 0.725 seconds
INFO  : OK
No rows affected (0.82 seconds)

0: jdbc:hive2://ip-172-31-36-60.us-west-2.com> GRANT ALL ON SERVER server1 to ROLE sentry_admin;
INFO  : Compiling command(queryId=hive_20170511040404_0e155491-f0bf-4f5c-9dea-e483a1c650b5): GRANT ALL ON SERVER server1 to ROLE sentry_admin
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20170511040404_0e155491-f0bf-4f5c-9dea-e483a1c650b5); Time taken: 0.1 seconds
INFO  : Executing command(queryId=hive_20170511040404_0e155491-f0bf-4f5c-9dea-e483a1c650b5): GRANT ALL ON SERVER server1 to ROLE sentry_admin
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170511040404_0e155491-f0bf-4f5c-9dea-e483a1c650b5); Time taken: 0.104 seconds
INFO  : OK
No rows affected (0.22 seconds)

0: jdbc:hive2://ip-172-31-36-60.us-west-2.com> GRANT ROLE sentry_admin to GROUP zebra716;
INFO  : Compiling command(queryId=hive_20170511040606_49da7186-788a-477a-bb53-c683f0cbb35c): GRANT ROLE sentry_admin to GROUP zebra716
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20170511040606_49da7186-788a-477a-bb53-c683f0cbb35c); Time taken: 0.08 seconds
INFO  : Executing command(queryId=hive_20170511040606_49da7186-788a-477a-bb53-c683f0cbb35c): GRANT ROLE sentry_admin to GROUP zebra716
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170511040606_49da7186-788a-477a-bb53-c683f0cbb35c); Time taken: 0.089 seconds
INFO  : OK
No rows affected (0.185 seconds)

0: jdbc:hive2://ip-172-31-36-60.us-west-2.com> SHOW TABLES;
INFO  : Compiling command(queryId=hive_20170511040606_bfec1de0-b9d5-4469-97fd-42a8e9c3ab9a): SHOW TABLES
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20170511040606_bfec1de0-b9d5-4469-97fd-42a8e9c3ab9a); Time taken: 0.064 seconds
INFO  : Executing command(queryId=hive_20170511040606_bfec1de0-b9d5-4469-97fd-42a8e9c3ab9a): SHOW TABLES
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170511040606_bfec1de0-b9d5-4469-97fd-42a8e9c3ab9a); Time taken: 0.155 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| customers  |
| sample_07  |
| sample_08  |
| web_logs   |
+------------+--+
4 rows selected (0.289 seconds)
```  

Create additional test users  
Add new users to all cluster nodes  
```
[root@ip-172-31-36-60 ~]# groupadd selector
[root@ip-172-31-36-60 ~]# groupadd inserters
[root@ip-172-31-36-60 ~]# useradd -u 1100 -g selector george
[root@ip-172-31-36-60 ~]# useradd -u 1200 -g inserters ferdinand
[root@ip-172-31-36-60 ~]# kadmin.local
Authenticating as principal zebra716/admin@HADOOP.COM with password.
kadmin.local:  add_principal george
WARNING: no policy specified for george@HADOOP.COM; defaulting to no policy
Enter password for principal "george@HADOOP.COM":
Re-enter password for principal "george@HADOOP.COM":
Principal "george@HADOOP.COM" created.
kadmin.local:  add_principal ferdinand
WARNING: no policy specified for ferdinand@HADOOP.COM; defaulting to no policy
Enter password for principal "ferdinand@HADOOP.COM":
Re-enter password for principal "ferdinand@HADOOP.COM":
Principal "ferdinand@HADOOP.COM" created.
```  

Create test roles  
Login to beeline as your admin user  
```
0: jdbc:hive2://ip-172-31-36-60.us-west-2.com> CREATE ROLE reads;
INFO  : Compiling command(queryId=hive_20170511041313_e4d08460-3b87-477f-b0e9-98024b5515ee): CREATE ROLE reads
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20170511041313_e4d08460-3b87-477f-b0e9-98024b5515ee); Time taken: 0.071 seconds
INFO  : Executing command(queryId=hive_20170511041313_e4d08460-3b87-477f-b0e9-98024b5515ee): CREATE ROLE reads
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170511041313_e4d08460-3b87-477f-b0e9-98024b5515ee); Time taken: 0.056 seconds
INFO  : OK
No rows affected (0.143 seconds)
0: jdbc:hive2://ip-172-31-36-60.us-west-2.com> CREATE ROLE writes;
INFO  : Compiling command(queryId=hive_20170511041313_292d2aad-f8bd-4fd4-8df1-c9c67be3ffc6): CREATE ROLE writes
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20170511041313_292d2aad-f8bd-4fd4-8df1-c9c67be3ffc6); Time taken: 0.062 seconds
INFO  : Executing command(queryId=hive_20170511041313_292d2aad-f8bd-4fd4-8df1-c9c67be3ffc6): CREATE ROLE writes
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170511041313_292d2aad-f8bd-4fd4-8df1-c9c67be3ffc6); Time taken: 0.031 seconds
INFO  : OK
No rows affected (0.109 seconds)
```  

Grant read privilege for all tables to reads  
```
0: jdbc:hive2://ip-172-31-36-60.us-west-2.com> GRANT SELECT ON DATABASE default to ROLE reads;
INFO  : Compiling command(queryId=hive_20170511041515_26ca6ed7-974b-457c-965a-02ac19e305d7): GRANT SELECT ON DATABASE default to ROLE reads
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20170511041515_26ca6ed7-974b-457c-965a-02ac19e305d7); Time taken: 0.067 seconds
INFO  : Executing command(queryId=hive_20170511041515_26ca6ed7-974b-457c-965a-02ac19e305d7): GRANT SELECT ON DATABASE default to ROLE reads
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170511041515_26ca6ed7-974b-457c-965a-02ac19e305d7); Time taken: 0.039 seconds
INFO  : OK
No rows affected (0.119 seconds)
0: jdbc:hive2://ip-172-31-36-60.us-west-2.com> GRANT ROLE reads to GROUP selector;
INFO  : Compiling command(queryId=hive_20170511041515_b4e53813-4cc2-4883-b1bb-c857a6583298): GRANT ROLE reads to GROUP selector
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20170511041515_b4e53813-4cc2-4883-b1bb-c857a6583298); Time taken: 0.076 seconds
INFO  : Executing command(queryId=hive_20170511041515_b4e53813-4cc2-4883-b1bb-c857a6583298): GRANT ROLE reads to GROUP selector
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170511041515_b4e53813-4cc2-4883-b1bb-c857a6583298); Time taken: 0.036 seconds
INFO  : OK
No rows affected (0.131 seconds)
```  

Grant read privilege for default.sample07 only to 'writes':  
```
0: jdbc:hive2://ip-172-31-36-60.us-west-2.com> GRANT SELECT ON default.sample_07 to ROLE writes;
INFO  : Compiling command(queryId=hive_20170511041818_63b85c8b-aa49-4f88-a977-742b745b980b): GRANT SELECT ON default.sample_07 to ROLE writes
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20170511041818_63b85c8b-aa49-4f88-a977-742b745b980b); Time taken: 0.062 seconds
INFO  : Executing command(queryId=hive_20170511041818_63b85c8b-aa49-4f88-a977-742b745b980b): GRANT SELECT ON default.sample_07 to ROLE writes
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170511041818_63b85c8b-aa49-4f88-a977-742b745b980b); Time taken: 0.036 seconds
INFO  : OK
No rows affected (0.114 seconds)
0: jdbc:hive2://ip-172-31-36-60.us-west-2.com> GRANT ROLE writes to GROUP inserters;
INFO  : Compiling command(queryId=hive_20170511041818_d8c7c315-1ad0-4810-aaf8-63c30e87a6df): GRANT ROLE writes to GROUP inserters
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20170511041818_d8c7c315-1ad0-4810-aaf8-63c30e87a6df); Time taken: 0.067 seconds
INFO  : Executing command(queryId=hive_20170511041818_d8c7c315-1ad0-4810-aaf8-63c30e87a6df): GRANT ROLE writes to GROUP inserters
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170511041818_d8c7c315-1ad0-4810-aaf8-63c30e87a6df); Time taken: 0.041 seconds
INFO  : OK
No rows affected (0.125 seconds)
```  

kinit as george, then login to beeline  
kinit as george, login to beeline, and use SHOW TABLES;

george should be able to see all tables
```
[root@ip-172-31-36-60 ~]# kinit george
Password for george@HADOOP.COM:

[root@ip-172-31-36-60 ~]# beeline
beeline> !connect jdbc:hive2://ip-172-31-36-60.us-west-2.compute.internal:10000/default;principal=hive/ip-172-31-36-60.us-west-2.compute.internal@HADOOP.COM
scan complete in 4ms
Connecting to jdbc:hive2://ip-172-31-36-60.us-west-2.compute.internal:10000/default;principal=hive/ip-172-31-36-60.us-west-2.compute.internal@HADOOP.COM
Connected to: Apache Hive (version 1.1.0-cdh5.11.0)
Driver: Hive JDBC (version 1.1.0-cdh5.11.0)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://ip-172-31-36-60.us-west-2.com> SHOW TABLES;
INFO  : Compiling command(queryId=hive_20170511042222_575647f8-de68-4634-b197-861a172a8827): SHOW TABLES
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20170511042222_575647f8-de68-4634-b197-861a172a8827); Time taken: 0.074 seconds
INFO  : Executing command(queryId=hive_20170511042222_575647f8-de68-4634-b197-861a172a8827): SHOW TABLES
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170511042222_575647f8-de68-4634-b197-861a172a8827); Time taken: 0.142 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| customers  |
| sample_07  |
| sample_08  |
| web_logs   |
+------------+--+
4 rows selected (0.328 seconds)

```  

Repeat the process as ferdinand
ferdinand should see sample_07
```
[root@ip-172-31-36-60 ~]# beeline
Beeline version 1.1.0-cdh5.11.0 by Apache Hive
beeline> !connect jdbc:hive2://ip-172-31-36-60.us-west-2.compute.internal:10000/default;principal=hive/ip-172-31-36-60.us-west-2.compute.internal@HADOOP.COM
scan complete in 2ms
Connecting to jdbc:hive2://ip-172-31-36-60.us-west-2.compute.internal:10000/default;principal=hive/ip-172-31-36-60.us-west-2.compute.internal@HADOOP.COM
Connected to: Apache Hive (version 1.1.0-cdh5.11.0)
Driver: Hive JDBC (version 1.1.0-cdh5.11.0)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://ip-172-31-36-60.us-west-2.com> SHOW TABLES;
INFO  : Compiling command(queryId=hive_20170511042424_a794075b-3be4-423f-881f-9f080f7e2875): SHOW TABLES
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20170511042424_a794075b-3be4-423f-881f-9f080f7e2875); Time taken: 0.085 seconds
INFO  : Executing command(queryId=hive_20170511042424_a794075b-3be4-423f-881f-9f080f7e2875): SHOW TABLES
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170511042424_a794075b-3be4-423f-881f-9f080f7e2875); Time taken: 0.142 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| sample_07  |
+------------+--+
1 row selected (0.338 seconds)

```  

