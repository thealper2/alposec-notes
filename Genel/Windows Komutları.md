# CMD Komutları

### Sistem Bilgisi Komutları

| Komut | Açıklama | 
| - | - |
| systeminfo | Sistem hakkında genel bilgileri sağlar, bu komutla işlemci, bellek, işletim sistemi sürümü, yüklü güncelleştirmeler ve daha fazlası hakkında bilgi görüntüler. |
| wmic cpu get caption | İşlemci hakkında bilgi verir. |
| wmic memorychip get capacity | Bellek modüllerinin kapasitelerini gösterir. |
| wmic os get caption, version | İşletim sistemi adı ve sürümü hakkında bilgi verir. |
| wmic qfe list full | Yüklü olan güncelleştirmeleri gösterir. | 
| systeminfo \| find "Total Physical Memory" | Toplam fiziksel bellek miktarını gösterir. |
| systeminfo \| find "Available Physical Memory" | Kullanılabilir fiziksel bellek miktarını gösterir. |
| systeminfo \| find "Available Virtual Memory" | Kullanılabilir sanal bellek miktarını gösterir. |
| systeminfo \| find "Network Card(s)" | Sistemde bulunan ağ kartları hakkında bilgi verir. |
| ipconfig /all | Ağ yapılandırma bilgilerini gösterir. |
| hostname | Bilgisayarın adını gösterir. |
| ping google.com | İnternet bağlantısını test etmek için Google'a ping atar. |
| shutdown | Bilgisayarı kapatmak veya yeniden başlatmak için kullanılır. |

### Donanım Bilgisi Komutları

| Komut | Açıklama | 
| - | - |
| wmic cpu get caption | Sistemde bulunan işlemci hakkında bilgi verir. Model ve üretici bilgisini gösterir. |
| wmic memorychip get capacity | Bellek modüllerinin kapasitelerini gösterir. Her bir modülün kapasitesini megabyte (MB) cinsinden listeler. |
| wmic bios get serialnumber | BIOS'un seri numarasını gösterir. |
| wmic baseboard get product | Anakartın modelini gösterir. |
| wmic diskdrive get caption, size | Sistemdeki sabit disk sürücülerinin adını ve kapasitelerini gösterir. |
| wmic diskdrive get status | Disk sürücülerinin durumunu gösterir. |
| wmic path win32_videocontrller get caption | Sistemdeki grafik kartının adını gösterir. |
| wmic sounddev get caption | Sistemdeki ses kartlarının adlarını gösterir. |
| wmic nic get name, speed | Sistemdeki yazıcıların adlarını gösterir. |
| wmic printer get name | Sistemdeki yazıcıların adlarını gösterir. |
| systeminfo | Birçok sistem bilgisini görüntüler. |
| wmic baseboard get manufacturer | Anakartın üreticisini gösterir. |
| wmic baseboard get version | Anakartın sürümünü gösterir. |
| wmic bios get name, version, serialnumber | BIOS'un adını, sürümünü ve seri numarasını gösterir. |
| wmic path win32_physicalmemory get capacity | Fiziksel bellek modüllerinin kapasitelerini gösterir. |
| wmic path win32_physicalmemory get manufacturer | Fiziksel bellek modüllerinin üreticisini gösterir. |
| wmic path win32_phyiscalmemory get partnumber | Fiziksel bellek modüllerinin parça numaralarını gösterir. |
| wmic path win32_phyiscalmemory get speed | Fiziksel bellek modüllerinin hızını gösterir. |
| wmic path win32_videocontroller get caption, adapterram | Sistemdei grafik kartlarının adını ve bellek kapasitelerini gösterir. |
| wmic sounddev get caption, status | Sistemdei ses kartlarının adlarını ve durumlarını gösterir. | 
| wmic nicconfig get caption, ipaddress, macaddress | Ağ kartlarının adlarını, IP adreslerini ve MAC adreslerini gösterir. |
| wmic diskdrive get caption, size, interfacetype | Sistemdeki sabit disk sürücülerinin adlarını, kapasitelerini ve arayüz türlerini gösterir. |
| wmic cdrom get caption | Sistemdei CD/DVD sürücülerinin adlarını gösterir. |
| wmic printer get name, portname | Sistemdeki yazıcıların adlarını ve bağlantı portlarını gösterir. |
| wmic product get name, version | Sistemdeki yüklü yazılımların adlarını ve sürümlerini gösterir. |
| wmic path win32_battery get caption, status, estimatedchargeremaining | Bilgisayarın pil bilgilerini gösterir. (Sadece laptoplarda çalışır.) |
| wmic path win32_keyboard get caption | Klavye bilgilerini gösterir. |
| wmic path win32_pointingdevice get caption | Fare veya dokunmatik yüzey bilgilerini gösterir. |

### Performans İzleme ve İstatistik Komutları

| Komut | Açıklama |
| - | - |
| tasklist | Çalışan işlemleri listeler. Görev yöneticisi benzeri bir liste sağlar. |
| tasklist /v | Daha detaylı işlem bilgilerini gösterir. |
| tasklist /m | Her işlemin yüklü modülleriyle birlikte listelenmesini sağlar. |
| tasklist /svc | Hizmet adlarını da gösterir, böylece hizmetlere ait işlemleri tespit etmeyi sağlar. | 
| tasklist /fi "imagename eq program.exe" | Belirli bir programın çalışıp çalışmadığını kontrol etmek için kullanılır. |
| tasklist /fi "status eq running" | Yalnızca çalışan işlemleri listeler. |
| wmic process get Caption, Processid, Commandline | Sistemde çalışan işlemlerin adını, PID'ini ve komut satırını gösterir. |
| perfmon | Performans monitörünü açar. |
| wmic cpu get loadpercentage | İşlemcinin mevcut yük yüzdesini gösterir. |
| wmic memorychip get capacity | Bellek modüllerinin kapasitelerini gösterir. |
| wmic diskdrive get size | Disk sürücülerinin boyutlarını gösterir. |
| wmic nic get name, speed | Sistemdeki ağ kartlarının adlarını ve hızlarını gösterir. |
| wmic cpu get caption, deviceid, maxclockspeed | İşlemci adı, cihaz kimliği ve maksimum saat hızı bilgilerini gösterir. |
| wmic os get freephysicalmemory | Sistemdeki boş fiziksel bellek miktarını gösterir. |
| wmic diskdrive get caption, status | Disk sürücülerinin durumlarını gösterir. |
| wmic logicaldisk get caption, size, freespace | Mantıksal disk sürücülerinin adını, toplam boyutunu ve boş alan miktarını gösterir. |
| wmic nic get name, netconnectionstatus | Ağ kartlarının adlarını ve bağlantı durumlarını gösterir. | 
| wmic path win32_networkadapter get netconnectionid, speed | Ağ adaptörlerinin bağlantı kimliklerini ve hızlarını gösterir. |
| wmic path win32_perfformatteddata_perfos_processor get name, percentprocessortime | İşlemcinin toplam işlemci zamanının yüzdesini gösterir. |
| wmic path win32_perfformatteddata_perfos_memory get AvailableMBytes | Kullanılabilir fiziksel bellek miktarını megabyte (MB) cinsinden gösterir. |
| wmic path win32_perfformatteddata_perfos_pagefile get percentusage | Sayfa dosyasının kullanım yüzdesini gösterir. |
| wmic qfe list full | Yüklü olan tüm güvenlik güncelleştirmelerini ve yamaları listeler. |
| wmic process where "name='process_name'" get caption, processid, workingsetsize | Belirli bir işlemin adını ve çalışma kümesi boyutunu gösterir. |
| netstat -a | Açık olan bağlantıları ve portları listeler. |
| netstat -e | Ağ arabirimlerine ait istatistikleri gösterir. |

### Kullanıcı Bilgileri ve Yönetimi Komutları

| Komut | Açıklama |
| - | - |
| whoami | Geçerli kullanıcı adını gösterir. |
| net user | Kullanıcı hesaplarını listeler. |
| net user username | Belirli bir kullanıcı hakkında detayli bilgileri gösterir.|
| net user username password | Belirli bir kullanıcı hesabının parolasını değiştirmek için kullanılır. |
| net user username /passwordreq:yes\|no | Bir kullanıcının parola gerekliliğini açar veya kapatır. |
| net user username /active:yes\|no | Bir kullanıcının hesabını aktifleştirir veya devre dışı bırakır. |
| net user username /expires:dd.mm.yyyy | Bir kullanıcının hesap son kullanma tarihini belirler. |
| net user username /fullname:"Full Name" | Bir kullanıcının tam adını günceller. |
| net user username /comment:"Comment" | Bir kullanıcı hesabına açıklama ekler. |
| net user newuser password /add | Yeni bir kullanıcı hesabı oluşturur. |
| net user username /delete | Kullanıcı hesabı siler. |
| net localgroup | Mevcut kullanıcı gruplarını listeler. |
| net localgroup groupname | Belirli bir kullanıcı grubu hakkında detayli bilgileri gösterir. |
| net localgroup groupname username /add | Belirtilen kullanıcıyı belirtilen gruba ekler. |
| net localgroup groupname username /delete | Belirtilen kullanıcıyı belirtilen gruptan çıkarır. |
| net accounts | Kullanıcı hesap politikalarını gösterir ve yapılandırabilir. |
| net session | Açık oturumarı listeler. |
| net session ID /delete | Belirtilen oturumu sonlandırır. |
| net time | Sistem saatini ayarlamak için kullanılır. |
| net time \computername /set | Sistem saatini belirtilen addaki bilgisayarın saatine ayarlayacaktır. |

### Dosya ve Dizin Komutları

| Komut | Açıklama |
| - | - |
| cd | Dizin değiştirmek için kullanılır. |
| mkdir | Yeni bir klasör oluşturmak için kullanılır. |
| rmdir | Klasörleri silmek için kullanılır. |
| dir | Mevut dizindeki dosya ve klasörleri listeler. |
| copy | Dosya ve klasörleri kopyalamak için kullanılır. |
| move | Dosya veya klasörleri taşımak için kullanılır. |
| del | Dosyaları silmek için kullanılır. |
| ren | Dosya veya klasörleri yeniden adlandırmak için kullanılır. |
| type | Dosyanın içeriğini ekrana yazdırmak için kullanılır. |
| more | Dosyanın içeriğini sayfa sayfa görmek için kullanılır. |
| find | Dosyada belirli bir metni aramak için kullanılır. |
| tree | Dizin yapısını ağaç şeklinde gösterir. |

### Ağ Komutları

| Komut | Açıklama |
| - | - |
| ping | Bir IP adresine veya alan adına ping atmak için kullanılır. |
| ipconfig | Ağ yapılandırma bilgilerini gösterir. |
| nslookup | Bir alan adının IP adresini ve tersine çözümlenmesini bulmak için kullanılır. |
| netstat | Ağ bağlantılarını ve bağlantı noktalarını görüntülemek için kullanılır. |
| tracert | Bir IP adresine veya alan adına giden yolun izlenmesi için kullanılır. |
| pathping | Tracert ile benzer şekilde, belirli bir IP adresine veya alan adına giden yolun izlenmesi için kullanılır. |
| arp | ARP önbellek tablosunu görüntülemek ve düzenlemek için kullanılır. |
| netsh | Ağ yapılandırmasını ve durumunu yönetmek için kullanılır. | 
| nbtstat | Ağ yapılandırmasını ve durumunu yönetmek için kullanılır. |
| net view | Ağda paylaşılan kaynakları gösterir. |
| net use | Başka bir bilgisiyardaki paylaşılmış bir kaynapı ağ sürücüsüne atamak için kullanılır. |
| net view /all | Ağdaki diğer bilgisayarları ve paylaşılan kaynakları listeler. |
| netstat -s | Ağ istatistiklerini gösterir. TCP, UDP, ICMP bağlantılarını ve diğer istatistikleri listeler. |
| ipconfig /release | Bilgisayarınızın IP adresini serbest bırakır ve bağlantıları sonlandırır. |
| ipconfig /renew | Bilgisayarınız için yeni bir IP adresi almak için DHCP sunucusuna talepte bulunur. |
| ipconfig /flushdns | DNS önbelleğini temizler, böylece DNS çözümlemelerini yeniden yapar. |
| netsh wlan show networks | Kablosuz ağların listesini gösterir. |
| netsh wlan show profiles | Kayıtlı kablosuz ağ profillerini gösterir. |
| netsh wlan show drivers | Kablosuz ağ sürücülerinin durumu ve özelliklerini gösterir. |
| telnet | Bir sunucu veya ağ cihazına bağlanmak için kullanılır. |
| netsh interface ip set dns | DNS sunucu adreslerini yapılandırmak için kullanılır. |


### Paket Kurulum Komutları

| Komut | Açıklama | 
| - | - |
| msiexec | MSI paketlerini kurmak için kullanılır. |
| choco | Chocolatey paket yöneticisi, birçok yazılımın komut satırından kolayca kurulmasını sağlar. |
| winget | Windows Package Manager, Windows 10'da Microsoft tarafından sağlanan resmi paket yöneticisidir. |
| npm | Node.js için paket yöneticisidir. JavaScript veya Node.js projeleri için paketleri kurmak için kullanılır. |
| pip | Python için paket yöneticisidir. Python projeleri için paketleri kurmak için kullanılır. |
| git | Git version kontrol sistemi, çeşitli projelerin yönetiminde kullanılır. Git'i kurmak için, resmi web sitesinden indirip kurabilirsiniz. |

### Arama Komutları

| Komut | Açıklama | 
| - | - |
| find | Belirli metinleri dosya içinde veya dizin listelerinde aramak için kullanılır. |
| findstr | Dizinlerde ve dosyalarda metinleri aramak için daha gelişmiş bir komuttur. |
| where | Belirli bir dizin altındaki dosyaları ve klasörleri filtrelemek için kullanılır. |
| tree | Dizin yapısını ağaç şeklide gösterir. | 
| wmic datafile where "name='C:\Path\to|file.txt'" get /value | Belirli bir dosyanın özelliklerini WMIC aracılığıyla almak için kullanılır. |
| more | Bir dosyanın içeriğini sayfa sayfa görüntülemek için kullanılır. |


### Disk Kullanımı Komutları

| Komut | Açıklama | 
| - | - |
| diskpart | Disk bölümleri oluşturmak, silmek ve yönetmek için kullanılır. |
| wmic logicaldisk get DeviceID, FileSystem, FreeSpace, Size | Sistemdeki sabit diskleri ve bunların dosya sistemi, boş alan ve toplam alan bilgilerini gösterir. |
| fsutil volume diskfree C: | Belirli bir sürücüdeki boş alan miktarını gösterir. |
| chkdsk | Diskte hataları tespit etmek ve düzeltmek için kullanılır. |
| defrag | Diski düzenlemek için kullanılır. |
| compact | Dosyaların sıkıştırılmasını sağlar. |

# Powershell Komutları

### Sistem Bilgisi Komutları

| Komut | Açıklama | 
| - | - | 
| Get-WmiObject | WMI sınıflarını kullanarak çeşitli sistem bilgilerini almak için kullanılır. |
| Get-CimInstance | Yine WMI sınıflarını kullanarak sistem bilgisi almak için kullanılır. Powershell 3.0 ve sonraki sürümlerde kullanılır. |
| Get-ComputerInfo | Sistem hakkında genel bilgiler almak için kullanılır. |
| Get-Process | Çalışan işlemler hakkında bilgi almak için kullanılır. |
| Get-Service | Çalışan servisler hakkında bilgi almak için kullanılır. |
| Get-Volume | Disk bölümleri hakkında bilgi almak için kullanılır. |
| Get-HotFix | Kurulu güncelleştirmeler hakkında bilgi almak için kullanılır. |
| Get-NetAdapter | Ağ adaptörleri hakkında bilgi almak için kullanılır. |
| Get-NetIPAddress | Ağ IP adresleri hakkında bilgi almak için kullanılır. |
| Get-NetTCPConnection | Açık TCP bağlantıları hakkında bilgi almak için kullanılır. |
| Get-WinEvent | Olay günlüğü bilgilerini almak için kullanılır. |
| Get-NetRoute | Ağ rotaları hakkında bilgi almak için kullanılır. |
| Get-LocalUser | Yerel kullanıcı hesapları hakkında bilgi almak için kullanılır. |
| Get-LocalGroup | Yerel gruplar hakkında bilgi almak için kullanılır. |
| Get-Disk | Disk sürücüleri ve diskler hakkında bilgi almak için kullanılır. |
| Get-Partition | Disk bölümleri hakkında bilgi almak için kullanılır. |
| Get-Service | Çalışan servislerin durumu hakkında ayrıntılı bilgi almak için kullanılır. |
| Get-Process | Çalışan işlemlerin daha ayrıntılı bilgilerini almak için kullanılır. |
| Get-Counter | Sistem performans sayacı verilerini almak için kullanılır. |
| Get-VolumeStatistics | Disk bölümü istatistiklerini almak için kullanılır. |
| Get-VM | Hyper-V sanal makineleri hakkında bilgi almak için kullanılır. |
| Get-WindowsFeature | Kurulu Windows özelliklerini almak için kullanılır. |
| Get-ScheduledTask | Zamanlanmış görevler hakkında bilgi almak için kullanılır. |
| Get-WinUserLanguageList | Kullanılabilir dil listesini almak için kullanılır. |

### Donanım Bilgisi Komutları

| Komut | Açıklama |
| - | - |
| Get-WmiObject | WMI sınıflarını kullanarak donanım bilgilerini almak için kullanılır. | 
| Get-CimInstance | Yine WMI sınıflarını kullanarak donanım bilgilerini almak için kullanılır. |
| Get-Win32DiskDrive | Disk sürücüleri hakkında bilgi almak için kullanılır. |
| Get-Win32LogicalDisk | Mantıksal diskler hakkında bilgi almak için kullanılır. |
| Get-Win32PhysicalMemory | Fiziksel bellek modülleri hakkında bilgi almak için kullanılır. |
| Get-Win32ComputerSystem | Bilgisayar sistemi hakkında bilgi almak için kullanılır. |
| Get-Win32Processor | İşlemci hakkında bilgi almak için kullanılır. |
| Get-Win32BIOS | BIOS hakkında bilgi almak için kullanılır. |
| Get-Win32BaseBoard | Anakart hakkında bilgi almak için kullanılır. |
| Get-Win32VideoController | Ekran kartı hakkında bilgi almak için kullanılır. |
| Get-Win32NetworkAdapter | Ağ adaptörleri hakkında bilgi almak için kullanılır. |
| Get-Win32PnPEntity | Sistemdeki tüm Plug and Play cihazları hakkında bilgi almak için kullanılır. |
| Get-Win32PhysicalMemoryArray | Bellek modülü dizisi hakkında bilgi almak için kullanılır. |
| Get-Win32ComputerSystemProduct | Bilgisayarın üretici ve modeli hakkında bilgi almak için kullanılır. |
| Get-Win32DiskPartition | Disk bölümü hakkında bilgi almak için kullanılır. |
| Get-Win32SystemEnclosure | Bilgisayar kasası hakkında bilgi almak için kullanılır. |
| Get-Win32SoundDevice | Ses aygıtları hakkında bilgi almak için kullanılır. |
| Get-Win32Keyboard | Klavye hakkında bilgi almak için kullanılır. |
| Get-Win32PointingDevice | Fare hakkında bilgi almak için kullanılır. |
| Get-Win32Printer | Kurulu yazıcılar hakkında bilgi almak için kullanılır. |
| Get-Win32PrinterDriver | Yazıcı sürücüleri hakkında bilgi almak için kullanılır. |
| Get-Win32PrinterPort | Yazıcı bağlantı noktaları hakkında bilgi almak için kullanılır. |
| Get-Win32SerialPort | Seri (COM) bağlantı noktaları hakkında bilgi almak için kullanılır. |
| Get-Win32USBController | USB denetleyicileri hakkında bilgi almak için kullanılır. |
| Get-Win32IDController | ID denetleyicileri hakkında bilgi almak için kullanılır. |
| Get-Win32Battery | Dizüstü bilgisayarlar ve tabletlerdeki pil hakkında bilgi almak için kullanılır. |
| Get-Win32DesktopMonitor | Monitörler hakkında bilgi almak için kullanılır. |
| Get-Win32CROMDrive | CD/DVD-ROM sürücüleri hakkında bilgi almak için kullanılır. |
| Get-Win32TapeDrive | Teyp sürücüleri hakkında bilgi almak için kullanılır. |

### Performans İzleme ve İstatistik Komutları

| Komut | Açıklama |
| - | - |
| Get-Counter | Performans sayaçlarını almak için kullanılır. |
| Get-Process | Çalışan işlemlerin performans istatistiklerini almak için kullanılır. |
| Get-CounterSet | Mevcut sayaç setlerini listelemek için kullanılır. |
| Get-CounterSample | Belirli bir performans sayacının örnek verilerini almak için kullanılır. |
| Get-WinEvent | Performans günlüğü verilerini almak için kullanılabilir. |
| Get-VMProcessor | Hyper-V sanal makinelerin işlemci istatistiklreini almak için kullanılır. |
| Get-NetTCPConnection | Açık TCP bağlantılarını almak için kullanılır. |
| Get-NetAdapterStatistics | Ağ adaptörü istatistiklerini almak için kullanılır. |

### Kullanıcı Bilgileri ve Yönetimi Komutları

| Komut | Açıklama |
| - | - |
| Get-LocalUser | Yerel kullanıcı hesaplarını listelemek için kullanılır. |
| Get-LocalGroup | Yerel grupları listelemek için kullanılır. |
| New-LocalUser | Yerel bir kullanıcı hesabı oluşturmak için kullanılır. |
| Add-LocalGroupMember | Bir kullanıcıyı veya bir gruptaki kullanıcıları yerel bir gruba eklemek için kullanılır. |
| Remove-LocalUser | Yerel bir kullanıcı hesabını silmek için kullanılır. |
| Set-LocalUser | Yerel bir kullanıcı hesabını düzenlemek için kullanılır. |
| Enable-LocalUser | Devre dışı bırakılmış bir yerel kullanıcıyı etkinleştirmek için kullanılır. |
| Disable-LocalUser | Bir yerel kullanıcıyı devre dışı bırakmak için kullanılır. |
| Rename-LocalUser | Yerel bir kullanıcının adını değiştirmek için kullanılır. |
| Get-ADUser | Etki alanındaki Active Directory (AD) kullanıcı hesaplarını listelemek ve yönetmek için kullanılır. |
| New-ADUser | Etki alanındaki yeni bir kullanıcı hesabı oluşturmak için kullanılır. |
| Set-ADUser | Etki alanındaki bir kullanıcı hesabını düzenlemek için kullanılır. |
| Enable-ADAccount | Etki alanındaki bir kullanıcı hesabını etkinleştirmek için kullanılır. |
| Disable-ADAccount | Etki alanındaki bir kullanıcı hesabını devre dışı bırakmak için kullanılır.| 
| Remove-ADUser | Etki alanındaki bir kullanıcı hesabını silmek için kullanılır. |
| Get-LocalGroupMember | Bir yerel grup içindei üyeleri listelemek için kullanılır. |
| Add-LocalGroupMember | Bir kullanıcıyı veya bir gruptaki kullanıcıları yerel bir gruba eklemek için kullanılır. |
| Remove-LocalGroupMember | Bir kullanıcıyı veya bir gruptan kullanıcıları kaldırmak için kullanılır. |
| Set-LocalGroup | Yerel bir grup üzerinde değişiklikler yapmak için kullanılır. |
| New-LocalGroup | Yerel bir grup oluşturmak için kullanılır. |
| Remove-LocalGroup | Yerel bir grup silmek için kullanılır. |
| Get-ADGroup | Etki alanındaki Active Directory gruplarını listelemek için kullanılır. |
| New-ADGroup | Etki alanında yeni bir grup oluşturmak için kullanılır. |
| Set-ADGroup | Etki alanındaki bir grubu düzenlemek için kullanılır. |
| Remove-ADGroup | Etki alanındaki bir grubu silmek için kullanılır. |
| Add-ADGroupMember | Etki alanındaki bir gruba üye eklemek için kullanılır. |
| Remove-ADGroupMember | Etki alanındaki bir gruptan üyeleri kaldırmak için kullanılır. |
| Set-ADUserPassword | Etki alanındaki bir kullanıcının şifresini değiştirmek için kullanılır. |
| Unlock-ADAccount | Etki alanındaki bir kullanıcının hesabının kilidini açmak için kullanılır. |
| Set-ADUser | Etki alanındaki bir kullanıcı hesabını düzenlemek için kullanılır. |

### Dosya ve Dizin Komutları

| Komut | Açıklama |
| - | - |
| Get-ChildItem | Geçerli dizindeki dosya ve dizinleri listelemek için kullanılır. |
| Get-Item | Belirli bir dosya veya dizinin ayrıntılı bilgilerini almak için kullanılır. |
| Get-Content | Dosyanın içeriğini okumak için kullanılır. |
| Set-Content | Dosyaya içerik yazmak veya mevcut içeriği değiştirmek için kullanılır. |
| Add-Content | Dosyaya yeni içerik eklemek için kullanılır. |
| New-Item | Yeni dosya veya dizin oluşturmak için kullanılır. |
| Remove-Item | Dosya veya dizini silmek için kullanılır. |
| Rename-Item | Dosya veya dizinin adını değiştirmek için kullanılır. |
| Copy-Item | Dosyayı veya dizini kopyalamak için kullanılır. |
| Move-Item | Dosyayı veya dizini taşımak veya yeniden adlandırmak için kullanılır. |
| Test-Path | Belirtilen dosya veya dizinin mevcut olup olmadığını kontrol etmek için kullanılır. |
| Resolve-Path | Göreli veya özel yolları çözümlemek için kullanılır. |
| Get-Acl | Dosya veya dizinin güvenlik izinlerini almak için kullanılır. |
| Set-Acl | Dosya veya dizinin güvenlik izinlerini ayarlamak için kullanılır. |
| Get-ItemPropertyValue | Bir dosya veya dizindeki özel bir özelliğin değerini almak için kullanılır. |
| Get-ItemProperty | Bir dosyanın veya dizinin özelliklerini almak için kullanılır. |
| Get-FileHash | Bir dosyanın karma değerini almak için kullanılır. |
| Select-String | Dosyalardaki metinleri aramak için kullanılır. |
| Get-FileMetaData | Dosyanın meta verilerini almak için kullanılır. |
| Get-Clipboard | Pano içeriğini almak için kullanılır. |
| Set-Clipboard | Pano içeriğini ayarlamak için kullanılır. |
| Compress-Archive | Dosyaları ve dizinleri sıkıştırmak için kullanılır. |
| Expand-Archive | Sıkıştırılmış dosyaları açmak için kullanılır. |
| Test-FileCatalog | Dosya ve klasörlerin bütünlüğünü doğrulamak için kullanılır. |
| Get-PSDrive | Sürücü bilgilerini almak için kullanılır. |
| New-PSDrive | Yeni bir PowerShell sürücüsü oluşturmak için kullanılır. |
| Remove-PSDrive | PowerShell sürücüsünü kaldırmak için kullanılır. |
| Get-Volume | Sabit disk bölümleri ve bu bölümlerle ilgili bilgileri almak için kullanılır. |

### Ağ Komutları

| Komut | Açıklama |
| - | - |
| Test-Connection | Bir IP adresine veya bir bilgisayara ping atarak bağlantı durumunu test etmek için kullanılır. |
| Test-NetConnection | Bir IP adresine veya bir bilgisayara ping atarak ve belirli portlara bağlantı deneyerek ağ bağlantısını test etmek için kullanılır. |
| Get-NetIPConfiguration | Ağ bağlantıları ve IP yapılandırması hakkında bilgi almak için kullanılır. |
| Get-NetAdapter | Ağ adaptörleri (NIC) hakkında bilgi almak için kullanılır. |
| Get-NetRoute | Routing tablosu hakkında bilgi almak için kullanılır. |
| Get-NetTCPConnection | Açık TCP bağlantılarını listelemek için kullanılır. |
| Get-NetUDPEndpoint | Açık UDP bağlantılarını listelemek için kullanılır. |
| Get-NetFirewallProfile | Windows Güvenlik Duvarı profillerini ve ayarlarını almak için kullanılır. |
| Get-DnsClientServerAddress | DNS sunucu adreslerini almak için kullanılır. |
| Resolve-DnsName | DNS ad çözümleme işlemleri yapmak için kullanılır. |
| Test-Port | Belirli bir IP adresi ve port numarasına bağlantı denemek için kullanılır. |
| Get-NetNeighbor | IP adresi ve fiziksel adres arasındaki eşlemeleri (ARP tablosu) almak için kullanılır. |
| Get-NetAdapterStatistics | Ağ adaptörü istatistiklerini almak için kullanılır. |
| Get-NetIPAddress | Ağdaki IP adresleri ve yapılandırmaları hakkında bilgi almak için kullanılır. |
| New-NetRoute | Yeni bir ağ rotası eklemek için kullanılır. |
| Get-NetAdapterBinding | Bir ağ adaptörünün bağlama (binding) durumunu ve ayarlarını almak için kullanılır. | 
| Set-NetAdapterBinding | Bir ağ adaptörünün bağlama (binding) durumunu etkinleştirmek veya devre dışı bırakmak için kullanılır. |
| Get-NetAdapterHardwareInfo | Ağ adaptörünün donanım bilgilerini almak için kullanılır. |
| Get-NetAdapterRss | Ağ adaptöründeki Receive Side Scaling (RSS) ayarlarını almak için kullanılır. |
| Get-NetAdapterSriov | Ağ adaptöründeki Single-Root I/O Virtualization (SR-IOV) ayarlarını almak için kullanılır. |
| Get-NetAdapterVmq | Ağ adaptöründeki Virtual Machine Queue (VMQ) ayarlarını almak için kullanılır. |
| Get-NetAdapterAdvancedProperty | Ağ adaptöründeki gelişmiş özelliklerin ayarlarını almak için kullanılır. |
| Enable-NetAdapter | Bir ağ adaptörünü etkinleştirmek için kullanılır. |
| Disable-NetAdapter | Bir ağ adaptörünü devre dışı bırakmak için kullanılır. |
| Restart-NetAdapter | Bir ağ adaptörünü yeniden başlatmak için kullanılır. |
| Set-NetAdapter | Ağ adaptörünün ayarlarını düzenlemek için kullanılır. |
| Set-DnsClientServerAddress | Bir bilgisayarın DNS sunucu ayarlarını değiştirmek için kullanılır. |
| Add-DnsClientServerAddress | Bir bilgisayara yeni DNS sunucu adresleri eklemek için kullanılır. |

### Dizin Kullanımı Komutları

| Komut | Açıklama |
| - | - |
| Get-PSDrive | Mevcut sürücüleri listelemek için kullanılır. |
| Get-Volume | Sabit disk bölümleri ve bu bölümlerle ilgili bilgileri almak için kullanılır. |
| Get-Partition | Disk bölümlerini almak için kullanılır. |
| Get-PhysicalDisk | Fiziksel disklerin bilgilerini almak için kullanılır. |
| Get-VolumeStatistics | Disk bölümleri hakkında istatistiksel bilgileri almak için kullanılır. |
| Get-DiskUsage | Belirli bir dizindeki dosya ve klasörlerin disk kullanımını görmek için kullanılır. |

