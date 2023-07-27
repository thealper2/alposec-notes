- Connection

```shell
ssh <user>@<IP_ADDR>
ssh -i id_rsa <user>@<IP_ADDR>
ssh -p <PORT> -i id_rsa <user>@<IP_ADDR>
```

- Banner grabbing

```shell
nc -vn <IP_ADDR> 22
```

- Public SSH Key

```shell
ssh-keyscan -t <TYPE> <IP_ADDR> -p <PORT>
```

- Nmap scripts:
1. ssh-hostkey
2. ssh-auth-methods
3. ssh2-enum-algos
4. ssh-brute

- Configs

```shell
ssh_config
sshd_config
authorized_keys
ssh_known_hosts
```

- Metasploit Framework

```shell
auxiliary/scanner/ssh/ssh_version
post/multi/gather/ssh_creds
auxiliary/scanner/ssh/ssh_login
scanner/ssh/ssh_identify_pubkeys
scanner/ssh/ssh_enumusers
```