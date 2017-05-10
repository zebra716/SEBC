Use the API on the command line to:  
  
1. Report the latest available version of the API  
```
[root@ip-172-31-36-60 ~]# curl -X GET -u zebra716:cloudera 'http://34.210.70.178:7180/api/version'
V16
```  

2. Report the CM version  
```
[root@ip-172-31-36-60 ~]# curl -X GET -u zebra716:cloudera 'http://34.210.70.:7180/api/v16/cm/version'
{
  "version" : "5.11.0",
  "buildUser" : "jenkins",
  "buildTimestamp" : "20170412-1249",
  "gitHash" : "70cb1442626406432a6e7af5bdf206a384ca3f98",
  "snapshot" : false
}
```  

3. List all CM users  
```
[root@ip-172-31-36-60 ~]# curl -X GET -u zebra716:cloudera 'http://34.210.70.178:7180/api/v16/users'
{
  "items" : [ {
    "name" : "admin",
    "roles" : [ "ROLE_LIMITED" ]
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ]
  }, {
    "name" : "zebra716",
    "roles" : [ "ROLE_ADMIN" ]
  } ]
}
```  

4. Report the database server in use by CM  
```

```  

Add these API calls and their output to enterprise/labs/4_API_upgrade_calls.md
Label the Issue review
