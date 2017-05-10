```
[root@ip-172-31-36-60 etc]# cat /etc/krb5.conf
[logging]
 default = FILE:/var/log/krb5libs.log
 kdc = FILE:/var/log/krb5kdc.log
 admin_server = FILE:/var/log/kadmind.log

[libdefaults]
 default_realm = HADOOP.COM
 dns_lookup_realm = false
 dns_lookup_kdc = false
 ticket_lifetime = 24h
 renew_lifetime = 7d
 forwardable = true
 udp_preference_limit = 1
 default_tgs_enctypes = arcfour-hmac
 default_tkt_enctypes = arcfour-hmac

[realms]
 HADOOP.COM = {
  kdc = 172.31.36.60
  admin_server = 172.31.36.60
 }

[domain_realm]
 .example.com = HADOOP.COM
 example.com = HADOOP.COM
```
