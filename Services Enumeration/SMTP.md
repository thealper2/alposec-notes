- Connection

```shell
telnet <IP_ADDR> 25
```

- Banner grabbing

```shell
nc -vn <IP_ADDR> 25
```

- User enum

```shell
smtp-user-enum -M VRFY -U <user_file> -t <IP_ADDR>
```

- Nmap scripts

```shell
smtp-brute
smtp-commands
smtp-enum-users
smtp-ntlm-info
```

- Metasploit Framework

```shell
auxiliary/scanner/smtp/smtp_version
auxiliary/scanner/smtp/smtp_relay
auxiliary/scanner/smtp/smtp_ntlm_domain
auxiliary/scanner/smtp/smtp_enum
auxiliary/fuzzers/smtp/smtp_fuzzer
```
