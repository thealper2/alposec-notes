# Common Passwords

- [DefaultCreds](https://github.com/ihebski/DefaultCreds-cheat-sheet) 
- [SecLists](https://github.com/danielmiessler/SecLists/tree/master/Passwords/Default-Credentials)
- [PasswordDatabase](passwordsdatabase.com)
- [cirt](https://www.cirt.net/passwords)

---

# Creating Wordlists

### html2dic

```shell
curl http://example.com > example.txt
html2dic example.txt
```

### Crunch

```shell
crunch min max pattern -o file.txt

# @ küçük harf
# , büyük harf
# % numerik
# ^ özel karakter
```

### Cewl

```shell
cewl http://example.com -w file.txt
```

### Cupp

```shell
# apt install cupp
cupp -h
```

---

# Wordlists

- [SecLists](https://github.com/danielmiessler/SecLists)
- [Google Fuzzing Dictionaries](https://github.com/google/fuzzing/tree/master/dictionaries)
- [Crackstation](https://crackstation.net/crackstation-wordlist-password-cracking-dictionary.htm)

---

# Web Sites

-  [CrackStation](https://crackstation.net/)
- [MD5 Decrypt](https://md5decrypt.net/)
- [OnlineHashCrack](https://www.onlinehashcrack.com/)
- [CyberChef](https://gchq.github.io/CyberChef/)


