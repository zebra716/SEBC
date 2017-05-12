List the command and output for ls /etc/yum.repos.d  
```
[root@ip-172-31-32-20 yum.repos.d]# ls /etc/yum.repos.d
CentOS-Base.repo       CentOS-Media.repo  cloudera-manager.repo
CentOS-Debuginfo.repo  CentOS-Vault.repo
```  

Connect Cloudera Manager Server to its database  
```
[root@ip-172-31-32-20 yum.repos.d]# /usr/share/cmf/schema/scm_prepare_database.sh -h 172.31.41.99 mysql scm root 123456
JAVA_HOME=/usr/java/jdk1.7.0_67-cloudera
Verifying that we can write to /etc/cloudera-scm-server
Creating SCM configuration file in /etc/cloudera-scm-server
Executing:  /usr/java/jdk1.7.0_67-cloudera/bin/java -cp /usr/share/java/mysql-connector-java.jar:/usr/share/java/oracle-connector-java.jar:/usr/share/cmf/schema/../lib/* com.cloudera.enterprise.dbutil.DbCommandExecutor /etc/cloudera-scm-server/db.properties com.cloudera.cmf.db.
[                          main] DbCommandExecutor              INFO  Successfully connected to database.
All done, your SCM database is configured correctly!

