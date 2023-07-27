# Port States (Port Durumları)

- **OPEN (AÇIK)**
Eğer bir port "OPEN" olarak etiketlenmişse, bu hedef sistemdeki o portun dinleme modunda olduğu anlamına gelir. Yani, bu port üzerinden bir servis ya da uygulama çalışıyor ve dış dünyadan gelen bağlantıları kabul edebilir. "OPEN" portlar, saldırganların bu servislere erişmeye çalışabileceği anlamına gelir ve güvenlik açısından dikkat edilmesi gerekir. 

- **FILTERED (FİLTRELİ)**
Eğer bir port "FILTERED" olarak etiketlenmişse, bu portun erişilebilirlik durumunun belirsiz olduğu anlamına gelir. Bu durum genellikle bir güvenlik duvarı (firewall) ya da ağ cihazları tarafından engellenen portlar için kullanılır. Bu portlar nmap tarafından erişilemeyen ve durumu net olarak tespit edilemeyen portlardır.

- **UNFILTERED (FİLTRESİZ)**
Eğer bir port "UNFILTERED" olarak etiketlenmişse, bu portun nmap tarafından tarama yapılırken erişilebildiği ancak açık olmadığı durumu ifade eder. Yani, portun hedef sisteminde açık bir servis çalışmıyor, ancak ağ cihazları tarafından engellenmiyor da.

- **OPEN/FILTERED (AÇIK/FİLTRELİ)**
Eğer bir port "OPEN/FILTERED" olarak etiketlenmişse, bu portun ya açık olduğunu ve bağlantıları kabul ettiğini ya da filtrelenmiş olduğunu, yani güvenlik duvarı tarafından engellendiğini gösterir. Tam durum belirsizliği olduğu için hem "OPEN" hem de "FILTERED" durumları birlikte gösterilir.

- **CLOSED/FILTERED (KAPALI/FİLTRELİ)**
Eğer bir port "CLOSED/FILTERED" olarak etiketlenmişse, bu portun hem kapalı olduğunu hem de filtrelenmiş olduğunu gösterir. Yani hedef sistemdeki port kapalıdır ve ağ cihazları tarafından erişilemez hale getirilmiştir.

---

# Tarama Türleri

### TCP SYN Scan

TCP SYN taraması, nmap'ın hedef sistemdeki portların durumunu belirlemek için TCP/IP üçlü el sıkışma (three-way handshake) işlemini kullanmasına dayanır. Bu işlem, istemcinin ve sunucunun biribirleriyle bağlantı kurmak için üç adımda (SYN, SYN-ACK, ACK) iletişim kurmasını içerir. Ancak, nmap SYN taramasında el sıkışma işlemini tamamlamaz ve yalnızca ilk iki adımı gerçekleştirir.

1. Birinci Adım (SYN): Nmap, hedef sistemdeki belirli bir portu hedefleyerek TCP paketi gönderir ve SYN bayrağını (flag) ayarlar. Bu, nmap'in hedef sistemdeki portun açık olup olmadığını öğrenmek için bir istek gönderdiği anlamına gelir.
2. İkinci Adım (SYN-ACK): Eğer hedef sistemdeki port açıksa, hedef sistem bu isteğe SYN-ACK paketi ile cevap verir. Bu, portun açık olduğunu ve bağlantıların kabul edilebileceğini gösterir.
3. Üçüncü Adım (ACK): Nmap, alınan SYN-ACK paketine bir ACK paketi ile cevap vermez ve bu bağlantıyı tamamlamaz.

```shell
nmap -sS 192.168.1.2
```

### TCP CONNECT Scan

TCP bağlantı tabanlı tarama, TCP üçlü el sıkışma (three-way handshake) işlemini gerçekleştirir. Bu, istemcinin ve sunucunun birbirleriyle bağlantı kurmak için üç adımda (SYN, SYN-ACK, ACK) iletişim kurmasını içerir.

1. **Birinci Adım (SYN)**: Nmap, hedef sistemdeki belirli bir portu hedefleyerek TCP paketi gönderir ve SYN bayrağını (flag) ayarlar. Bu, nmap'in hedef sistemdeki portun açık olup olmadığını öğrenmek için bir istek gönderdiği anlamına gelir.
2. **İkinci Adım (SYN-ACK)**: Eğer hedef sistemdeki port açıksa, hedef sistem bu isteğe SYN-ACK paketi ile cevap verir. Bu, portun açık olduğunu ve bağlantıların kabul edilebileceğini gösterir.
3. **Üçüncü Adım (ACK)**: Nmap, alınan SYN-ACK paketine bir ACK paketi ile cevap verir ve böylece TCP üçlü el sıkışma işlemini tamamlar.

```shell
nmap -sT 192.168.1.2
```

### UDP Scan

UDP taraması, nmap'ın hedef sistemdeki UDP portlarının durumunu belirlemek için kullanılan bir tarama türüdür. UDP protokolü, TCP protokolünden farklı olarak bağlantısız ve güvensiz bir protokoldür. UDP taraması, hedef sistemdeki UDP portlarının açık olup olmadığını tespit etmek için UDP paketleri gönderir ve cevaplarına bakar. Ancak, UDP protokolüne özgü olarak, cevap vermeyen portlar açık olabilir veya gönderilen UDP paketleri güvenlik duvarları tarafından engellenebilir.

1. **Birinci Adım**: Nmap, hedef sistemdeki belirli bir UDP portunu hedefleyerek UDP Paketi gönderir.
2. **Ikinci Adım**: Eğer hedef sistemdei UDP port açıksa ve hedef servis UDP paketine cevap veriyorsa, nmap bu portu "OPEN" olarak işaretler.
3. **Üçüncü Adım**: Eğer hedef sistemdeki UDP port kapalıysa veya gönderilen UDP paketleri güvenlik duvarları tarafından engelleniyorsa ve cevap alınamıyorsa, nmap bu portu "CLOSED" olarak işaretler.
4. **Dördüncü Adım**: Eğer hedef sistem UDP portuna cevap vermiyor ve nmap, portun durumunu kesin olarak belirleyemiyorsa, portu "OPEN / FILTERED" olarak işaretler.

```shell
nmap -sU 192.168.1.2
```

### FIN Scan

TCP FIN taraması, nmap'ın hedef sistemdei TCP portlarının durumunu belirlemek için TCP FIN bayrağı (flag) kullanarak tarama yapmasını sağlar. Bu tarama yönteminde, nmap hedef sistemdeki belirli bir TCP portuna FIN paketi gönderir. Eğer hedef sistemdeki port kapalıysa, FIN paketine herhangi bir cevap verilmez. Ancak, eğer hedef sistemdeki port açık ve bağlantıya cevap veriyorsa, FIN-ACK paketi ile cevap verir.

```shell
namp -sF 192.168.1.2
```

### NULL Scan

TCP Null taramasında, nmap hiçbir bayrak (flag) ayarlamadan bir TCP paketi gönderir. Eğer hedef sistemdeki port kapalıysa, hedef sistem tarafından bir RST (reset) paketi ile cevap alacaktır. Eğer hedef sistemdei port açıksa, hedef sistem tarafından hiçbir cevap almayacaktır.

```shell
nmap -sN 192.168.1.2
```

### XMAS Scan

No TCP Flags adı verilen tarama yöntemi, nmap aracı ile kullanılan bir TCP tarama yöntemidir. Bu tarama, TCP protokolünün bayraklarını kullanarak hedef sistemdei belirli portların durumunu tespit etmeye çalışır. Xmas taramasında, nmap hedef sistemdeki bir TCP portuna bir dizi bayrak içermeyen (no flags set) TCP paketi gönderir. "Xmas" ismi, bu paketin bayraklarının birer Noel ağacını andırması nedeniyle verilmiştir. 

```shell
nmap -sX 192.168.1.2
```

# WINDOW Scan

Window taramasında, nmap hedef sistemdeki belirli bir TCP portuna SYN paketi gönderir ve ardından hedef sistemden gelen SYN-ACK paketindeki "Window" değerini kontrol eder. "Window" alanı, TCP bağlantısında alıcının verileri ne kadar kabul edebileceğini belirten bir değerdir. Bu değer, açık portlarda farklı değerlere sahip olabilirken, kapalı portlarda genellikle 0 olarak ayarlanmıştır.

1. **Açık Portlar**: Eğer hedef sistemdeki port açıksa, SYN-ACK paketindeki "Window" değeri genellikle sıfırdan farklı bir değere sahip olacaktır, çünkü hedef sistem veri alımı için bir pencere açacaktır.
2. **Kapalı Portlar**: Eğer hedef sistemdeki port kapalıysa, SYN-ACK paketindeki "Window" değeri muhtemelen 0 olarak ayarlanmış olacaktır, çünkü hedef sistem veri alımı için herhangi bir pencere açmayacaktır.

```shell
nmap -sW 192.168.1.2
```


### MAIMON SCAN

```shell
nmap -sM 192.168.1.2
```

### TCP ACK Scan

ACK Taraması, hedef sistemdeki belirli TCP portlarının durumunu tespit etmek için TCP ACK bayrağını (flag) kullanır. ACK bayrağı, TCP bağlantısındaki ACKnowledgement işareti olarak kullanılır ve genellikle mevcut bir bağlantının başarılı bir şekilde kurulduğunu gösterir. Ancak, ACK paketlerinin bağlantıyı kurma yeteneği yoktur ve bir bağlantı talebi veya kapanma talebi iletmek yerine, mevcut bir bağlantının devam ettiğini veya durumunu gösterir. ACK taramasında, nmap hedef sistemdeki belirli TCP portlarına ACK bayrağı içeren bir ACK paketi gönderir. Eğer hedef sistemdeki port açıksa, hedef sistem nmap'e bir RST (reset) paketi ile cevap verir. Eğer hedef sistemdeki port kapalıysa veya filtrelenmişse, ACK paketine hiçbir cevap alınmaz.

```shell
nmap -sA 192.168.1.2
```

### IPv6 SCAN

```shell
nmap -6 ADDR
```

---

# TARGET SPECIFICATION

| Komut | Açıklama |
| - | - |
| nmap 192.168.2.1 |  Tek IP tarama | 
| nmap 192.168.2.1 192.168.2.2 | Birden fazla IP tarama |
| nmap 192.168.2.1-10 | Belirli bir adres aralığındaki IP'leri tarama |
| nmap -iL targets.txt | Dosyadan okuyarak tarama |
| nmap 192.168.2.0/24 | Bir IP aralığını tarama |
| nmap 192.168.2.0/24 --exclude 192.168.2.0-15 | Belirli bir aralığı dışlayarak tarama |
| nmap 192.168.2.0/24 --excludefile exclude_targets.txt | Dışlanacak hedefleri dosyadan okuyarak tarama |

---

# PORT SPECIFICATION

| Komut | Açıklama |
| - | - |
| nmap -p 22 192.168.1.2 | Tek port tarama | 
| nmap -p 80, 8080 192.168.1.2 | Birden fazla portu tarama |
| nmap -p 30-50 192.168.1.2 | Port aralığını tarama |
| nmap -p -sS -sU U:53,T:80-100,8080 192.168.1.2 | Belirtilen TCP ve UDP portlarını tarama |
| nmap -p- 192.168.1.2 | Tüm portları tarama |
| nmap -p http 192.168.1.2 | HTTP portlarını tarama |
| nmap -p http? 192.168.1.2 | Başı HTTP ile başlayan portları tarama |
| nmap -p- http* 192.168.1.2 | HTTP ile başlayan portları tarama | 
| nmap -F 192.168.1.2 | Hızlı tarama, en bilinen 100 port |
| nmap -r -F 192.168.1.2 | Rastgele tarama | 
| nmap --top-ports 150 192.168.1.2 | En bilinen 150 portu tarama | 
| nmap --exclude-ports 50-100 192.168.1.2 | Belirtilen port aralığı haricini tarama |
| nmap -sn -PS21 192.168.1.2 | TCP SYN Taraması | 
| nmap -sn -PA22 192.168.1.2 | TCP ACK Taraması | 
| nmap -sn -PU23 192.168.1.2 | UDP Taraması | 
| nmap -sn -PU24 192.168.1.2 | SCTP Taraması |

---

# HOST DISCOVERY

| Komut | Açıklama |
| - | - |
| nmap -sL 192.168.1.2  | Yerel ağ tarama |
| nmap -sn 192.168.1.2 | Ping taraması |
| nmap -sn -PR 192.168.1.2 | ARP Taraması |
| nmap --traceroute -p 25 192.168.1.2 | Traceroute |

---

# SERVICE DETECTION

| Komut | Açıklama |
| - | - |
| nmap -sV 192.168.1.2 | Servis taraması |
| nmap -sV --version-intensity 0-9 192.168.1.2 | Servis tahmin derecesi |
| nmap -sV --version-light 192.168.1.2 | Düşük dereceli servis tahmini | 
| nmap -sV --version-all 192.168.1.2 | Servis tahmini |
| nmap -O 192.168.1.2 | İşletim sistemi taraması |
| nmap -O --osscan-limit 192.168.1.2 | İşletim sistemi tahmin limiti |
| nmap -O --osscan-guess 192.168.1.2 | İşletim sistemi tahmini | 
| nmap -A 192.168.1.2 | Agresif tarama | 

---

# TIMING

T1 (SNEAKY) -> T2 (POLITE) -> T3 (NORMAL) -> T4 (AGGRESSIVE) -> T5 (INSANE)

| Komut | Açıklama |
| - | - |
| nmap -T1 192.168.1.2 | Sneaky |
| nmap -T2 192.168.1.2 | Polite |
| nmap -T3 192.168.1.2 | Normal |
| nmap -T4 192.168.1.2 | Aggressive | 
| nmap -T5 192.168.1.2 | Insane | 
| nmap --min-rate 50 192.168.1.2 | Saniyede en az gönderilecek paket sayısı | 
| nmap --max-rate 100 192.168.1.2 | Saniyede en fazla gönderilecek paket sayısı | 
| nmap --min-retries X 192.168.1.2 | Saniyede en az deneme sayısı |
| nmap --max-retries X 192.168.1.2 | Saniyede en fazla deneme sayısı |
| nmap --host-timeout 10s IP_ADDR| Zaman aşımı süresi |
| nmap --min-hostgroup X -iL targets.txt| Eşzamanlı olarak taranacak en az grup sayısı | 
| nmap --max-hostgroup X -iL targets.txt| Eşzamanlı olarak taranacak en fazla grup sayısı | 

---

# NMAP SCRIPTING ENGINE (NSE)

scripts -> /usr/share/nmap/scripts bu dizinde bulunur.
script db -> /usr/share/nmap/scripts/script.db db dosyası bu dizinde bulunur.

### Script Kategorileri

1. **Safe (Güvenli)**: Bu kategori, nmap'in genellikle ağ üzerinde hiçbir değişiklik yapmadan çalıştırılabilen, hedef sistemlerde güvenli bir şekilde çalışan scriptleri içerir. Bu scriptler, hedef sistemlerin durumu hakkında bilgi toplamaya yönelik olabilir ve güvenlik duvarlarından veya diğer güvenlik önlemlerinden etkilenmeden çalışabilirler. Bu scriptlerin hedef sistemler üzerinde herhangi bir istismara neden olması beklenmez.
2. **Intrusive (Müdahaleci)**: Bu kategori, hedef sistemlerde etkili olmak için daha derinlemesine bir tarama yapıabilen ve bazı etkileri olabilen scriptleri içerir. Bu scriptler, hedef sistemleri daha etkili bir şekilde taramak ve bilgi toplamak için kullanılabilir. Ancak, bu scriptlerin hedef sistemlerde iz bırakabileceği ve güvenlik duvarları veya diğer savunma mekanizmaları tarafından algılanabileceği unutulmamalıdır.
3. **Vuln (Zafiyet)**: Bu kategori, hedef sistemlerdeki potansiyel güvenlik açıklarını tespit etmeye yönelik scriptleri içerir. Bu scriptler, yaygın güvenlik zafiyetlerini veya hatalı yapılandırmaları tespit etmeye çalışır. Bu tür scriptler, sistem yöneticilerine potansiyel riskleri belirlemeleri ve gidermeleri konusunda yardımcı olabilir.
4. **Exploit (İstismar)**: Bu kategori, hedef sistemlerdeki güvenlik açıklarını aktif olarak kullanmaya çalışan scriptleri içerir. Bu tür scriptler, gerçek saldırılar gibi davranabilir ve güvenlik açıklarını istismar etmeye çalışarak hedef sistemlere zarar verebilir. Bu nedenle, bu scriptleri kullanırken dikkatli olmak ve yasal izinleri almak son derece önemlidir.
5. **Auth (Kimlik Doğrulama)**: Bu kategori, hedef sistemlere kimlik doğrulama girişimlerinde bulunmayı amaçlayan scriptleri içerir. Bu scriptler, hedef sistemlerdeki kullanıcı adları ve parolalar gibi kimlik doğrulama bilgilerini test etmeye yönelik olabilir. Kimlik doğrulama için zayıf parolaları veya diğer güvenlik zayıflıklarını belirlemek için kullanılabilir.
6. **Brute (Brute Force)**: Bu kategori, hedef sistemlere brute force saldırılarını gerçekleştirmek için kullanılan scriptleri içerir. Brute force saldırıları, kullanıcı adları ve parolalar gibi kimlik doğrulama bilgilerini tahmin etmek için sürekli deneme yapar. Bu tür scriptlerin kullanımı, yasal izinleri almak ve etik kurallara uymak için çok önemlidir.
7. **Discovery (Keşif)**: Bu kategori, hedef sistemlerdeki ağ kaynaklarını keşfetmeye yönelik scriptleri içerir. Bu scriptler, açık portları, hedef sistemlerde çalışan servisleri ve diğer ağ bilgilerini belirlemeye çalışır.
8. **Default (Varsayılan)**: Bu kategori, nmap'in varsayılan olarak çalıştırılan scriptleri içerir. Nmap, varsayılan scriptlerin bir kısmını hedef sistemlerde çalıştırırken, diğer scriptleri ise kullanıcı tarafından belirtilen seçeneklerle çalıştırır.

| Komut | Açıklama |
| - | - |
| nmap -sC 192.168.1.2 | Default scriptleri kullanarak tarama |
| nmap --script=default 192.168.1.2 | Default scriptleri kullanarak tarama |
| nmap --script vuln 192.168.1.2 | Bir kategorideki scriptleri kullanarak tarama |
| nmap --script "vuln, exploit" 192.168.1.2 | Birden fazla kategorideki scriptleri kullanarak tarama |
| nmap --script "http-\*" 192.168.1.2 | http ile başlayan scriptlerle tarama | 
| nmap --script "not https\*" 192.168.1.2 | https içermeyen scriptlerle tarama | 
| nmap --script-help 192.168.1.2 | Script hakkında bilgi alma |
| nmap --script-updatedb | Script veritabanını güncelleme | 

---

# FIREWALL

| Komut | Açıklama |
| - | - |
| nmap -sS -f 192.168.1.2 | MTU belirterek tarama |
| nmap -sS --mtu 8,16,24,.. 192.168.1.2 (x8) | MTU belirterek tarama | 
| nmap -sS -D F_IP,F_IP 192.168.1.2 | Sahte adreslerle tarama | 
| nmap -sS -D RND:5 192.168.1.2 | Random 5 adresle tarama | 
| nmap -sS --spoof-mac "mac_prefix_name" 192.168.1.2 | MAC belirterek tarama | 
| nmap -sS --spoof-mac 11:22:33:aa:bb:cc 192.168.1.2 | MAC belirterek tarama |
| nmap -sS --spoof-mac 0 192.168.1.2 | Random MAC ile tarama | 

---

# OUTPUT

| Komut | Açıklama |
| - | - |
| nmap -sS -sV 192.168.1.2 -oN file.txt | Normal çıktı | 
| nmap -sS -sV 192.168.1.2 -oX file.txt | XML formatında çıktı | 
| nmap -sS -sV 192.168.1.2 -oS file.txt | Script kiddie formatında çıktı | 
| nmap -sS -sV 192.168.1.2 -oG file.txt | Grepable çıktı | 
| nmap -sS -sV 192.168.1.2 -oA file.txt | Tüm formatlarda çıktı |
| nmap -sS -sV 192.168.1.2 --reason | İlginç portlar tablosuna Nmap'in bir portu neden bu şekilde sınıflandırdığını açıklayan bir sütun ekler. | 
| nmap -sS -sV 192.168.1.2 --stats-every 5s | Tarama durumunu gösterme süresi | 
| nmap -sS -SV 192.168.1.2 --packet-trace | Nmap'in gönderdiği ve aldığı her paketin bir özetini yazdırmasına neden olur. | 
| nmap -sS -sV 192.168.1.2 -v | Çıktı göster | 











