- Check

```shell
snmp-check <IP_ADDR> -c public
```

- snmpwalk

```shell
snmpwalk <IP_ADDR> -c public -v <version>
```

- snmpenum

```shell
snmpenum <IP_ADDR> public <config_file>
```

- Nmap scripts

```shell
snmp-brute
snmp-interfaces
snmp-netstat
snmp-processes
snmp-win32-services
snmp-win32-shares
snmp-win32-software
snmp-win32-users
```

- Metasploit-Framework

```shell
auxiliary/scanner/snmp/snmp_login
auxiliary/scanner/snmp/snmp_enum
auxiliary/scanner/snmp/snmp_enumshares
auxiliary/scanner/snmp/snmp_enumusers
post/windows/gather/enum_snmp
```

