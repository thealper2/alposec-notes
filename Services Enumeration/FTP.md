- Connection

```shell
ftp <IP_ADDR>
```

| Komut | Açıklama |
| - | - |
| send | Dosya gönder |
| put | Dosya yükle |
| mput | Birden fazla dosya yükle |
| get | Dosya indir |
| mget | Birden fazla dosya indir |
| mget \* | Tüm dosyaları indir |

- binary
- ascii

- Banner Grabbing

```shell
nc -vn <IP_ADDR> 21
telnet -n <IP_ADDR> 21
```

- Anonymous Login (anonymous:anonymous)

- Browser -> \ftp://user:pass@<IP_ADDR>

```shell
ftp://anonymous:anonymous@10.10.10.10
```


- Nmap Scripts:
1. ftp-anon
2. ftp-bounce
3. ftp-libopie
4. ftp-proftpd-backdoor
5. ftp-vsftpd-backdoor
6. ftp-vuln-cve2010-4221
7. tftp-enum

```shell
nmap -p 21 --script=<script> <IP_ADDR>
```

- Configs

```shell
ftpusers
ftp.conf
vsftpd.conf
proftpd.conf
```

- Metasploit-Framework

```shell
auxiliary/scanner/ftp/ftp_version
auxiliary/scanner/ftp/anonymous
auxiliary/scanner/ftp/ftp_login
auxiliary/scanner/portscan/ftpbounce
exploit/windows/ftp/proftp_banner
auxiliary/scanner/tftp/tftpbrute
exploit/unix/ftp/vsftpd_234_backdoor
```