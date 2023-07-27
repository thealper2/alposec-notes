- Connection

```shell
redis-cli
```

- Banner grabbing

```shel
nc -vn <IP_ADDR> 6379
```

- Dumping

```shell
redis-cli -h <IP_ADDR>
> INFO keyspace
> KEYS *
> GET <KEY>
```

- Nmap scripts

```shell
redis-brute
redis-info
```

- Metasploit Framework

```shell
auxiliary/scanner/redis/redis_login
```