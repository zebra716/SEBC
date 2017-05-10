```
{  
  "timestamp" : "2017-05-10T05:42:43.337Z",  
  "clusters" : [ {  
    "name" : "Cluster 1",  
    "version" : "CDH5",  
    "services" : [ {  
      "name" : "hive",  
      "type" : "HIVE",  
      "config" : {  
        "roleTypeConfigs" : [ {  
          "roleType" : "HIVEMETASTORE",  
          "items" : [ {  
            "name" : "hive_metastore_java_heapsize",  
            "value" : "612368384"  
          } ]  
        }, {  
          "roleType" : "HIVESERVER2",  
          "items" : [ {  
            "name" : "hiveserver2_java_heapsize",  
            "value" : "612368384"  
          }, {  
            "name" : "hiveserver2_spark_driver_memory",  
            "value" : "966367641"  
          }, {  
            "name" : "hiveserver2_spark_executor_cores",  
            "value" : "4"  
          }, {  
            "name" : "hiveserver2_spark_executor_memory",  
            "value" : "4679270400"  
          }, {  
            "name" : "hiveserver2_spark_yarn_driver_memory_overhead",  
            "value" : "102"  
          }, {  
            "name" : "hiveserver2_spark_yarn_executor_memory_overhead",  
            "value" : "787"  
          } ]  
        } ],  
        "items" : [ {  
          "name" : "hive_metastore_database_host",  
          "value" : "ip-172-31-36-60.us-west-2.compute.internal"  
        }, {  
          "name" : "hive_metastore_database_name",  
          "value" : "hive"  
        }, {  
          "name" : "hive_metastore_database_password",  
          "value" : "123456"  
        }, {  
          "name" : "hive_metastore_database_user",  
          "value" : "root"  
        }, {  
          "name" : "mapreduce_yarn_service",  
          "value" : "yarn"  
        }, {  
          "name" : "zookeeper_service",  
          "value" : "zookeeper"  
        } ]  
      },  
      "roles" : [ {  
        "name" : "hive-GATEWAY-3d5faea69feccab8df0dc231be3c8415",  
        "type" : "GATEWAY",  
        "hostRef" : {  
          "hostId" : "ca817835-e193-4e58-987d-4564b2d01042"  
        },  
        "config" : {  
          "items" : [ ]  
        }  
      }, {  
        "name" : "hive-GATEWAY-a87cefa945c6950f576eecfa44f60584",  
        "type" : "GATEWAY",  
        "hostRef" : {  
          "hostId" : "5b58f5a6-39c0-43c6-b3cf-083933859bdc"  
        },  
        "config" : {  
          "items" : [ ]  
        }  
      }, {  
        "name" : "hive-GATEWAY-ac71a854fb2665298acc78ffa77e6f1a",  
        "type" : "GATEWAY",  
        "hostRef" : {  
          "hostId" : "15dbc7f1-17db-4d05-bb1c-98b127ec1d97"  
        },  
        "config" : {  
          "items" : [ ]  
        }  
      }, {  
        "name" : "hive-HIVEMETASTORE-3d5faea69feccab8df0dc231be3c8415",  
        "type" : "HIVEMETASTORE",  
        "hostRef" : {  
          "hostId" : "ca817835-e193-4e58-987d-4564b2d01042"  
        },  
        "config" : {  
          "items" : [ {  
            "name" : "role_jceks_password",  
            "value" : "dd8uoyexm4ss8cbzl8whn0vkl"  
          } ]  
        }  
      }, {  
        "name" : "hive-HIVESERVER2-3d5faea69feccab8df0dc231be3c8415",  
        "type" : "HIVESERVER2",  
        "hostRef" : {  
          "hostId" : "ca817835-e193-4e58-987d-4564b2d01042"  
        },  
        "config" : {  
          "items" : [ {  
            "name" : "role_jceks_password",  
            "value" : "14phf4cv3h359bkcl9ae0cgon"  
          } ]  
        }  
      } ],  
      "displayName" : "Hive"  
    }, {  
      "name" : "zookeeper",  
      "type" : "ZOOKEEPER",  
      "config" : {  
        "roleTypeConfigs" : [ {  
          "roleType" : "SERVER",  
          "items" : [ {  
            "name" : "zookeeper_server_java_heapsize",  
            "value" : "612368384"  
          } ]  
        } ],  
        "items" : [ {  
          "name" : "service_config_suppression_server_count_validator",  
          "value" : "true"  
        } ]  
      },  
      "roles" : [ {  
        "name" : "zookeeper-SERVER-3d5faea69feccab8df0dc231be3c8415",  
        "type" : "SERVER",  
        "hostRef" : {  
          "hostId" : "ca817835-e193-4e58-987d-4564b2d01042"  
        },  
        "config" : {  
          "items" : [ {  
            "name" : "role_jceks_password",  
            "value" : "5f02mpn7b0gtyrdo8invy86h9"  
          }, {  
            "name" : "serverId",  
            "value" : "1"  
          } ]  
        }  
      } ],  
      "displayName" : "ZooKeeper"  
    }, {  
      "name" : "hue",  
      "type" : "HUE",  
      "config" : {  
        "roleTypeConfigs" : [ ],  
        "items" : [ {  
          "name" : "database_host",  
          "value" : "ip-172-31-36-60.us-west-2.compute.internal"  
        }, {  
          "name" : "database_password",  
          "value" : "123456"  
        }, {  
          "name" : "database_type",  
          "value" : "mysql"  
        }, {  
          "name" : "database_user",  
          "value" : "root"  
        }, {  
          "name" : "hive_service",  
          "value" : "hive"  
        }, {  
          "name" : "hue_webhdfs",  
          "value" : "hdfs-NAMENODE-3d5faea69feccab8df0dc231be3c8415"  
        }, {  
          "name" : "oozie_service",  
          "value" : "oozie"  
        }, {  
          "name" : "zookeeper_service",  
          "value" : "zookeeper"  
        } ]  
      },  
      "roles" : [ {  
        "name" : "hue-HUE_SERVER-3d5faea69feccab8df0dc231be3c8415",  
        "type" : "HUE_SERVER",  
        "hostRef" : {  
          "hostId" : "ca817835-e193-4e58-987d-4564b2d01042"  
        },  
        "config" : {  
          "items" : [ {  
            "name" : "role_jceks_password",  
            "value" : "al5xhecs4xq6swxw6yxbeq75l"  
          }, {  
            "name" : "secret_key",  
            "value" : "CkxltcWqkYUCLGt6WpblKV7JsSb0E4"  
          } ]  
        }  
      } ],  
      "displayName" : "Hue"  
    }, {  
      "name" : "oozie",  
      "type" : "OOZIE",  
      "config" : {  
        "roleTypeConfigs" : [ {  
          "roleType" : "OOZIE_SERVER",  
          "items" : [ {  
            "name" : "oozie_database_host",  
            "value" : "ip-172-31-36-60.us-west-2.compute.internal"  
          }, {  
            "name" : "oozie_database_password",  
            "value" : "123456"  
          }, {  
            "name" : "oozie_database_type",  
            "value" : "mysql"  
          }, {  
            "name" : "oozie_database_user",  
            "value" : "root"  
          }, {  
            "name" : "oozie_java_heapsize",  
            "value" : "612368384"  
          } ]  
        } ],  
        "items" : [ {  
          "name" : "hive_service",  
          "value" : "hive"  
        }, {  
          "name" : "mapreduce_yarn_service",  
          "value" : "yarn"  
        }, {  
          "name" : "zookeeper_service",  
          "value" : "zookeeper"  
        } ]  
      },  
      "roles" : [ {  
        "name" : "oozie-OOZIE_SERVER-3d5faea69feccab8df0dc231be3c8415",  
        "type" : "OOZIE_SERVER",  
        "hostRef" : {  
          "hostId" : "ca817835-e193-4e58-987d-4564b2d01042"  
        },  
        "config" : {  
          "items" : [ {  
            "name" : "role_jceks_password",  
            "value" : "9irc1cvw5uup27e0iujxlg7r6"  
          } ]  
        }  
      } ],  
      "displayName" : "Oozie"  
    }, {  
      "name" : "yarn",  
      "type" : "YARN",  
      "config" : {  
        "roleTypeConfigs" : [ {  
          "roleType" : "GATEWAY",  
          "items" : [ {  
            "name" : "mapred_reduce_tasks",  
            "value" : "4"  
          }, {  
            "name" : "mapred_submit_replication",  
            "value" : "1"  
          } ]  
        }, {  
          "roleType" : "JOBHISTORY",  
          "items" : [ {  
            "name" : "mr2_jobhistory_java_heapsize",  
            "value" : "612368384"  
          } ]  
        }, {  
          "roleType" : "NODEMANAGER",  
          "items" : [ {  
            "name" : "rm_cpu_shares",  
            "value" : "1600"  
          }, {  
            "name" : "rm_io_weight",  
            "value" : "800"  
          }, {  
            "name" : "yarn_nodemanager_heartbeat_interval_ms",  
            "value" : "100"  
          }, {  
            "name" : "yarn_nodemanager_local_dirs",  
            "value" : "/yarn/nm"  
          }, {  
            "name" : "yarn_nodemanager_log_dirs",  
            "value" : "/yarn/container-logs"  
          }, {  
            "name" : "yarn_nodemanager_resource_cpu_vcores",  
            "value" : "3"  
          }, {  
            "name" : "yarn_nodemanager_resource_memory_mb",  
            "value" : "4584"  
          } ]  
        }, {  
          "roleType" : "RESOURCEMANAGER",  
          "items" : [ {  
            "name" : "resource_manager_java_heapsize",  
            "value" : "612368384"  
          }, {  
            "name" : "yarn_scheduler_maximum_allocation_mb",  
            "value" : "4584"  
          }, {  
            "name" : "yarn_scheduler_maximum_allocation_vcores",  
            "value" : "3"  
          } ]  
        } ],  
        "items" : [ {  
          "name" : "hdfs_service",  
          "value" : "hdfs"  
        }, {  
          "name" : "rm_dirty",  
          "value" : "false"  
        }, {  
          "name" : "rm_last_allocation_percentage",  
          "value" : "80"  
        }, {  
          "name" : "service_health_suppression_yarn_node_managers_healthy",  
          "value" : "true"  
        }, {  
          "name" : "yarn_service_cgroups",  
          "value" : "false"  
        }, {  
          "name" : "yarn_service_lce_always",  
          "value" : "false"  
        }, {  
          "name" : "zk_authorization_secret_key",  
          "value" : "8SEGUwbj79ZiVV96mnaZT8JzFY8OCV"  
        }, {  
          "name" : "zookeeper_service",  
          "value" : "zookeeper"  
        } ]  
      },  
      "roles" : [ {  
        "name" : "yarn-JOBHISTORY-3d5faea69feccab8df0dc231be3c8415",  
        "type" : "JOBHISTORY",  
        "hostRef" : {  
          "hostId" : "ca817835-e193-4e58-987d-4564b2d01042"  
        },  
        "config" : {  
          "items" : [ {  
            "name" : "role_jceks_password",  
            "value" : "3xl4keyis4zaizohc3perpmp0"  
          } ]  
        }  
      }, {  
        "name" : "yarn-NODEMANAGER-a87cefa945c6950f576eecfa44f60584",  
        "type" : "NODEMANAGER",  
        "hostRef" : {  
          "hostId" : "5b58f5a6-39c0-43c6-b3cf-083933859bdc"  
        },  
        "config" : {  
          "items" : [ {  
            "name" : "role_health_suppression_node_manager_heap_dump_directory_free_space",  
            "value" : "true"  
          }, {  
            "name" : "role_health_suppression_node_manager_log_directory_free_space",  
            "value" : "true"  
          }, {  
            "name" : "role_health_suppression_nodemanager_local_data_directories_free_space",  
            "value" : "true"  
          }, {  
            "name" : "role_health_suppression_nodemanager_log_directories_free_space",  
            "value" : "true"  
          }, {  
            "name" : "role_health_suppression_nodemanager_recovery_directory_free_space",  
            "value" : "true"  
          }, {  
            "name" : "role_jceks_password",  
            "value" : "4q34ico52g39kz4fnu1zyngq9"  
          } ]  
        }  
      }, {  
        "name" : "yarn-NODEMANAGER-ac71a854fb2665298acc78ffa77e6f1a",  
        "type" : "NODEMANAGER",  
        "hostRef" : {  
          "hostId" : "15dbc7f1-17db-4d05-bb1c-98b127ec1d97"  
        },  
        "config" : {  
          "items" : [ {  
            "name" : "role_health_suppression_node_manager_heap_dump_directory_free_space",  
            "value" : "true"  
          }, {  
            "name" : "role_health_suppression_node_manager_log_directory_free_space",  
            "value" : "true"  
          }, {  
            "name" : "role_health_suppression_nodemanager_local_data_directories_free_space",  
            "value" : "true"  
          }, {  
            "name" : "role_health_suppression_nodemanager_log_directories_free_space",  
            "value" : "true"  
          }, {  
            "name" : "role_health_suppression_nodemanager_recovery_directory_free_space",  
            "value" : "true"  
          }, {  
            "name" : "role_jceks_password",  
            "value" : "7hj3bp5rxwadudszhcbnfmr25"  
          } ]  
        }  
      }, {  
        "name" : "yarn-RESOURCEMANAGER-3d5faea69feccab8df0dc231be3c8415",  
        "type" : "RESOURCEMANAGER",  
        "hostRef" : {  
          "hostId" : "ca817835-e193-4e58-987d-4564b2d01042"  
        },  
        "config" : {  
          "items" : [ {  
            "name" : "rm_id",  
            "value" : "61"  
          }, {  
            "name" : "role_jceks_password",  
            "value" : "bmrt0coya4c2ndvdkrkf0je76"  
          } ]  
        }  
      } ],  
      "displayName" : "YARN (MR2 Included)"  
    }, {  
      "name" : "hdfs",  
      "type" : "HDFS",  
      "config" : {  
        "roleTypeConfigs" : [ {  
          "roleType" : "BALANCER",  
          "items" : [ {  
            "name" : "balancer_java_heapsize",  
            "value" : "612368384"  
          } ]  
        }, {  
          "roleType" : "DATANODE",  
          "items" : [ {  
            "name" : "datanode_java_heapsize",  
            "value" : "1073741824"  
          }, {  
            "name" : "dfs_data_dir_list",  
            "value" : "/dfs/dn"  
          }, {  
            "name" : "dfs_datanode_du_reserved",  
            "value" : "3170683699"  
          }, {  
            "name" : "dfs_datanode_max_locked_memory",  
            "value" : "4294967296"  
          }, {  
            "name" : "rm_cpu_shares",  
            "value" : "400"  
          }, {  
            "name" : "rm_io_weight",  
            "value" : "200"  
          } ]  
        }, {  
          "roleType" : "GATEWAY",  
          "items" : [ {  
            "name" : "dfs_client_use_trash",  
            "value" : "true"  
          } ]  
        }, {  
          "roleType" : "JOURNALNODE",  
          "items" : [ {  
            "name" : "dfs_journalnode_edits_dir",  
            "value" : "/dfs/jn"  
          } ]  
        }, {  
          "roleType" : "NAMENODE",  
          "items" : [ {  
            "name" : "dfs_name_dir_list",  
            "value" : "/dfs/nn"  
          }, {  
            "name" : "dfs_namenode_servicerpc_address",  
            "value" : "8022"  
          }, {  
            "name" : "namenode_java_heapsize",  
            "value" : "612368384"  
          }, {  
            "name" : "role_config_suppression_namenode_java_heapsize_minimum_validator",  
            "value" : "true"  
          } ]  
        }, {  
          "roleType" : "SECONDARYNAMENODE",  
          "items" : [ {  
            "name" : "fs_checkpoint_dir_list",  
            "value" : "/dfs/snn"  
          }, {  
            "name" : "secondary_namenode_java_heapsize",  
            "value" : "612368384"  
          } ]  
        } ],  
        "items" : [ {  
          "name" : "dfs_ha_fencing_cloudera_manager_secret_key",  
          "value" : "U2hxg2zQoDpPtMMeRJXr7VjPU4vMrE"  
        }, {  
          "name" : "fc_authorization_secret_key",  
          "value" : "hacqUSJ8UQWSaBLs2RzvC0EIeWe3IE"  
        }, {  
          "name" : "http_auth_signature_secret",  
          "value" : "344dlYU8kSnqaH8N4k853kamrlgGLR"  
        }, {  
          "name" : "rm_dirty",  
          "value" : "false"  
        }, {  
          "name" : "rm_last_allocation_percentage",  
          "value" : "20"  
        }, {  
          "name" : "service_config_suppression_datanode_count_validator",  
          "value" : "true"  
        }, {  
          "name" : "service_health_suppression_hdfs_under_replicated_blocks",  
          "value" : "true"  
        }, {  
          "name" : "zookeeper_service",  
          "value" : "zookeeper"  
        } ]  
      },  
      "roles" : [ {  
        "name" : "hdfs-BALANCER-3d5faea69feccab8df0dc231be3c8415",  
        "type" : "BALANCER",  
        "hostRef" : {  
          "hostId" : "ca817835-e193-4e58-987d-4564b2d01042"  
        },  
        "config" : {  
          "items" : [ ]  
        }  
      }, {  
        "name" : "hdfs-DATANODE-a87cefa945c6950f576eecfa44f60584",  
        "type" : "DATANODE",  
        "hostRef" : {  
          "hostId" : "5b58f5a6-39c0-43c6-b3cf-083933859bdc"  
        },  
        "config" : {  
          "items" : [ {  
            "name" : "role_health_suppression_data_node_heap_dump_directory_free_space",  
            "value" : "true"  
          }, {  
            "name" : "role_health_suppression_data_node_log_directory_free_space",  
            "value" : "true"  
          }, {  
            "name" : "role_health_suppression_datanode_data_directories_free_space",  
            "value" : "true"  
          }, {  
            "name" : "role_jceks_password",  
            "value" : "dyokl9zulyewcv1shjdmsn2j8"  
          } ]  
        }  
      }, {  
        "name" : "hdfs-DATANODE-ac71a854fb2665298acc78ffa77e6f1a",  
        "type" : "DATANODE",  
        "hostRef" : {  
          "hostId" : "15dbc7f1-17db-4d05-bb1c-98b127ec1d97"  
        },  
        "config" : {  
          "items" : [ {  
            "name" : "role_health_suppression_data_node_heap_dump_directory_free_space",  
            "value" : "true"  
          }, {  
            "name" : "role_health_suppression_data_node_log_directory_free_space",  
            "value" : "true"  
          }, {  
            "name" : "role_health_suppression_datanode_data_directories_free_space",  
            "value" : "true"  
          }, {  
            "name" : "role_jceks_password",  
            "value" : "37spf4gbrdbftsexqwxy3cz1t"  
          } ]  
        }  
      }, {  
        "name" : "hdfs-FAILOVERCONTROLLER-3d5faea69feccab8df0dc231be3c8415",  
        "type" : "FAILOVERCONTROLLER",  
        "hostRef" : {  
          "hostId" : "ca817835-e193-4e58-987d-4564b2d01042"  
        },  
        "config" : {  
          "items" : [ {  
            "name" : "role_jceks_password",  
            "value" : "86xn41zkgjkepf8jnj2ck7xs3"  
          } ]  
        }  
      }, {  
        "name" : "hdfs-FAILOVERCONTROLLER-a87cefa945c6950f576eecfa44f60584",  
        "type" : "FAILOVERCONTROLLER",  
        "hostRef" : {  
          "hostId" : "5b58f5a6-39c0-43c6-b3cf-083933859bdc"  
        },  
        "config" : {  
          "items" : [ {  
            "name" : "role_health_suppression_hdfs_failovercontroller_heap_dump_directory_free_space",  
            "value" : "true"  
          }, {  
            "name" : "role_health_suppression_hdfs_failovercontroller_log_directory_free_space",  
            "value" : "true"  
          }, {  
            "name" : "role_jceks_password",  
            "value" : "858o05bankibk4538vx6ps2rv"  
          } ]  
        }  
      }, {  
        "name" : "hdfs-JOURNALNODE-3d5faea69feccab8df0dc231be3c8415",  
        "type" : "JOURNALNODE",  
        "hostRef" : {  
          "hostId" : "ca817835-e193-4e58-987d-4564b2d01042"  
        },  
        "config" : {  
          "items" : [ {  
            "name" : "role_jceks_password",  
            "value" : "bj5crqnuje8tsqgz30hhkoqdw"  
          } ]  
        }  
      }, {  
        "name" : "hdfs-JOURNALNODE-a87cefa945c6950f576eecfa44f60584",  
        "type" : "JOURNALNODE",  
        "hostRef" : {  
          "hostId" : "5b58f5a6-39c0-43c6-b3cf-083933859bdc"  
        },  
        "config" : {  
          "items" : [ {  
            "name" : "role_health_suppression_journal_node_edits_directory_free_space",  
            "value" : "true"  
          }, {  
            "name" : "role_health_suppression_journal_node_heap_dump_directory_free_space",  
            "value" : "true"  
          }, {  
            "name" : "role_health_suppression_journal_node_log_directory_free_space",  
            "value" : "true"  
          }, {  
            "name" : "role_jceks_password",  
            "value" : "3jjdltqq9zkxvtfzvtnhag118"  
          } ]  
        }  
      }, {  
        "name" : "hdfs-JOURNALNODE-ac71a854fb2665298acc78ffa77e6f1a",  
        "type" : "JOURNALNODE",  
        "hostRef" : {  
          "hostId" : "15dbc7f1-17db-4d05-bb1c-98b127ec1d97"  
        },  
        "config" : {  
          "items" : [ {  
            "name" : "role_health_suppression_journal_node_edits_directory_free_space",  
            "value" : "true"  
          }, {  
            "name" : "role_health_suppression_journal_node_heap_dump_directory_free_space",  
            "value" : "true"  
          }, {  
            "name" : "role_health_suppression_journal_node_log_directory_free_space",  
            "value" : "true"  
          }, {  
            "name" : "role_jceks_password",  
            "value" : "5s8wd0bxb6bjiujz3kp32k3mq"  
          } ]  
        }  
      }, {  
        "name" : "hdfs-NAMENODE-3d5faea69feccab8df0dc231be3c8415",  
        "type" : "NAMENODE",  
        "hostRef" : {  
          "hostId" : "ca817835-e193-4e58-987d-4564b2d01042"  
        },  
        "config" : {  
          "items" : [ {  
            "name" : "autofailover_enabled",  
            "value" : "true"  
          }, {  
            "name" : "dfs_federation_namenode_nameservice",  
            "value" : "nameservice1"  
          }, {  
            "name" : "dfs_namenode_quorum_journal_name",  
            "value" : "nameservice1"  
          }, {  
            "name" : "namenode_id",  
            "value" : "63"  
          }, {  
            "name" : "role_jceks_password",  
            "value" : "980dmimqtu56hbkniydppaqr6"  
          } ]  
        }  
      }, {  
        "name" : "hdfs-NAMENODE-a87cefa945c6950f576eecfa44f60584",  
        "type" : "NAMENODE",  
        "hostRef" : {  
          "hostId" : "5b58f5a6-39c0-43c6-b3cf-083933859bdc"  
        },  
        "config" : {  
          "items" : [ {  
            "name" : "autofailover_enabled",  
            "value" : "true"  
          }, {  
            "name" : "dfs_federation_namenode_nameservice",  
            "value" : "nameservice1"  
          }, {  
            "name" : "dfs_namenode_quorum_journal_name",  
            "value" : "nameservice1"  
          }, {  
            "name" : "namenode_id",  
            "value" : "67"  
          }, {  
            "name" : "role_health_suppression_name_node_data_directories_free_space",  
            "value" : "true"  
          }, {  
            "name" : "role_health_suppression_name_node_heap_dump_directory_free_space",  
            "value" : "true"  
          }, {  
            "name" : "role_health_suppression_name_node_log_directory_free_space",  
            "value" : "true"  
          }, {  
            "name" : "role_jceks_password",  
            "value" : "7p79h0kalfsf7f847xhnym6p4"  
          } ]  
        }  
      } ],  
      "displayName" : "HDFS"  
    } ]  
  } ],  
  "hosts" : [ {  
    "hostId" : "ca817835-e193-4e58-987d-4564b2d01042",  
    "ipAddress" : "172.31.36.60",  
    "hostname" : "ip-172-31-36-60.us-west-2.compute.internal",  
    "rackId" : "/default",  
    "config" : {  
      "items" : [ {  
        "name" : "host_config_suppression_memory_overcommitted_validator",  
        "value" : "true"  
      } ]  
    }  
  }, {  
    "hostId" : "15dbc7f1-17db-4d05-bb1c-98b127ec1d97",  
    "ipAddress" : "172.31.37.233",  
    "hostname" : "ip-172-31-37-233.us-west-2.compute.internal",  
    "rackId" : "/default",  
    "config" : {  
      "items" : [ {  
        "name" : "host_health_suppression_host_agent_parcel_directory_free_space",  
        "value" : "true"  
      }, {  
        "name" : "host_health_suppression_host_clock_offset",  
        "value" : "true"  
      } ]  
    }  
  }, {  
    "hostId" : "5b58f5a6-39c0-43c6-b3cf-083933859bdc",  
    "ipAddress" : "172.31.43.51",  
    "hostname" : "ip-172-31-43-51.us-west-2.compute.internal",  
    "rackId" : "/default",  
    "config" : {  
      "items" : [ {  
        "name" : "host_config_suppression_memory_overcommitted_validator",  
        "value" : "true"  
      }, {  
        "name" : "host_health_suppression_host_agent_parcel_directory_free_space",  
        "value" : "true"  
      }, {  
        "name" : "host_health_suppression_host_clock_offset",  
        "value" : "true"  
      } ]  
    }  
  } ],  
  "users" : [ {  
    "name" : "__cloudera_internal_user__mgmt-EVENTSERVER-3d5faea69feccab8df0dc231be3c8415",  
    "roles" : [ "ROLE_USER" ],  
    "pwHash" : "3790db1a761f437495f6cffeea2302a4b1e0f1ae4275b3a555ee0d7481922f7e",  
    "pwSalt" : -6891416436474578351,  
    "pwLogin" : true  
  }, {  
    "name" : "__cloudera_internal_user__mgmt-HOSTMONITOR-3d5faea69feccab8df0dc231be3c8415",  
    "roles" : [ "ROLE_USER" ],  
    "pwHash" : "7318d624dbae10607f523e00ffa950340ada3b7bd4a6b00ac91da969137fec21",  
    "pwSalt" : 330161312637122099,  
    "pwLogin" : true  
  }, {  
    "name" : "__cloudera_internal_user__mgmt-REPORTSMANAGER-3d5faea69feccab8df0dc231be3c8415",  
    "roles" : [ "ROLE_USER" ],  
    "pwHash" : "284f247cb68860069a2704d818669ac95a7306e8541552b4ba34dba328945f7f",  
    "pwSalt" : -5988507809209229060,  
    "pwLogin" : true  
  }, {  
    "name" : "__cloudera_internal_user__mgmt-SERVICEMONITOR-3d5faea69feccab8df0dc231be3c8415",  
    "roles" : [ "ROLE_USER" ],  
    "pwHash" : "2d3fad82168f6a5e7dabdd44d17f92b05e53006df5e6f18566c0d6b477ab1c89",  
    "pwSalt" : 1593613436148299390,  
    "pwLogin" : true  
  }, {  
    "name" : "admin",  
    "roles" : [ "ROLE_LIMITED" ],  
    "pwHash" : "ac2cb2aa10a18165f7fa08cbb336b2fff358820e2bf3b13f46219e39935cb348",  
    "pwSalt" : 1929501651514675292,  
    "pwLogin" : true  
  }, {  
    "name" : "minotaur",  
    "roles" : [ "ROLE_CONFIGURATOR" ],  
    "pwHash" : "1a685fb3df7ac4ae9af9fbce006e2c9fe0a757736c0866f763064fc1d7f645a8",  
    "pwSalt" : -6199128740889594673,  
    "pwLogin" : true  
  }, {  
    "name" : "zebra716",  
    "roles" : [ "ROLE_ADMIN" ],  
    "pwHash" : "51fed0a9125eb65064cbdf71f23e8e9335bc31a7c2f6c637f5d06dcb74e92280",  
    "pwSalt" : 7281874779906640856,  
    "pwLogin" : true  
  } ],  
  "versionInfo" : {  
    "version" : "5.11.0",  
    "buildUser" : "jenkins",  
    "buildTimestamp" : "20170412-1249",  
    "gitHash" : "70cb1442626406432a6e7af5bdf206a384ca3f98",  
    "snapshot" : false  
  },  
  "managementService" : {  
    "name" : "mgmt",  
    "type" : "MGMT",  
    "config" : {  
      "roleTypeConfigs" : [ {  
        "roleType" : "EVENTSERVER",  
        "items" : [ {  
          "name" : "event_server_heapsize",  
          "value" : "612368384"  
        } ]  
      }, {  
        "roleType" : "HOSTMONITOR",  
        "items" : [ {  
          "name" : "firehose_heapsize",  
          "value" : "612368384"  
        }, {  
          "name" : "firehose_non_java_memory_bytes",  
          "value" : "805306368"  
        }, {  
          "name" : "role_config_suppression_firehose_heap_size_validator",  
          "value" : "true"  
        }, {  
          "name" : "role_config_suppression_firehose_non_java_memory_validator",  
          "value" : "true"  
        } ]  
      }, {  
        "roleType" : "REPORTSMANAGER",  
        "items" : [ {  
          "name" : "headlamp_database_host",  
          "value" : "ip-172-31-36-60.us-west-2.compute.internal"  
        }, {  
          "name" : "headlamp_database_name",  
          "value" : "rm"  
        }, {  
          "name" : "headlamp_database_password",  
          "value" : "123456"  
        }, {  
          "name" : "headlamp_database_user",  
          "value" : "root"  
        }, {  
          "name" : "headlamp_heapsize",  
          "value" : "612368384"  
        } ]  
      }, {  
        "roleType" : "SERVICEMONITOR",  
        "items" : [ {  
          "name" : "firehose_heapsize",  
          "value" : "612368384"  
        }, {  
          "name" : "firehose_non_java_memory_bytes",  
          "value" : "805306368"  
        }, {  
          "name" : "role_config_suppression_firehose_heap_size_validator",  
          "value" : "true"  
        }, {  
          "name" : "role_config_suppression_firehose_non_java_memory_validator",  
          "value" : "true"  
        } ]  
      } ],  
      "items" : [ ]  
    },  
    "roles" : [ {  
      "name" : "mgmt-ALERTPUBLISHER-3d5faea69feccab8df0dc231be3c8415",  
      "type" : "ALERTPUBLISHER",  
      "hostRef" : {  
        "hostId" : "ca817835-e193-4e58-987d-4564b2d01042"  
      },  
      "config" : {  
        "items" : [ {  
          "name" : "role_jceks_password",  
          "value" : "eck4t3eem2c3b2xyv6ahokln0"  
        } ]  
      }  
    }, {  
      "name" : "mgmt-EVENTSERVER-3d5faea69feccab8df0dc231be3c8415",  
      "type" : "EVENTSERVER",  
      "hostRef" : {  
        "hostId" : "ca817835-e193-4e58-987d-4564b2d01042"  
      },  
      "config" : {  
        "items" : [ {  
          "name" : "role_jceks_password",  
          "value" : "2246vjki9p8mys4swpx5o2ik1"  
        } ]  
      }  
    }, {  
      "name" : "mgmt-HOSTMONITOR-3d5faea69feccab8df0dc231be3c8415",  
      "type" : "HOSTMONITOR",  
      "hostRef" : {  
        "hostId" : "ca817835-e193-4e58-987d-4564b2d01042"  
      },  
      "config" : {  
        "items" : [ {  
          "name" : "role_jceks_password",  
          "value" : "5m2nvq0ca6axhmcwely7evos2"  
        } ]  
      }  
    }, {  
      "name" : "mgmt-REPORTSMANAGER-3d5faea69feccab8df0dc231be3c8415",  
      "type" : "REPORTSMANAGER",  
      "hostRef" : {  
        "hostId" : "ca817835-e193-4e58-987d-4564b2d01042"  
      },  
      "config" : {  
        "items" : [ {  
          "name" : "role_jceks_password",  
          "value" : "crp3vamz8xx3anvksi7f0u27m"  
        } ]  
      }  
    }, {  
      "name" : "mgmt-SERVICEMONITOR-3d5faea69feccab8df0dc231be3c8415",  
      "type" : "SERVICEMONITOR",  
      "hostRef" : {  
        "hostId" : "ca817835-e193-4e58-987d-4564b2d01042"  
      },  
      "config" : {  
        "items" : [ {  
          "name" : "role_jceks_password",  
          "value" : "6g9dyiye0f67f60kupcoes8ae"  
        } ]  
      }  
    } ],  
    "displayName" : "Cloudera Management Service"  
  },  
  "managerSettings" : {  
    "items" : [ {  
      "name" : "CLUSTER_STATS_START",  
      "value" : "10/27/2012 15:00"  
    }, {  
      "name" : "PUBLIC_CLOUD_STATUS",  
      "value" : "ON_PUBLIC_CLOUD"  
    }, {  
      "name" : "REMOTE_PARCEL_REPO_URLS",  
      "value" : "https://archive.cloudera.com/cdh5/parcels/{latest_supported}/,https://archive.cloudera.com/cdh4/parcels/latest/,https://archive.cloudera.com/impala/parcels/latest/,https://archive.cloudera.com/search/parcels/latest/,https://archive.cloudera.com/accumulo/parcels/1.4/,https://archive.cloudera.com/accumulo-c5/parcels/latest/,https://archive.cloudera.com/kafka/parcels/latest/,https://archive.cloudera.com/navigator-keytrustee5/parcels/latest/,http://archive.cloudera.com/kudu/parcels/latest/,https://archive.cloudera.com/spark/parcels/latest/,https://archive.cloudera.com/sqoop-connectors/parcels/latest/"  
    } ]  
  }  
}
```  
