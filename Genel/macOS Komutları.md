
# Sistem Bilgisi Komutları

| Komut | Açıklama |
| - | - |
| system_profiler | Sistem profilini geniş bir şekilde gösteren komuttur. Sistem donanımı, yazılımı, ağ ayarları ve daha fazlası hakkında bilgiler sunar. |
| sw_vers | Sistem sürümü hakkında bilgi verir. |
| sysctl | Sistem ayarlarını gösterir ve değiştirmenizi sağlar. |
| sysctl -n machdep.cpu.brand_string | İşlemci modeli hakkında bilgi verir. |
| diskutil list | Sistemde bağlı diskleri ve bölümleri listeleyen komuttur. |
| df | Disk kullanımını gösterir ve boş alan miktarını verir. |
| top | Sistemdeki işlemci ve bellek kullanımını gerçek zamanlı olarak gösterir. |
| ioreg | I/O Kit verilerini gösterir ve donanım aygıtları hakkında bilgi sağlar. |
| networksetup -listallhardwareports | Ağ bağdaştırıcıları ve ağ portları hakkında bilgi verir. |
| ioreg -l -p IODeviceTree \| grep firmware-abi | Firmware (BIOS/EFI) mimarisi hakkında bilgi verir. |
| nvram | NVRAM ayarları hakkında bilgi verir. |
| system_profiler SPHardwareDataType | Sistem donanımı hakkında daha detaylı bilgi sağlar. |
| system_profiler SPSoftwareDataType | Yazılım bilgilerini gösterir, yüklü macOS sürümü, güvenlik güncelleştirmeleri ve diğer yazılım bileşenleri hakkında bilgi verir. |
| system_profiler SPNetworkDataType | Ağ bağdaştırıcıları, IP adresleri, ağ bağlantıları ve diğer ağ bilgileri hakkında detaylı bilgiler verir. |
| system_profiler SPSerialATADataType | Sistemdeki SATA cihazları ve bağla diskler hakkında bilgi verir. |
| system_profiler SPUSBDataType | USB cihazları hakkında bilgi verir. |
| system_profiler SPPowerDataType | Güö yönetimi hakkında bilgi verir, batarya durumu, şarj seviyesi ve güç tüketimi gibi bilgileri sağlar. | 
| system_profiler SPBluetoothDataType | Bluetooth bağdaştırıcıları ve bağlı cihazlar hakkında bilgi verir. |
| system_profiler SPFireWireDataType | FireWire bağdaştırıcıları ve bağlı cihazlar hakkında bilgi verir. | 
| system_profiler SPDisplaysDataType | Bağlı ekranlar ve grafik kartları hakkında bilgi verir. |
| system_profiler SPExtensionsDataType | Yüklü kernel uzantıları hakkında bilgi sağlar. |
| ioreg -l | I/O Kit ağacındaki tüm cihazları listeleyen komuttur. |
| networksetup -listallnetworkservices | Tüm ağ hizmetlerini listeleyen komuttur. |

# Donanım Bilgisi Komutları

| Komut | Açıklama |
| - | - |
| system_profiler SPUSBDataType | USB cihazları hakkında bilgi almak için kullanılır. |
| system_profiler SPSerialATADataType | SATA cihazları ve bağlı diskler hakkında bilgi almak için kullanılır. |
| system_profiler SPBluetoothDataType | Bluetooth bağdaştırıcıları ve bağlı cihazlar hakkında bilgi almak için kullanılır. |
| system_proıfiler SPCardReaderDataType | Kart okuyucular ve bağlı kartlar hakkında bilgi almak için kullanılır. |
| system_profiler SPDisplaysDataType | Bağlı ekran ve grafik kartları hakkında bilgi almak için kullanılır. |
| system_profiler SPAudioDataType | Ses cihazları ve bağlı ses aygıtları hakkında bilgi almak için kullanılır. |
| system_profiler SPMemoryDataType | Bellek hakkında bilgi almak için kullanılır. |
| system_profiler SPPowerDataType | Güç yönetimi ve batarya hakkında bilgi almak için kullanılır. |
| system_profiler SPNetworkDataType | Ağ bağdaştırıcıları, IP adresleri ve diğer ağ bilgileri hakkında bilgi almak için kullanılır. |
| system_profiler SPThunderboltDataType | Thunderbolt bağdaştırıcıları ve bağlı cihazlar hakkında bilgi almak için kullanılır. |

# Performans İzleme ve İstatistik Komutları

| Komut | Açıklama | 
| - | - |
| nettop | Ağ trafiğini gerçek zamanlı izlemenizi sağlar. |
| sar | Sistem aktivitesi raporları sağlar. | 
| purge | RAM belleği temizlemek için kullanılır. |

# Kullanıcı Bilgileri ve Yönetimi Komutları

| Komut | Açıklama | 
| - | - |
| dscl . -list /Users | Sistemdeki tüm kullanıcıları listeler. |
| dscl . -read /Users/username | Belirtilen kullanıcının bilgilerini gösterir. |
| dscacheutil -q user | Önbellekteki kullanıcı bilgilerini gösterir. |
| sudo dscl . -create /Users/newuser | Yeni bir kullanıcı oluşturur. |
| sudo dscl . -delete /Users/username | Kullanıcıyı siler.|
| sudo dseditgroup -o edit -a username -t user groupname | Belirtilen kullanıcıyı belirtilen gruba ekler. |
| sudo dseditgroup -o edit -d username -t user groupname | Belirtilen kullanıcıyı belirtilen gruptan çıkarır. |
| dscacheutil -q group | Sistemdeki tüm grupları listeler. |
| dscl . -read /Groups/groupname | Belirtilen grup hakkında bilgi sağlar. |
| dscacheutil -flushcache | Kullanıcı ve grup önbelleğini temizler. |
| dseditgroup -o checkmember -m username groupname | Belirtilen kullanıcının belirtilen grupta olup olmadığını kontrol eder. |
| dseditgroup -o checkmember -n . username | Belirtilen kullanıcının hangi gruplarda bulunduğunu gösterir. |
| dsmemberutil checkmembership -U username -G groupname | Belirtilen kullanıcının belirtilen grupta olup olmadığını kontrol eder. |
| sudo sysadminctl -addUsers username -password PASSWORD -home /Users/username -admin | Belirtilen kullanıcı adında yeni bir yönetici kullanıcı oluşturur ve parola atar. |


# Ağ Komutları

| Komut | Açıklama | 
| - | - |
| dns-sd | DNS hizmeti keşfetmek ve hizmetleri listelemek için kullanılır. |
| networksetup -listallnetworkservices | Sistemdeki tüm ağ bağdaştırıcılarını ve ağ hizmetlerini listeler. |
| networksetup -getinfo "name" | Belirtilen bir ağ bağdaştırıcısının yapılandırma bilgilerini gösterir. |
| networksetup -setairportpower Wi-Fi on\|off | Wifi bağlantısını açmak veya kapatmak için kullanılır. |
| arp -a | ARP önbelliğini gösterir. IP adresleri ve MAC adresleri arasındaki çözümlenmiş bağlantıları listeler. |
| networksetup -getinfo Ethernet | Ethernet bağdaştırıcısının yapılandırma bilgilerini gösterir. |
| networksetup -setdhcp "name" | DHCP ile belirtilen bir ağ bağdaştırıcısının yapılandırmasını ayarlar. |
| networksetup -setmanual "name", IP_ADDR SUBNET_MASK Router | Belirtilen bir ağ bağdaştırıcısının IP adresini, alt ağı maskesini ve ağ geçidini manuel olarak ayarlar. |
| networksetup -setdnsservers "name" DNS1 DNS2 | Belirtilen bir ağ bağdaştırıcısının DNS sunucu ayarlarını manuel olarak ayarlar. |
| networksetup -setsocksfirewallproxy "name" IP_ADDR Port | Belirtilen bir ağ bağdaştırıcısının SOCKS proxy'sini ayarlar. |
| scutil --dns | Sistemde DNS yapılandırma bilgilerini gösterir. |
| traceroute6 | Belirtilen bir IPv6 adresine doğru rota oluşturur. |


# Paket Kurulum Komutları

| Komut | Açıklama | 
| - | - |
| brew search packagename | Homebrew ile paket araması yapmak için kullanılır. | 
| brew install packagename | Homebrew ile paket yüklemek için kullanılır. |
| brew update | Homebrew ile güncellemeleri almak için kullanılır. |
| brew upgrade | Homebrew ile tüm paketleri güncellemek için kullanılır. |
| brew uninstall packagename | Homebrew ile paket kaldırmak için kullanılır. |
