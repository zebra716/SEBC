What is ubertask optimization?  
```
Uber is a optimization in hadoop2.0 that multi small tasks can be executed in one container.
We can use mapreduce.job.ubertask.enable setting to enable or disable, and define these seetings the mapreduce.job.ubertask.maxmaps, mapreduce.job.ubertask.maxreduces, and mapreduce.job.ubertask.maxbytes as samll.
```  

Where in CM is the Kerberos Security Realm value displayed?  
```
Menu -> Administration -> Settings -> CATEGORY -> Kerberos, and to find Kerberos Security Realm.
```  

Which CDH service(s) host a property for enabling Kerberos authentication?  
```
Have the below services:
YARN, HDFS, ZooKeeper, Hive, Oozie, Cloudera Management Service, Hue etc.
```  

How do you upgrade the CM agents?  
```
Menu -> Hosts -> All Hosts, we select all CM agents which all have been displayed and then click "Re-run Upgrade Wizard" button.
```  

Give the tsquery statement used to chart Hue's CPU utilization?  
```
SELECT cpu_system_rate + cpu_user_rate WHERE entityName = "hue-HUE_SERVER-3d5faea69feccab8df0dc231be3c8415" AND category = ROLE
```  

Name all the roles that make up the Hive service  
```
Hive Metastore Server, HiveServer2, WebHCat Server, Gateway
```  

What steps must be completed before integrating Cloudera Manager with Kerberos?  
```
Set up a working KDC. 
Cloudera Manager supports authentication with MIT KDC and Active Directory.
Configure the KDC to allow renewable tickets with non-zero ticket lifetimes. 
Active Directory allows renewable tickets with non-zero lifetimes by default. 
We can verify this by checking Domain Security Settings > Account Policies > Kerberos Policy in Active Directory.
If you are using Active Directory, make sure LDAP over TLS/SSL (LDAPS) is enabled for the Domain Controllers.
Install the OS-specific packages for your cluster.
Create an account for Cloudera Manager that has the permissions to create other accounts in the KDC.
```  
