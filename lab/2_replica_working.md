1. Download and install mysql/mysql-server/connector  
```
[root@ip-172-31-36-60 ~]# yum install mysql  
[root@ip-172-31-36-60 ~]# yum install mysql-server  
[root@ip-172-31-36-60 ~]# mkdir /usr/share/java  
[root@ip-172-31-36-60 ~]# cd /usr/share/java  
[root@ip-172-31-36-60 ~]# wget https://dev.mysql.com/get/Downloads/Connector-J/mysql-connector-java-5.1.42.tar.gz  
[root@ip-172-31-36-60 ~]# tar zxvf mysql-connector-java-5.1.42.tar.gz  
[root@ip-172-31-36-60 ~]# cp ./mysql-connector-java-5.1.42/mysql-connector-java-5.1.42-bin.jar /usr/share/java/oracle-connector-java.jar 
[root@ip-172-31-36-60 ~]# cp ./mysql-connector-java-5.1.42/mysql-connector-java-5.1.42-bin.jar /usr/share/java/mysql-connector-java.jar   
```

2. Change the password of root user to 123456  
```
[root@ip-172-31-36-60 ~]# /etc/init.d/mysql stop  
[root@ip-172-31-36-60 ~]# mysqld_safe --user=mysql --skip-grant-tables --skip-networking &  
[root@ip-172-31-36-60 ~]# mysql -u root mysql  
[root@ip-172-31-36-60 ~]# UPDATE user SET Password=PASSWORD('123456') where USER='root';  
[root@ip-172-31-36-60 ~]# FLUSH PRIVILEGES;  
[root@ip-172-31-36-60 ~]# quit;  
```

3. Grant all rights to all clients  
```
[root@ip-172-31-36-60 ~]# /etc/init.d/mysql restart  
[root@ip-172-31-36-60 ~]# mysql -uroot -p123456  
[root@ip-172-31-36-60 ~]# grant all privileges on *.* to 'root'@'%' identified by '123456' with grant option;  
[root@ip-172-31-36-60 ~]# flush privileges;  
```

4. Config Mysql Master/Slave with the following steps  
4.1. modify /etc/my.cnf to support replication   
```
> for master  
    [mysqld]  
    log-bin=mysql-bin  
    server-id=1  
      
  > for slave  
    [mysqld]  
    server-id=2  
```

4.2. Start the mysqld service  
```
[root@ip-172-31-36-60 ~]# service mysqld start  
   Initializing MySQL database:                               [  OK  ]  
   Installing validate password plugin:                       [  OK  ]  
   Starting mysqld:          
   Use /usr/bin/mysql_secure_installation to:  
   a. Set password protection for the server  
   b. Revoke permissions for anonymous users  
   c. Permit remote privileged login  
   d. Remove test databases  
   e. Refresh privileges in memory  
   f. Refreshes the mysqld service  
[root@ip-172-31-36-60 ~]# /usr/bin/mysql_secure_installation  
     
   Securing the MySQL server deployment.  
     
   Enter password for user root:   
     
   The existing password for the user account root has expired. Please set a new password.  
     
   New password:   
     
   Re-enter new password:   
   The 'validate_password' plugin is installed on the server.  
   The subsequent steps will run with the existing configuration  
   of the plugin.  
   Using existing password for root.  
     
   Estimated strength of the password: 100   
   Change the password for root ? ((Press y|Y for Yes, any other key for No) : y  
     
   New password:   
     
   Re-enter new password:   
     
   Estimated strength of the password: 100   
   Do you wish to continue with the password provided?(Press y|Y for Yes, any other key for No) : y  
   By default, a MySQL installation has an anonymous user,  
   allowing anyone to log into MySQL without having to have  
   a user account created for them. This is intended only for  
   testing, and to make the installation go a bit smoother.  
   You should remove them before moving into a production  
   environment.  
     
   Remove anonymous users? (Press y|Y for Yes, any other key for No) : y  
   Success.  
     
     
   Normally, root should only be allowed to connect from  
   'localhost'. This ensures that someone cannot guess at  
   the root password from the network.  
     
   Disallow root login remotely? (Press y|Y for Yes, any other key for No) : n  
     
    ... skipping.  
   By default, MySQL comes with a database named 'test' that  
   anyone can access. This is also intended only for testing,  
   and should be removed before moving into a production  
   environment.  
     
     
   Remove test database and access to it? (Press y|Y for Yes, any other key for No) : y  
    - Dropping test database...  
   Success.  
     
    - Removing privileges on test database...  
   Success.  
     
   Reloading the privilege tables will ensure that all changes  
   made so far will take effect immediately.  
     
   Reload privilege tables now? (Press y|Y for Yes, any other key for No) : y  
   Success.  
     
   All done!   
```

4.3.On the master MySQL node, grant replication privileges for my replica node  
```
mysql> GRANT REPLICATION SLAVE ON *.* TO 'repl'@'%' IDENTIFIED BY '123456';  
   Query OK, 0 rows affected (0.00 sec)  
     
   mysql> SET GLOBAL binlog_format = 'ROW';  
   Query OK, 0 rows affected (0.00 sec)  
     
   mysql> FLUSH TABLES WITH READ LOCK;  
   Query OK, 0 rows affected (0.00 sec)  
```

4.4. In a second terminal session, log into the MySQL master and show its status  
```
mysql> SHOW MASTER STATUS;  
   +------------------+----------+--------------+------------------+-------------------+  
   | File             | Position | Binlog_Do_DB | Binlog_Ignore_DB | Executed_Gtid_Set |  
   +------------------+----------+--------------+------------------+-------------------+  
   | mysql-bin.000001 |      529 |              |                  |                   |  
   +------------------+----------+--------------+------------------+-------------------+  
   1 row in set (0.00 sec)  
```

4.5. Login to the replica server and configure a connection to the master  
```
mysql> CHANGE MASTER TO MASTER_HOST='172.31.36.60', MASTER_USER='repl', MASTER_PASSWORD='123456', MASTER_LOG_FILE='mysql-bin.000001', MASTER_LOG_POS=529;  
   Query OK, 0 rows affected (0.01 sec)  
```

4.6. Initiate slave operations on the replica  
```
   mysql> START SLAVE;  
   Query OK, 0 rows affected (0.00 sec)  
     
   mysql> SHOW SLAVE STATUS \G  
   *************************** 1. row ***************************  
                  Slave_IO_State: Waiting for master to send event  
                     Master_Host: 172.31.36.60  
                     Master_User: repl  
                     Master_Port: 3306  
                   Connect_Retry: 60  
                 Master_Log_File: mysql-bin.000001  
             Read_Master_Log_Pos: 44365177  
                  Relay_Log_File: mysqld-relay-bin.000002  
                   Relay_Log_Pos: 44364899  
           Relay_Master_Log_File: mysql-bin.000001  
                Slave_IO_Running: Yes  
               Slave_SQL_Running: Yes  
                 Replicate_Do_DB:  
             Replicate_Ignore_DB:  
              Replicate_Do_Table:  
          Replicate_Ignore_Table:  
         Replicate_Wild_Do_Table:  
     Replicate_Wild_Ignore_Table:  
                      Last_Errno: 0  
                      Last_Error:  
                    Skip_Counter: 0  
             Exec_Master_Log_Pos: 44365177  
                 Relay_Log_Space: 44365055  
                 Until_Condition: None  
                  Until_Log_File:  
                   Until_Log_Pos: 0  
              Master_SSL_Allowed: No  
              Master_SSL_CA_File:  
              Master_SSL_CA_Path:  
                 Master_SSL_Cert:  
               Master_SSL_Cipher:  
                  Master_SSL_Key:  
           Seconds_Behind_Master: 0  
   Master_SSL_Verify_Server_Cert: No  
                   Last_IO_Errno: 0  
                   Last_IO_Error:  
                  Last_SQL_Errno: 0  
                  Last_SQL_Error:  
   1 row in set (0.00 sec)  
```
