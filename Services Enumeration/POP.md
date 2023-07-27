| Komut | Açıklama |
| - | - |
| USER | Giriş yap |
| PASS | Parola |
| STAT | Durum |
| LIST | Mesajları listele | 
| RETR | Mesajı göster |
| QUIT | Çıkış |

- Banner grabbing

```shell
nc -vn <IP_ADDR> 110
```

- Connection 

```shell
telnet <IP_ADDR> 110
```

- Nmap scripts

```shell
pop3-brute
pop3-capabilities
```

- Metasploit Framework

```shell
auxiliary/scanner/pop3/pop3_version
auxiliary/scanner/pop3/pop3_login
```

