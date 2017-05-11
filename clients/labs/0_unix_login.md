export HUE_CONF_DIR="/var/run/cloudera-scm-agent/process/`ls -alrt /var/run/cloudera-scm-agent/process | grep HUE | tail -1 | awk '{print $9}'`"  
  
export HUE_SECRET_KEY=cloudera #password cloudera as same as hue web ui logon password.  
  
export HUE_DATABASE_PASSWORD=123456  #hue repository db's password 

/opt/cloudera/parcels/CDH/lib/hue/build/env/bin/hue useradmin_sync_with_unix  
  
