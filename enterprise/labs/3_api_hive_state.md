1. Stop hive service  
```
[root@ip-172-31-36-60 ~]# curl -X POST -u zebra716:cloudera 'http://34.210.70.178:7180/api/v16/clusters/zebra716/services/hive/commands/stop'
{
  "id" : 387,
  "name" : "Stop",
  "startTime" : "2017-05-10T06:47:36.005Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
```  

2. Start hive service  
```
[root@ip-172-31-36-60 ~]# curl -X POST -u zebra716:cloudera 'http://34.210.70.18:7180/api/v16/clusters/zebra716/services/hive/commands/start'
{
  "id" : 382,
  "name" : "Start",
  "startTime" : "2017-05-10T06:46:01.108Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
```  

3. Check status of hive servce  
```
[root@ip-172-31-36-60 ~]# curl -X GET -u zebra716:cloudera 'http://34.210.70.178:7180/api/v12/clusters/zebra716/services/hive'
{
  "name" : "hive",
  "type" : "HIVE",
  "clusterRef" : {
    "clusterName" : "cluster"
  },
  "serviceUrl" : "http://ip-172-31-36-60.us-west-2.compute.internal:7180/cmf/serviceRedirect/hive",
  "roleInstancesUrl" : "http://ip-172-31-36-60.us-west-2.compute.internal:7180/cmf/serviceRedirect/hive/instances",
  "serviceState" : "STARTED",
  "healthSummary" : "GOOD",
  "healthChecks" : [ {
    "name" : "HIVE_HIVEMETASTORES_HEALTHY",
    "summary" : "GOOD",
    "suppressed" : false
  }, {
    "name" : "HIVE_HIVESERVER2S_HEALTHY",
    "summary" : "GOOD",
    "suppressed" : false
  } ],
  "configStalenessStatus" : "FRESH",
  "clientConfigStalenessStatus" : "FRESH",
  "maintenanceMode" : false,
  "maintenanceOwners" : [ ],
  "displayName" : "Hive",
  "entityStatus" : "GOOD_HEALTH"
}
```  
