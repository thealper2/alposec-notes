# Sistem Bilgisi Komutları

| Komut | Açıklama |
| ------- | ---------- |
| uname -a | Sistem bilgilerini görüntüler |
| uname -r | Çekirdek sürüm bilgilerini görüntüler |
| uptime | Sistemin ne kadar süredir çalıştığını gösterir |
| hostname | Bilgisayarın ağ üzerindeki adını görüntüler. |
| hostname -I | Bilgisayarın ağdaki IP adresini görüntüler |
| last reboot | Sistemin yeniden başlatma geçmişini gösterir |
| date | Tarih ve saati gösterir | 
| cal | Takvimi gösterir |
| w | Kimin çevrimiçi olduğunu gösterir | 
| whoami | Kimin giriş yaptığını gösterir |
| lsb_release -a | Dağıtım bilgilerini gösterir. |
| cat /etc/os-release | İşletim sistemi sürümü hakkında ayrıntılı bilgi sağlar. |


# Donanım Bilgisi Komutları

| Komut | Açıklama |
| - | - |
| dmesg | Çekirdek arabelleğindeki mesajları görüntüler |
| cat /proc/cpuinfo | CPU Bilgilerini görüntüler |
| cat /proc/meminfo | Bellek bilgilerini görüntüler |
| free -h | Toplam, boş ve kullanılan belleği görüntüler |
| lspci | PCI aygıtları gösterir |
| lsusb | USB aygıtları gösterir |
| dmidecode | DMI verilerini görüntüler. Bilgisayar donanımı hakkında bilgileri çıkartır ve BIOS tarafından sağlanan DMI tablolarını görüntüler. |
| hdparm -i | Belirtilen disk hakkındaki bilgileri gösterir |
| hdparm -tT | Belirtilen disk üzerinde bir okuma hızı testi yapar |
| badblocks -s | Belirtilen diskte okunamayan blokları test eder |
| lscpu | İşlemci hakkında ayrıntılı bilgi sağlar. |
| lsblk | Blok cihazları (diskler, bölümler) hakkında bilgi sağlar. |
| lshw | Sistem donanımı hakkında ayrıntılı bilgi sağlar. |
| ifconfig <br/> ip | Ağ arayüzlerinin (Ethernet, Wi-Fi vb.) yapılandırma bilgilerini gösterir| 
| netstat | Ağ bağlantılarını, bağlantı noktalarını ve ağ istatistiklerini gösterir. |
| iwconfig | Kablosuz ağ arayüzlerinin yapılandırma bilgilerini gösterir. |
| lsof | Açık dosya ve ağ bağlantılarını gösterir |
| du | Belirli bir dizinin disk kullanımını gösterir. |
| journalctl | Sistem günlüğü (log) dosyalarını görüntüler. |
| dmesg | Başlatma (boot) mesajlarını ve sistem günlüğünü gösterir. |
| os-prober | Sistem üzerindeki disklerdeki işletim sistemlerini tanımlar. |
| update-grub | GRUB önyüklecisini günceller. |



# Performans İzleme ve İstatistik Komutları

| Komut | Açıklama | 
| - | - |
| top | En önemli süreçleri görüntüler ve yönetir |
| htop | Etkileşimli süreç görüntüleyici  |
| mpstat 1 | İşlemci ile ilgili istatistikleri görüntüler |
| vmstat 1 | Sanal bellek istatistiklerini görüntüler |
| iostat 1 | I/O istatistiklerini görüntüler |
| tcpdump -i | Belirtilen arabirimindeki tüm paketleri yakalar ve görüntüler |
| lsof | Sistemdeki tüm açık dosyaları listeler |
| watch | Parametre olarak verilen komutu çalıştırarak izler. |
| free | Sistem belleği hakkında bilgi verir. |
| vmstat | Sanal bellek, işlemci, disk, ağ ve diğer sistem kaynakları hakkında ayrıntılı istatistikler sağlar. |
| sar | Sistem performansıyla ilgili geniş bir yelpazede istatistikler sağlar. CPU kullanımı, bellek kullanımı, ağ trafiği, I/O istatistikleri ve daha fazlasını içerir. |
| nmon | Sistem kaynaklarını (CPU, bellek, disk, ağ vb.) gerçek zamanlı olarak izler ve istatistikleri gösterir. |
| iotop | Disk giriş/çıkış etkinliğini izler ve süreç bazında I/O istatistikleri sağlar. |
| iftop | Ağ trafiğini gerçek zamanlı olarak izler. İnternet bağlantı noktaları, bağlantı hızları, bant genişliği kullanımı gibi bilgileri gösterir. |
| dstat | Sistem kaynakları, I/O istatistikleri, ağ trafiği, sistem yükü ve diğer performans verileri gibi çeşitli istatistikleri gerçek zamanlı olarak gösterir. |
| atop | Sistem kaynakları ve süreçler hakkında ayrıntılı istatistikler sağlar. CPU, bellek, disk, ağ ve diğer kaynakları izleyebilir ve süreçlerin davranışını analiz edebilirsiniz. |
| pidstat | Belirli bir sürecin CPU kullanımı, bellek kullanımı, I/O istatistikleri ve diğer performans bilgileri gibi süreç bazında istatistikler sağlar. |
| mpstat | Çoklu işlemcili sistemlerde CPU istatistiklerini gösterir. Her bir CPU çekirdeğinin yükünü, kullanımını ve diğer ölçümleri sağlar. |
| slabtop | Sistem belleği kullanımını ve çekirdek önbellek (kernel slab) istatistiklerini gösterir. Önbellek yönetimi ve bellek tüketimi hakkında bilgi sağlar. |
| tcpdump <br/> tshark | Ağ trafiğini yakalar ve paketleri analiz eder. Ağ sorunlarını teşhis etmek ve ağ trafiğini incelemek için kullanılır. |
| nethogs | Ağ trafiğini süreç bazında izler. Hangi süreçlerin ne kadar ağ bant genişliği kullandığını gösterir. |
| ifstat | Ağ arayüzlerinin gelen ve giden trafiğini gerçek zamanlı olarak izler. Bant genişliği kullanımını ve ağ aktivitesini gösterir. |

# Kullanıcı Bilgileri ve Yönetimi Komutları

| Komut | Açıklama |
| - | - |
| id | Mevcut oturumun kullanıcı ve grup kimliklerini görüntüler |
| last | Sisteme en son giriş yapan kullanıcıları görüntüler |
| who | Sisteme kimin giriş yaptığını gösterir |
| groupadd | Grup oluşturur. |
| useradd -c "description" -m user | Belirtilen açıklamayla belirtilen isimde bir hesap ve kullanıcı luşturur. |
| userdel | Hesap siler |
| usermod -aG groupname user | Kullanıcı hesabını belirtilen gruba ekler |
| whoami | Mevcut kullanıcı oturumu gösterir. | 
| passwd | Kullanıcının parolasını değiştirmek için kullanılır. |
| groupdel | Bir grup hesabını siler. |
| groups | Kullanıcının ait olduğu grupları gösterir. |
| chown | Dosya veya dizinin grubunu değiştirmek için kullanılır. |
| chgrp | Dosya veya dizinin grubunu değiştirmek için kullanılır. |
| su | Kullanıcı oturumunu değiştirmek için kullanılır. |
| sudo | Root (kök) kullanıcının yetkilerini başka bir kullanıcıya geçici olarak vermek için kullanılır. |
| finger | Kullanıcı hakkında ayrıntılı bilgiler sağlar. |
| chage | Kullanıcının parola değişiklik politikalarını yönetir. |
| visudo | /etc/sudoers dosyasını düzenlemek için kullanılır. Bu dosya, sudo yetkilerini ve yapılandırmalarını yönetir. |
| chfn | Kullanıcının parola dışı bilgilerini (tam ad, ofis numarası vb.) değiştirmek için kullanılır. |
| pwck | /etc/passwd dosyasındaki kullanıcı hesaplarını doğrular ve hataları kontrol eder. |
| grpck | /etc/group dosyasındaki grup hesaplarını doğrular ve hataları kontrol eder. |
| newgrp | Geçerli oturumu belirli bir gruba değiştirmek için kullanılır. |
| pwgen | Rastgele parolalar oluşturmak için kullanılır. |
| chsh | Kullanıcının kabuk (shell) ayarlarını değiştirmek için kullanılır. |
| pwconv <br/> grpconv | Shadow dosyalarını etkinleştirmek ve /etc/passwd ve /etc/group dosyalarını güncellemek için kullanılır. |

# Dosya ve Dizin Komutları

| Komut | Açıklama |
| - | - |
| ls | Mevcut dizindeki dosyaları gösterir |
| pwd | Mevcut çalışma dizinini gösterir |
| mkdir directory | Bir dizin oluşturur |
| rm file | Dosya silme |
| cp file1 file2 | file1'i file2'ye kopyalar |
| mv file1 file2 | file1'i file2'ye yeniden adlandırır veya taşır |
| ln -s /path/to/file linkname | Linkname için sembolik link oluşturur |
| touch file | Boş bir dosya oluşturur veya dosyanın erişim ve değişiklik zamanlarını günceller |
| cat file | Dosyanın içeriğini görüntüler |
| less file | Bir metin dosyasına göz atar | 
| head file | Dosyanın ilk 10 satırını gösterir |
| tail file | Dosyanın son 10 satırını gösterir |
| ps | Şu anda çalışan işlemleri görüntüler |
| kill pid | Belirtilen PID'e ait işlemi sonlandırır |
| killall processname | Belirtilen işlem ismine ait tüm işlemleri sonlandırır |
| komut & | Belirtilen komutu arka planda çalıştırır | 
| bg | Durdurulan veya arka plandaki işlemleri gösterir |
| fg | En son arka plandaki işlemi ön plana çıkarır | 
| more file | Boyutu büyük olan bir dosyayı sayfalar halinde okumaya yarar. |
| ln | Dosya veya dizinlere bağlantı (link) oluşturur. Sembolik link (symbolic link) veya sert bağlantı (hard link) oluşturmak için kullanılır. |
| file filename | Dosyanın türünü belirler. |
| stat | Dosya veya dizinin ayrıntılı istatistiklerini gösterir. Dosyanın boyutu, oluşturulma tarihi, değiştirme tarihi vb. gibi bilgileri sağlar. |
| cpio | Dosyaları arşivlemek veya arşivden çıkarmak için kullanılır. |
| tar | Dosyaları bir arşiv dosyasına paketlemek veya arşivden çıkarmak için kullanılır. |
| gzip <br/> gunzip | Dosyaları sıkıştırmak veya sıkıştırmadan çıkarmak için kullanılır. |
| zip <br/> unzip | Dosyaları zip formatında arşivlemek ve arşivden çıkarmak için kullanılır. |
| md5sum | Dosyanın MD5 özetini hesaplar. |
| sha1sum | Dosyanın SHA1 özetini hesaplar. |
| sha256sum | Dosyanın SHA256 özetini hesaplar. |
| diff | İki dosya arasındaki farkları gösterir. |
| chattr <br/> lsattr | Dosyaların veya dizinlerin değiştirilmezlik (immutable) veya diğer özel özelliklerini ayarlamak ve görünlemek için kullanılır. |


# Dosya İzin Komutları

- Execute : Çalıştırma
- Write: Yazma
- Read: Okuma

- User: Kullanıcı
- Group: Grup
- Other: Diğerleri
- All: Hepsi

| U | G | W | komut |
| - | - | - | - |
| rwx | rwx | rwx | chmod 777 filename |
| rwx | rwx | r-x | chmod 775 filename |
| rwx | r-x | r-x | chmod 755 filename |
| rw- | rw- | r-- | chmod 664 filename |
| rw- | r-- | r-- | chmod 644 filename |

# Ağ Komutları

| Komut | Açıklama |
| - | - |
| ifconfig | Tüm ağ arayüzlerinin ayrıntılı bilgilerini gösterir. |
| ethtool eth0 | Ağ sürücüsü ve donanım ayarlarını sorgular veya kontrol eder | 
| ping | Belirtilen bilgisayara ICMP isteği gönderir |
| whois domain | Belirtilen alan adına ait whois bilgilerini gösterir |
| dig domain | Belirtilen alan adına ait DNS bilgilerini gösterir |
| dig -x IP | IP adresine karşılık gelen alan adını bulur |
| wget URL | URL adresindeki dosyayı indirir | 
| netstat -tulpn | TCP ve UDP bağlantı noktalarını ve kullanan programları görüntüler |

# Paket Kurulum Komutları

| Komut | Açıklama |
| - | - | 
| apt search packagename | Paket araması yapar. |
| apt install package | Paketi kurar |
| apt info package | Paketle ilgili açıklama ve özet bilgileri görüntüler |
| dpkg -i package.deb | Paketi package.deb adlı yerel dosyadan yükler |
| tar zxvf sourcecode.tar.gz <br/> cd source code <br/> ./configure <br/> make <br/>  make install | Yazılımı kaynak koddan yükler |
| apt remove package| Paketi kaldırır. |
| apt-get update | Paket güncellemelerini alır. |
| apt-get upgrade | Alınan güncellemeleri kullanarak paketleri günceller. |

# Arama Komutları

| Komut | Açıklama |
| - | - |
| grep pattern file | Dosya içinde eşleşme arar |
| locate name | Dosya ve dizinleri ada göre bulur |
| find | Arama komutu |
| whereis | İlgili bir dosyanın yeri, kaynak dosyaları ve man sayfası gibi bilgileri gösterir. |
| which | Belirli bir komutun tam yolunu gösterir. |
| ack | Gelişmiş bir metin arama aracıdır. Dosyalar arasında hızlı ve kolay bir şekilde metin araması yapmanızı sağlar. Ayrıca, belirli dosya türlerini veya dizinleri filtrelemek için kullanılabilir. | 
| ag | Bir başka hızlı ve kolay metin arama aracıdır. Çok hızlı ve esnek bir şekilde büyük projelerde metin araması yapmanızı sağlar. |

# SSH Bağlantısı

| Komut | Açıklama |
| - | - |
| ssh host | Yerel kullanıcı adı ile sunucuya bağlanır |
| ssh user@host | User olarak sunucuya bağlanır |
| ssh -p port user@host | Belirtilen portu kullanarak sunucuya bağlanır | 
| ssh-keygen | SSH anahtarı oluşturmaya yarar. |
| ssh-copy-id | SSH anahtarını uzak sunucuya kopyalamak için kullanılır. |
| sftp | Dosya aktarımlarını güvenli bir şekilde gerçekleştirmek için kullanılır. |
| ssh-agent | SSH anahtarlarını yönetmek için kullanılır. Anahtarların oturum süresi boyunca bellekte tutulmasını ve parola girişi gerektiğinde kullanıcıya hatırlatma yapmasını sağlar. |
| ssh-add | SSH anahtarlarını ssh-agent'a eklemek için kullanılır. |
| sshfs | Uzak bir sunucunun dosya sistemini yerel bir dizine bağlamak için kullanılır. |
| cat ~/.ssh/id_rsa | Bu dosya, SSH istemcisi tarafından kullanılan özel anahtar dosyasıdır. Anahtar tabanlı kimlik doğrulama için istemcinin özel anahtarını temsil eder. Bu dosyanın güvenli bir şekilde korunması ve erişilebilirliğinin sınırlı olması önemlidir. |
| cat ~/.ssh/id_rsa.pub | Bu dosya, SSH istemcisi tarafından kullanılan genel anahtar dosyasıdır. İstemcinin genel anahtarını temsil eder. Genel anahtar, istemciden sunucuya gönderilir ve sunucuda bulunan 'authorized_keys' dosyasıyla eşleştirilir. |
| cat ~/.ssh/authorized_keys | Bu dosya, SSH sunucusu tarafından kullanılan bir dosyadır. Sunucunun kabul ettiği SSH istemci anahtarlarını içerir. İstemci, genel anahtarını sunucuya gönderdikten sonra sunucu bu dosyayı kontrol eder ve uyumlu bir anahtar varsa oturumu kabul eder. |


# Dosya Transferi Komutları

| Komut | Açıklama |
| - | - |
| scp file.txt server:/tmp | file.txt dosyasını sunucudaki /tmp klasörüne güvenli bir şekilde kopyalar. |
| scp server:/var/www/\*.html /tmp | \*.html dosyalarını sunucudan yerel /tmp klasörüne kopyalar |
| scp -r server:/var/www /tmp | Tüm dosya ve dizinleri yinelemeli olarak kopyalar |
| rsync -a /home /backups | Dosyaları /home ile /backups/home arasında senkronize eder |
| rsync -avz /home server:/backups | Dosyaları/dizinleri, sıkıştırma etkinken yerel ve uzak sistem arasında senkronize eder. |
| wget | Bir URL'den dosyaları indirmek için kullanılır. |
| curl | Bir URL'den dosyaları indirmek veya veri göndermek için kullanılır. |
| ftp | FTP sunucusuna bağanmak ve dosyaları indirmek veya yüklemek için kullanılır. |

# Disk Kullanımı Komutları

| Komut | Açıklama | 
| - | - |
| df -h | Bağlı dosya sistemlerinde boş ve kullanılmış alanı gösterir |
| fdisk -l | Disk bölümlerinin boyutlarını ve türlerini görüntüler |
| du -ah | Tüm dosyalar ve dizinler için disk kullanımını görüntüler |
| du -sh | Mevcut dizindeki toplam disk kullanımını gösterir |
| parted | Disk bölümleme işlemleri için kullanılır. |
| gdisk | GPT (GUID Partition Table) disk bölümleme işlemleri için kullanılır. |

# Dizinlerde Gezinme Komutları

| Komut | Açıklama |
| - | - |
| cd .. | Bir üst dizine çıkmak için kullanılır |
| cd | $HOME dizinine gider |
| cd /opt | /opt dizinine geçer |

