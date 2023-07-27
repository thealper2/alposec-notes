- Banner grabbing

```shell
nmap -p 53 --script dns-nsid <IP_ADDR>
```

- NSlookup

```shell
nslookup <IP_ADDR>
```

- Name Servers

```shell
host -t ns <IP_ADDR>
dnsenum <IP_ADDR>
```

- TXT Records

```shell
host -t txt <IP_ADDR>
```

- Dig 

```shell
dig axfr <DOMAIN> @<IP_ADDR>
dig A <DOMAIN> @<IP_ADDR>
dig AAAA <DOMAIN> @<IP_ADDR>
dig TXT <DOMAIN> @<IP_ADDR>
dig MX <DOMAIN> @<IP_ADDR>
dig NS <DOMAIN> @<IP_ADDR>
```

- Fierce

```shell
fierce -dns <DOMAIN>
```

- DNS enum

```shell
dnsrecon -d <IP_ADDR> -t axfr
```

- Domain Names

```shell
whois <IP_ADDR>
```

- Nmap Scripts

```shell
dns-blacklist
dns-brute
dns-check-zone
dns-fuzz
dns-ip6-arpa-scan
dns-nsec-enum
dns-nsid
dns-zone-transfer
```

- Metasploit Framework

```shell
auxiliary/gather/enum_dns
auxiliary/fuzzers/dns/dns_fuzzer
```