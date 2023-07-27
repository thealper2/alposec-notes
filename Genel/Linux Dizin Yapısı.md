Linux işletim sistemi, dosya sistemi için hiyerarşik bir dizin yapısı kullanır. Bu yapı, tüm dosya ve dizinlerin kök dizini altında düzenlenmesini sağlar. Linux'un dizin yapısı, Filesystem Hierarchy Standard (FHS) adı verilen bir standartla belirlenmiştir. 

| Dizin | Açıklama |
| - | - |
| / (Kök dizin - root directory) | Linux işletim sistemindeki en üst düzey dizindir ve tüm diğer dizinler buradan başlar. "/" işareti kök dizini ifade eder. |
| /bin | Temel sistem komutlarının (binary) bulunduğu dizindir. Önyükleme (boot) ve sistem bakımı için gerekli önemli komutlar burada bulunur. |
| /boot | İşletim sisteminin önyükleme dosyalarının (bootloader) ve çekirdek (kernel) dosyalarının bulunduğu dizindir. |
| /dev | Cihaz dosyalarının bulunduğu dizindir. Donanım ve diğer cihazlar, bu dizin altında özel dosya olarak temsil edilir. |
| /etc | Sistem yapılandırma dosyalarının bulunduğu dizindir. Ağ yapılandırması, sistem hizmetleri, kullanıcıların hesap bilgileri gibi sistem ayarları burada bulunur. |
| /home | Kullanıcıların ev dizinleri bulunur. Her kullanıcı için ayrı bir dizin oluşturulur ve kullanıcılar kendi ev dizinlerinde çalışabilirler. |
| /lib <br/> /lib64 | Sistem kütüphanelerinin bulunduğu dizindir. |
| /media | Taşınabilir cihazların otomatik olarak bağlandığı yerdir. |
| /mnt | Kullanıcının elle monte ettiği geçici dosya sistemlerinin bağlandığı yerdir. |
| /opt | Üçüncü taraf uygulamalarının ve paketlerinin yüklendiği yerdir. |
| /proc | Sanal dosya sistemidir ve işletim sisteminin çalışan süreçleri ve sistem bilgilerini içerir. | 
| /root | Root kullanıcısının ev dizinidir. |
| /sbin | Sistem yöneticisi komutlarının bulunduğu dizindir. Root kullanıcısı tarafından kullanılır. |
| /tmp | Geçici dosyaların saklandığı dizindir. |
| /usr | Çoğu kullanıcı uygulamasının ve verilerinin bulunduğu dizindir. |
| /var | Değişken verilerin saklandığı dizindir. |

