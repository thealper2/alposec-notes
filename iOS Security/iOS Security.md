iOS, Apple Inc. tarafından geliştirilen ve Apple cihazların çalışan mobil işletim sistemidir. "iOS" adı "iPhone Ooperating System" kelimesinin kısaltmasından gelmektedir. iOS, katmanlardan oluşan bir işletim sistemidir. Her bit katman, belirli bir işlevi yerine getirir ve sistemin düzgün çalışmasını sağlar.

1. Uygulama Katmanı (App Layer): En üstteki katmandır ve kullanıcıların etkileşimde bulunduğu uygulamaları içerir. Bu katmanda, kullanıcı arayüzü ve uygulama mantığı yer alır.

2. Hizmet Katmanı (Services Layer): Bu katman, uygulamaların ortak işlevleri ve kaynaklara erişimi sağlar. 

3. Medya Katmanı (Media Layer): iOS cihazlarda medya içeriği için işlevler sağlar. Bu katman, medya içeriğinin depolanması, çalınması ve düzenlenmesi gibi görevleri üstlenir. Aynı zamanda kamera ve mikrofon gibi donanımlara erişimi de içerir.

4. Çekirdek Hizmet Katmanı (Core Services Layer): Bu katman, temel sistem hizmetlerini ve çeşitli işlevleri sağlar. Veritabanı yönetimi, ağ erişimi, dosya sistemi yönetimi ve temel veri yapıları gibi çekirdek hizmetler bu katmanda yer alır.

5. Çekirdek OS Katmanı (Core OS Layer): En alt düzeydeki katmandır ve işletim sisteminin temel bileşenlerini içerir. Güvenlik, bellek yönetimi, işlem yönetimi ve donanım sürücüleri gibi temel işlevler bu katmanda gerçekleştirilir.


| iOS Katmanları |  |
| - | - |
| Cocoa Touch | |
| Media | |
| Core Services | | 
| Core OS | | 


### Cocoa Nedir ? 

Cocoa, Apple Inc. tarafından geliştirilen ve macOS ve iOS işletim sistemlerinde kullanılan bir programlama çerçevesidir. Bu çerçeve, geliştiricilere uygulama yazmak için bir dizi araç ve kütüphane sağlar. macOS ve iOS platformlarında kullanıcı arayüzü oluşturmak, olay yönetimi, veritabanı işlemleri, ağ bağlantıları ve diğer çeşitli görevleri yerine getirmek için Cocoa'nın sunduğu araçlar kullanılır.

Cocoa, Objective-C ve Swift gibi programlama dillerini destekler. Başlangıçta sadece Objective-C ile kullanılabilse de, sonraki sürümlerde Swift dilinin tanıtılmasıyla birlikte Swift de Cocoa'nın temel dillerinden biri haline gelmiştir.

Cocoa, üç temel kütüphane üzerine inşa edilmiştir:

1. Foundation: Temel veri yapıları, dosya işlemleri, hafıza yönetimi, dil desteği, tarih ve saat işlemleri gibi işlevleri içerir. Birçok iOS ve macOS uygulamasında yaygın olarak kullanılan bu kütüphane, Core Foundation ile de entegre çalışabilir.
   
2. AppKit (macOS) / UIKit (iOS): macOS ve iOS platformları için kullanıcı arayüzü (UI) tasarlamak ve oluşturmak için kullanılan kütüphanelerdir. macOS için AppKit, iOS için UIKit kullanılır. Bu kütüphaneler, arayüz elemanları (pencere, düğme, metin kutusu vb.), olay yönetimi ve animasyonlar gibi UI unsurlarını yönetmeyi sağlar.
   
3. Core Data: Bu kütüphane, veritabanı yönetimi ve verilerin depolanması için kullanılır. Core Data, uygulamalarda veri modellemesi ve veritabanı işlemlerini kolaylaştırmak için bir arayüz sunar.

### IPA Dosya Yapısı

IPA dosyası, iOS işletim sisteminde çalışan uygulamaların dağıtımı ve yüklenmesi için kullanılan bir dosya türüdür. Bu dosya, uygulamanın tüm kaynak kodları, görseller, ses dosyaları, veritabanları, arayüz dosyaları ve diğer bileşenleri içerir. IPA dosyası, uygulamanın bir tür "paketlenmiş" sürümüdür ve bu sürüm, App Store'da yayınlanmadan önce dağıtım amacıyla kullanılır.

| Dosya | Açıklama |
| - | - |
| Executable (Yürütülebilir Dosya) | Uygulamanın çalıştırılabilir ana dosyasıdır. Bu dosya, uygulama kodunu içerir ve uygulamanın çalışmasını sağlar. Genellikle "AppName.app" adında bir klasör olarak bulunur ve uygulamanın ana yürütülebilir dosyası "AppName" adını taşır. |
| Info.plist | Uygulamanın temel yapılandırma bilgilerini içeren bir özellik listesi (Property List) dosyasıdır. Bu dosya, uygulama adı, sürüm numarası, gerekli yetkilendirmeler, desteklenen cihazlar ve diğer bilgiler gibi temel meta verileri içerir. |
| Frameworks | Uygulamanın kullanabileceği çeşitli önceden derlenmiş kütüphaneler ve çerçeveler burada bulunur. Bu, uygulamanın ihtiyaç duyduğu çeşitli işlevleri gerçekleştiren ve paylaşılan kod parçalarını içerir. |
| Assets | Görsel dosyalar, sesler, videolar ve diğer medya öğeleri gibi uygulama içeriği için kullanılan kaynak dosyaları burada bulunur. |
| Localizations (Çeviriler) | Birden fazla dilde uygulama metinlerini destekleyen çeviri dosyalarını içerir. Bu sayede, uygulama farklı dillerde kullanıcı arayüzü sağlayabilir. |
| Embedded Mobile Provisioning Profile | Bu, uygulamanın belirli cihazlarda ve kullanıcı hesaplarında çalışmasını sağlayan dağıtım profillerini içerir. |

