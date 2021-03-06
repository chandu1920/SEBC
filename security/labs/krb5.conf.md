```
# Configuration snippets may be placed in this directory as well
includedir /etc/krb5.conf.d/

[logging]
 default = FILE:/var/log/krb5libs.log
 kdc = FILE:/var/log/krb5kdc.log
 admin_server = FILE:/var/log/kadmind.log

[libdefaults]
 dns_lookup_realm = false
 ticket_lifetime = 24h
 renew_lifetime = 7d
 forwardable = true
 rdns = false
 udp_preference_limit = 1
 default_tgs_enctypes = arcfour-hmac
 default_tkt_enctypes = arcfour-hmac
 default_realm = HADOOP.COM
 default_ccache_name = KEYRING:persistent:%{uid}

[realms]
HADOOP.COM = {
   kdc = amsterdam.c.sebc-labs.internal
   admin_server = amsterdam.c.sebc-labs.internal
}

[domain_realm]
  .example.com = HADOOP.COM
  example.com = HADOOP.COM
```