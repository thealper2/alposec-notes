- Scanning

```shell
nmap -p 139,445 --open 192.168.1.0/24
nbtscan -r 192.168.1.0/24
enum4linux -a <IP_ADDR>
crackmapexec -u <user> -p <password> --shares <IP_ADDR>
smbmap -H <IP_ADDR>
smbclient -L \\<IP_ADDR>
```

- Connection 

```shell
smbclient -L \\<IP_ADDR>
smbclient \\\\<IP_ADDR>\\<SHARE>
smbclient \\\\<IP_ADDR>\\<SHARE> -U <user>
```

- Hostname

```shell
nmblookup -A <IP_ADDR>
```

- Browser connection

```shell
smb://<IP_ADDR>/<SHARE>
xdg-open smb://<IP_ADDR>
```

- Nmap Scripts

```shell
smb-brute
smb-enum-domains
smb-enum-groups
smb-enum-processes
smb-enum-services
smb-enum-sessions
smb-enum-shares
smb-enum-users
smb-os-discovery
smb-system-info
```

- Mount

```shell
mount -t cifs //<IP_ADDR>/<SHARE> /mnt/path
```

- Metasploit-Framework

```shell
auxiliary/scanner/smb/smb_lookupsid
auxiliary/scanner/smb/smb_enumusers_domain
auxiliary/scanner/smb/smb_login
auxiliary/scanner/smb/smb_enumshares
auxiliary/scanner/smb/smb_enumusers
auxiliary/scanner/smb/smb_version
```