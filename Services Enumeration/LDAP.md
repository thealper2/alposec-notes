- Ldap search

```shell
ldapsearch -h <IP_ADDR> -p 389 -x -b "dc=example,dc=com"
```

- Nmap scripts

```shell
ldap-brute
ldap-search
```

- Metasploit Framework

```shell
auxiliary/gather/ldap_hashdump
auxiliary/gather/ldap_query
```

