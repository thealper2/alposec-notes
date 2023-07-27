| Komut | Açıklama |
| - | - |
| docker container run image:tag | Konteyner çalıştırma |
| docker container run -d image:tag | Arka planda konteyner çalıştırma |
| docker container run image:tag commands | Konteyner başlattıktan sonra komut çalıştırma |
| docker container run --name container_name image:tag | İsim vererek konteyner çalıştırma |
| docker container exec container_id commands  <br/> docker container exec container_name commands| Çalışan konteynerda komut çalıştırma |
| docker container exec -it container_id sh <br/> docker container exec -it container_name sh | Çalışan bir konteynerde shell bağlantısı alma | 
| docker container stop container_id <br/> docker container stop container_name | Çalışan konteyneri durdurma |
| docker container rm container_id <br/> docker container rm container_name | Konteyner silme |
| docker container run -rm image:tag | Kapatıldıktan sonra konteynerin otomatik silinmesi |
| docker container inspect container_id <br/> docker container inspect container_name | Konteyner detaylarını görüntüleme |
| docker container ls <br/> docker container ps | Çalışan konteynerleri listeleme |
| docker container ls -a <br/> docker container ps -a | Tüm konteynerleri listeleme |
| docker top container_id <br/> docker top container_name | Konteynerde çalışan işlemleri listeleme |
| docker stats container_id <br/> docker stats container_name | Konteyner kullanım istatistiklerini görüntülüme |
| docker container run -memory=300m --memory-swap=2g image:tag | Konteyner hafıza sınırlama |
| docker container run --cpus=".5" <br/> docker container run --cpuset-cpus="0,4" image:tag | Konteyner CPU sınırlama |
| docker container run --env VAR_NAME=VAR image:tag | Konteynere çevre değişkeni verme |
| docker cp container_id:/destination /save/path <br/> docker cp container_name:/destination /save/path | Konteynerden dosya kopyalama |
| docker image pull image:tag | İmaj çekme |
| docker image push repository_name/image:tag | Docker HUB'a imaj yükleme |
| docker image tag image:tag newimage:newtag | Mevcut imaja yeni tag ekleme |
| docker image inspect image:tag | İmaj detaylarını görüntüleme |
| docker image history image:tag | İmaj katmanlarını görüntüleme |
| docker image build -t image:tag . | Dockerfile ile yeni imaj oluşturma |
| docker image ls | Sistemdeki tüm imajları listeleme |
| docker save image:tag -o file.tar | İmaji bir dosyaya kaydetme |
| docker load -i file.tar | Kaydedilen imaji dosyadan yükleme |
| docker volume create volume_name | Volume oluşturma |
| docker volume inspect volume_id <br/> docker volume inspect volume_name | Volume detaylarını görüntüleme |
| docker volume ls | Sistemdeki tüm volumeleri listeleme |
| docker container run -v volume_name:path image:tag | Konteynere volume bağlama |
| docker container run -v volume_name:path:ro image:tag | Konteynere read-only volume bağlama |
| docker container run -v folder_path:path image:tag | Yerel bir klasörü veya dosyayı konteynere bağlama |
| docker volume rm volume_name | Volume silme |
| docker network create --driver=bridge network_name | Bridge Network oluşturma |
| docker network create --driver=bridge --subnet=192.168.1.0/24 --ip-range=192.168.1.0/24 --gateway=192.168.1.1 | Öntanımlı Bridge Network oluşturma |
| docker network ls | Sistemdeki tüm networkleri listeleme |
| docker network inspect network_name | Network detaylarını görüntüleme |
| docker container run --network network_name image:tag | Konteynırı network'e bağlama |
| docker network connect network_name container_id <br/> docker network connect network_name container_name | Çalışan konteynerı network'e bağlama |
| docker network disconnect network_name container_id <br/> docker network disconnect network_name container_name | Çalışan konteynerin network bağlantısını kesme |
| docker container run -p host_port:container_port image:tag | Port publishing |
| docker logs container_id <br/> docker logs container_name | Konteyner loglarını görüntüleme |
| docker logs --details container_id <br/> docker logs --details container_name | Konteyner loglarını detaylı görüntüleme |
| docker logs --since date_time --until date_time container_id <br/> docker logs --since date_time --until date_time container_name | Konteyner loglarına tarih filteri uygulama |
| docker logs -f container_id <br/> docker logs -f container_name | Konteyner loglarını izleme |

