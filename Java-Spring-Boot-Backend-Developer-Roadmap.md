# Java + Spring Boot Backend Developer Roadmap
## Sıfırdan Junior Backend Developer'a — Yaşayan Eğitim Programı

**Durum:** 🟢 Aktif — Bölüm 1/4 tamamlandı (bu doküman parça parça büyüyecek)
**Son güncelleme:** Haziran 2026

---

## Bu Doküman Nasıl Kullanılır?

Bu bir kerelik üretilip unutulan bir PDF değil. Senin ilerlemenle birlikte büyüyen, gerektiğinde geri dönüp güncellenecek bir **çalışma dokümanı**.

Şu an elinde olan şey:

1. Üç pazarın (Türkiye/İstanbul, Remote Avrupa, Remote Dünya) gerçek iş ilanı beklentilerine dayanan bir analiz ve bunun roadmap'e nasıl yansıdığı,
2. Programın tamamının faz/modül haritası (ilerleme takip checklist'i olarak da kullanabilirsin),
3. Proje sisteminin tam mantığı (Proje A / Proje B, checkpoint'ler, git akışı),
4. **Faz 0** ve **Faz 1'in ilk iki modülünün** tam detaylı içeriği — buradan başlayabilirsin.

Geri kalan modüller (Faz 1.3'ten itibaren) kasıtlı olarak şimdilik sadece başlık seviyesinde. Sebebi basit: sen henüz oraya gelmedin, ve ben her konuyu önceki konunun üzerine inşa ederek vermek istiyorum — ezbere yığın bilgi değil. Bir modülü bitirdiğinde ya da bir sonrakini detaylandırmamı istediğinde bana şunu söylemen yeterli:

> "Modül 1.3'ü detaylandır" / "Faz 0'ı bitirdim, devam et" / "X konusunda zorlanıyorum, alternatif anlatım/kaynak öner"

Ben de bu dokümanı senin gerçek ilerlemene göre güncelleyeceğim, eksik gördüğüm yerleri ekleyeceğim, zorlandığın noktalarda ek materyal önereceğim.

---

## 📌 Revizyon Notu — v2 (Dış Review Sonrası Güçlendirme)

Bu roadmap bir dış değerlendirmeden (işe alım + uzun vadeli kariyer gözüyle) geçti ve haklı bulunan eksikler eklendi. Değişiklikleri **iki kategoriye** ayırdım, çünkü senin birinci hedefin net: *önce ilk işi bul, sonra ikinci aşamada maaş + diploma eksiğini kapat.* Bir şeyi "iyi olur" diye eklemek seni ilk işten geciktiriyorsa, bu kötü bir takastır.

**Şimdi roadmap'e eklendi (ilk iş için gerçekten gerekli):**
- **Faz 1'e:** DSA / Algoritma & Veri Yapıları modülü (1.7), Debugging modülü (1.8), JVM temelleri (1.9) — özellikle DSA en büyük gerçek eksikti, junior mülakatlarında canlı coding soruluyor.
- **Yeni Faz 3.5:** HTTP & Web Temelleri + Auth kavramları (status code, header, REST, Basic/Bearer/Cookie/Session, CORS, CSRF) — Spring REST API bunların üstüne oturuyor.
- **Faz 2 & 4'e gömüldü:** N+1 problem ve transaction isolation level (JPA'da seni mutlaka ısıracak konular).
- **Faz 8 Linux modülü** pratik komut setiyle güçlendirildi.
- **Design Pattern** erken tanıtımı Spring modülüne organik olarak eklendi (Spring bean'leri zaten Singleton vb.).
- **Her modüle standart "🎓 Senior Notları" bloğu:** sık yapılan hatalar + mülakat soruları + "Claude kötü kod versin, sen refactor et" pratiği.

**İkinci aşamaya not edildi (iş bulduktan SONRA — maaş + diploma eksiği):**
- Sistem Tasarımı (load balancer, CDN, rate limiting, horizontal scaling) — bunlar *mid-level* mülakat konusu, junior için değil.
- JVM/GC derinliği, SQL ileri optimizasyon (execution plan, covering index, deadlock).
- Open source katkısı, senior-seviye refactoring.
- Bunların iskeleti **Faz 14 (Senior Gibi Düşünme)** olarak haritaya kondu, ama bilinçli olarak ikinci aşamaya bırakıldı.

> Neyin neden birinci değil ikinci aşamaya konduğunu merak edersen sor — her kararın gerekçesi var.

---

# BÖLÜM 1 — Piyasa Analizi ve Bunun Roadmap'e Etkisi

Roadmap'i yazmadan önce Türkiye/İstanbul, Remote Avrupa ve Remote Dünya genelindeki Junior Backend (Java/Spring) ilanlarını taradım. Aşağıdaki sonuçlar moda olan değil, **fiilen ilanlarda tekrar eden** beklentilere dayanıyor.

## 1.1 Türkiye / İstanbul

- Açık pozisyonlar coğrafi olarak büyük ölçüde İstanbul'un Avrupa yakasında yoğunlaşıyor; Ankara ve İzmir ikinci sırada geliyor.
- Junior seviyesinde dahi, "Spring/Spring Boot bilmiyorsanız başvurmayınız" tarzı **net ve sert ön koşullar** yaygın — yani Spring artık junior için "öğrenirsin" değil, "gelmeden önce bil" seviyesinde bir beklenti haline gelmiş.
- Linux'a aşinalık ve Gitflow bilgisi, junior ilanlarında bile "artı puan" olarak özellikle belirtiliyor.
- Şirketler çoğunlukla Bilgisayar/Yazılım Mühendisliği mezuniyeti + Java/Spring + SQL kombinasyonunu arıyor; JavaScript/frontend bilgisi "tercihen" düzeyinde bir bonus.

## 1.2 Remote Avrupa

- Remote Avrupa ilanlarında, pozisyon "junior" diye etiketlenmiş olsa bile gerçek beklenti çoğu zaman Java + Spring Boot + REST API + Git + Docker + en az bir CI/CD aracı + en az bir bulut sağlayıcısına (AWS/Azure) aşinalık şeklinde özetleniyor.
- Remote çalışmaya özgü bir beklenti de var: zaman dilimi farkına rağmen net yazılı iletişim ve dokümantasyon alışkanlığı — bu, README ve teknik yazma becerinin neden bu roadmap'te zorunlu olduğunu doğruluyor.
- Dürüst olmak gerekirse: "remote + junior" araması yapıldığında sonuçların önemli bir kısmı gerçekte 3+ yıl deneyim isteyen rollerin "junior" anahtar kelimesiyle eşleşmiş hali çıkıyor. Yani **gerçek 0 deneyimli tam remote pozisyon arzı, Türkiye'deki hibrit/yerinde junior arzından daha düşük.** Bu, stratejik bir nottur — Bölüm 1.6'da bunu nasıl yöneteceğimizi anlatıyorum.

## 1.3 Remote Dünya Geneli

- Global ilanlarda junior/mid ayrımı şu şekilde netleşiyor: Junior seviyesi mülakat beklentisi temiz controller kodu, validation, temel exception handling, dependency injection ve SQL sorgu yazabilme; bir üst seviye API versiyonlama, authentication/authorization, integration test ve caching stratejileri ekliyor.
- 2026 itibarıyla Docker, CI/CD ve en az bir bulut sağlayıcısı artık "senior'a özel" değil, **cloud-native temel beklenti** olarak tanımlanıyor.
- Veritabanı tarafında beklenti sadece "SQL yazabilmek" değil; şema tasarımı, indexleme/sorgu optimizasyonu ve ACID/transaction kavramlarını anlamak olarak tarif ediliyor.
- 2026'ya özgü ilginç bir gözlem: AI destekli kod üretiminin yaygınlaşmasıyla birlikte, juniorları birbirinden ayıran şey artık "kod yazabilmek" değil, **bozuk bir sistemi debug edebilmek ve sistemin neden o şekilde çalıştığını anlayabilmek.** Bu yüzden bu roadmap'te "neden" sorusuna bu kadar çok yer ayırıyoruz.

## 1.4 Üç Pazarda da Ortak Çıkan Zorunlu Çekirdek (Tier 1)

Bunlar olmadan **hiçbir** junior ilanına gerçek anlamda hazır sayılmazsın:

- Java temelleri: OOP, Collections, Exception Handling
- Spring Boot + Spring MVC + Spring Data JPA (Hibernate)
- REST API tasarımı (controller, DTO, status code'lar)
- SQL + ilişkisel veritabanı tasarımı (PostgreSQL/MySQL)
- Git (gerçek anlamda — sadece `commit`/`push` değil)
- Maven veya Gradle
- Validation ve global exception handling

## 1.5 Seni Diğer Junior'lardan Ayıran Katman (Tier 2)

Bunlar artık "iyi olur" değil, **ciddi ilanların çoğunda fiilen aranıyor**:

- JWT Authentication + Spring Security
- Role Based Authorization
- Docker + Docker Compose
- CI/CD temelleri (GitHub Actions)
- Test yazma (JUnit, Mockito, integration test)
- Logging, pagination, filtering
- En az bir bulut sağlayıcısına (AWS veya Azure) temel aşinalık

## 1.6 Bonus / Orta Seviyeye Geçiş Sinyali (Tier 3)

Bunlar junior ilanlarının azınlığında zorunlu, ama varlığı seni **mid-level'a yakın** gösterir ve mülakatlarda fark yaratır:

- Redis ile caching
- Mesajlaşma temelleri (RabbitMQ/Kafka giriş seviyesi)
- OAuth2
- Clean Architecture / Hexagonal Architecture
- Microservice kavramsal temelleri
- Nginx, Testcontainers

## 1.7 Gerçekçi Beklenti Notu

Senin orijinal teknoloji listenin Tier 1 ve Tier 2'yi zaten neredeyse tamamen kapsadığını görüyorum — bu listeyi sezgisel değil, gerçekten doğru kurmuşsun. Roadmap'i bu üç katmana göre sıraladım; Tier 3'ü ise programın ikinci yarısına, temel sağlamlaştıktan sonra yerleştirdim.

Stratejik tavsiyem: **tam remote + 0 deneyim** kombinasyonunu ilk hedef olarak görme. Gerçekçi sıralama şu şekilde işler:
1. Önce Türkiye'deki (özellikle İstanbul) hibrit/yerinde junior ilanlarına güçlü bir portföyle başvur — arz burada daha gerçek.
2. Paralelde Remote Avrupa'daki, açıkça "junior/entry" diye 1-2 yıl deneyim isteyen (0 deneyim değil ama erişilebilir) rollere de portföyünü göstererek başvur.
3. Portföyün (özellikle bu roadmap'teki iki proje) büyüdükçe tam remote dünya geneli ilanlarına geçiş yap.

Bu, hayalini kırmak için değil — başvuru enerjini doğru yere harcaman için.

## 1.8 Sonuç: Bu Analiz Roadmap'i Nasıl Şekillendirdi

- Test yazma (JUnit/Mockito) bilinçli olarak Docker'dan **önce** değil, Authentication/Authorization'dan sonra ama Docker'dan önce yerleştirildi — çünkü test yazmayı öğrenmeden Docker'a geçmek "neyi test ettiğini bilmeden container'a koyma" riskini doğurur.
- OAuth2, Tier 3 olduğu için derinlemesine değil, kavramsal + basit uygulama seviyesinde işlenecek.
- Microservice ve Hexagonal Architecture "ileri seviye" olarak işaretlendi çünkü ilanlarda junior için nadiren zorunlu, ama büyük proje okuma yeteneğin için (senin de hedeflerinden biri) değerli.
- Git, ayrı bir modül olmaktan çıkarılıp **her fazın içine** gömüldü — çünkü gerçek git becerisi izole alıştırmalarla değil, gerçek proje akışı içinde öğrenilir.

---

# BÖLÜM 2 — Öğrenme Felsefesi

Bu programın üç kuralı var:

**1. Önce "neden", sonra "nasıl".** Her modül, o teknolojinin hangi problemi çözdüğünü, hangi alternatiflerin var olduğunu ve hangi durumda o teknolojinin *yanlış* tercih olacağını açıklayarak başlar. "Spring Data JPA nasıl kullanılır?" değil, önce "JDBC ile her repository metodunu elle yazmak neden sürdürülemez, ORM bu sorunu nasıl çözer, hangi bedeli öder?" sorusuna cevap veririz.

**2. Spiral öğrenme.** Hiçbir konu izole değil. Faz 1'de öğrendiğin `equals()`/`hashCode()` davranışı, Faz 2'de veritabanı entity'lerinde, Faz 4'te JPA entity'lerinde karşına tekrar çıkacak — her seferinde bir önceki bilgiye yeni bir kat ekleyerek.

**3. Üretmeden öğrenme yok.** Her modülde mini egzersizler var. Pasif okuma seni mülakata hazırlamaz; klavyenin başında geçirdiğin saatler hazırlar.

Her modülün başında kısa bir **"Neden Bu Modülü Öğreniyorum?"** bölümü bulacaksın — bu, programın "ezber değil, anlama" prensibinin somut karşılığı.

## 🎓 Her Modülün Standart Kapanış Bloğu: "Senior Notları"

v2'den itibaren her modül, mevcut kapanış başlıklarına (Kazanılan Yetenekler, Git Becerileri vb.) ek olarak bir **🎓 Senior Notları** bloğuyla bitiyor. Bu blok üç şeyi içerir ve roadmap'i "öğrenen junior"dan "düşünen geliştirici"ye çeviren kısımdır:

- **⚠️ Sık Yapılan Hatalar:** Bu konuda juniorların düştüğü tipik tuzaklar ve seniorların neye dikkat ettiği.
- **🎤 Mülakat Soruları:** Bu modülden gerçek mülakatlarda sorulabilecek sorular (cevaplarını kendin üretmeye çalış, sonra bana kontrol ettir).
- **🔧 Kötü Kod → Refactor Pratiği:** Bana "bu modül için kötü kod örneği ver" dediğinde, sana kasıtlı olarak hatalı/kokulu (code smell içeren) bir kod parçası veririm; sen refactor edersin, ben senior gibi code review yaparım. Bu, kod *okuma* ve *eleştirme* kasını çalıştırır — ki bu, AI çağında bir junior'ı değerli kılan asıl beceridir.

> Bu blok, halihazırda detaylı olan modüllerde (0.1, 0.2, 1.1, 1.2) aşağıda mevcut. Bundan sonra detaylandıracağım her modülde standart olarak yer alacak.

---

# BÖLÜM 3 — Programın Tam Haritası (İlerleme Takip Listesi)

Aşağıdaki liste, programın tamamını gösterir. Tamamladığın modülleri işaretleyerek bunu kendi ilerleme takip aracın olarak kullanabilirsin. **🔵 işaretli modüller bu dokümanda zaten tam detaylı; diğerleri sıradaki bölümlerde detaylandırılacak.**

### FAZ 0 — Ortam ve Git Temelleri
- [ ] 🔵 0.1 — Geliştirme Ortamı Kurulumu
- [ ] 🔵 0.2 — Git ve GitHub Temelleri

### FAZ 1 — Java Temelleri
- [ ] 🔵 1.1 — Söz Dizimi ve Temel Yapılar
- [ ] 🔵 1.2 — Nesne Yönelimli Programlama (OOP)
- [ ] 1.3 — Collections Framework & Generics
- [ ] 1.4 — Exception Handling
- [ ] 1.5 — Java 8+ Modern Özellikler (Lambda, Stream API, Optional)
- [ ] 1.6 — Multithreading & Concurrency Temelleri
- [ ] 1.7 — 🆕 Veri Yapıları & Algoritma (DSA) + Big O — *mülakat için kritik*
- [ ] 1.8 — 🆕 Debugging (IntelliJ debugger, stack trace okuma, exception analizi)
- [ ] 1.9 — 🆕 JVM Temelleri (JDK/JRE/JVM, heap/stack, GC — kavramsal)

### FAZ 2 — Veritabanı ve SQL
- [ ] 2.1 — İlişkisel Veritabanı Tasarımı (ER modelleme, normalizasyon)
- [ ] 2.2 — SQL Derinlemesine (DDL/DML/DQL, join'ler, alt sorgular)
- [ ] 2.3 — Indexing ve Query Optimization Temelleri
- [ ] 2.4 — Transactions ve ACID (🆕 isolation level'lar dahil)
- [ ] 2.5 — JDBC Temelleri
  - 🆕 *Not: N+1 problem kavramı burada tanıtılır, Faz 4'te JPA bağlamında derinleşir*

### FAZ 3 — Build Tools
- [ ] 3.1 — Maven / Gradle ve Profesyonel Proje Yapısı

### 🆕 FAZ 3.5 — HTTP & Web Temelleri (Spring'den ÖNCE)
- [ ] 3.5.1 — HTTP protokolü: method'lar, status code'lar, header'lar, request/response anatomisi
- [ ] 3.5.2 — REST mimari prensipleri ve idempotency
- [ ] 3.5.3 — Auth kavramları: Basic Auth, Bearer Token, Cookie vs. Session, CORS, CSRF
- [ ] 3.5.4 — (Kavramsal farkındalık) TCP/DNS/HTTPS — derinleşme değil, "ne işe yarar" düzeyi

### FAZ 4 — Spring Framework Temelleri
- [ ] 4.1 — Spring Core: IoC ve Dependency Injection
- [ ] 4.2 — Spring Boot ile Proje Başlatma ve Auto-Configuration
- [ ] 4.3 — Spring MVC ve REST API Geliştirme
- [ ] 4.4 — Spring Data JPA ve Hibernate (🆕 N+1 problem burada derinlemesine işlenir)
- [ ] 4.5 — Validation
- [ ] 4.6 — Global Exception Handling (@ControllerAdvice)
- [ ] 4.7 — Logging
- [ ] 4.8 — Pagination ve Filtering
  - 🆕 *Not: Singleton/Factory/Builder pattern'leri bu fazda organik olarak tanıtılır (Spring bean'leri zaten Singleton'dır), tam Design Pattern işlemesi Faz 11'de*

**🚩 PROJE CHECKPOINT 1 — CRUD (Repo A & Repo B → v0.1.0)**

### FAZ 5 — Authentication
- [ ] 5.1 — Spring Security Temelleri
- [ ] 5.2 — JWT Authentication

**🚩 PROJE CHECKPOINT 2 — Authentication (v0.2.0)**

### FAZ 6 — Authorization
- [ ] 6.1 — Role Based Authorization
- [ ] 6.2 — OAuth2 Temelleri

**🚩 PROJE CHECKPOINT 3 — Role Based Authorization (v0.3.0)**

### FAZ 7 — Test Yazma
- [ ] 7.1 — JUnit 5 Temelleri
- [ ] 7.2 — Mockito ile Unit Test
- [ ] 7.3 — Integration Testing (MockMvc, @SpringBootTest)
- [ ] 7.4 — Testcontainers

*(Bu fazda ayrı bir proje checkpoint'i yok — mevcut projelere test eklemek, bu fazın projesi.)*

### FAZ 8 — Containerization
- [ ] 8.1 — Linux Temelleri (🆕 pratik komut seti: permissions, grep, find, tail, ps, ssh, scp, curl, wget)
- [ ] 8.2 — Docker Temelleri
- [ ] 8.3 — Docker Compose

**🚩 PROJE CHECKPOINT 4 — Docker (v0.4.0)**

### FAZ 9 — Performans ve Caching
- [ ] 9.1 — Caching Kavramları + Spring Cache Abstraction
- [ ] 9.2 — Redis

**🚩 PROJE CHECKPOINT 5 — Redis (v0.5.0)**

### FAZ 10 — Ek Backend Servisleri
- [ ] 10.1 — File Upload
- [ ] 10.2 — Email Service
- [ ] 10.3 — Mesajlaşma Temelleri (RabbitMQ/Kafka giriş seviyesi)

**🚩 PROJE CHECKPOINT 6 — Messaging (v0.6.0)**

### FAZ 11 — Mimari ve Tasarım
- [ ] 11.1 — SOLID Prensipleri
- [ ] 11.2 — Design Patterns
- [ ] 11.3 — Clean Code
- [ ] 11.4 — Clean Architecture
- [ ] 11.5 — Hexagonal Architecture (ileri seviye)
- [ ] 11.6 — Microservice Temelleri (kavramsal)

**🚩 PROJE CHECKPOINT 7 — Clean Architecture Refactor (v0.7.0)**

### FAZ 12 — CI/CD ve Cloud
- [ ] 12.1 — Nginx Temelleri
- [ ] 12.2 — CI/CD ve GitHub Actions
- [ ] 12.3 — AWS veya Azure Temelleri

**🚩 PROJE CHECKPOINT 8 — Deployment (v1.0.0) — FINAL CAPSTONE**

### FAZ 13 — İş Arama Hazırlığı
- [ ] 13.1 — CV ve GitHub Profili Optimizasyonu (🆕 ön lisanslı aday için özel: otomatik CV filtresini geçme taktikleri)
- [ ] 13.2 — Mülakat Hazırlığı (canlı coding, SQL/Java/Spring soruları)
- [ ] 13.3 — 🆕 Mock Teknik Mülakat + Mock HR Mülakatı (Claude ile prova)
- [ ] 13.4 — Başvuru Stratejisi (TR/İstanbul ajans & KOBİ öncelikli, sonra Remote Avrupa/Dünya)

**🎯 BİRİNCİ HEDEF SINIRI — İLK İŞ:** Faz 13'ün sonu, *birinci hedefin* (ilk developer işini bulmak) hedef çizgisidir. Buraya kadar olan her şey ilk işe girmen için gereken çekirdeği oluşturur. **Faz 14 ve aşağıdaki "İkinci Aşama" içeriği, iş bulduktan SONRA başlar.**

---

### 🆕 FAZ 14 — Senior Gibi Düşünme (İKİNCİ AŞAMA — iş bulduktan sonra)

Bu faz bilinçli olarak ikinci aşamaya konuldu. İçeriği hem işe başladıktan sonraki ilk aylara adaptasyonunu kolaylaştırır, hem de senin ikinci hedefinin (maaş yükseltme + mühendislik diploması eksiğini kapatma) tam malzemesidir. İlk işi bulmadan bunlara girmek "koşmayı öğrenmeden maraton" olur.

- [ ] 14.1 — Bozuk projeleri onarma (debugging odaklı derin pratik)
- [ ] 14.2 — Gerçek GitHub issue'larını çözme + küçük open source PR'lar
- [ ] 14.3 — Senior-seviye refactoring görevleri
- [ ] 14.4 — Sistem Tasarımı temelleri (Rate Limiting, Load Balancer, Reverse Proxy, CDN, Horizontal Scaling) — *mid-level mülakat konusu*
- [ ] 14.5 — SQL ileri optimizasyon (Execution Plan, Composite/Covering Index, Deadlock, Lock)
- [ ] 14.6 — JVM/GC derinliği (memory model, garbage collector türleri)
- [ ] 14.7 — Güvenlik açığı tespiti (OWASP temelleri)
- [ ] 14.8 — DGS değerlendirmesi (mühendislik diplomasına geçiş — opsiyonel B planı)

**Kabaca süre beklentisi (bağlayıcı değil, sadece pusula):** Birinci hedef (Faz 0→13, ilk işe hazır olma) tam zamanlı yoğun çalışmayla ~4-6 ay, part-time (haftada 10-15 saat) çalışmayla ~9-14 ay. Faz 14 ise iş bulduktan sonra, işle paralel ilerleyen açık uçlu bir aşamadır. Senin hızın senin hızındır; bu sayılar kendini kötü hissetmen için değil, plan yapman için.

---

# BÖLÜM 4 — Proje Sistemi: İki Paralel Repo, Sekiz Checkpoint

Senin istediğin "Proje A / Proje B" yapısını şu şekilde kurguladım: **8 ayrı checkpoint için 16 dağınık küçük repo yerine, iki uzun ömürlü repo** — her biri 8 checkpoint boyunca evrilen, gerçek bir commit geçmişine sahip, production mantığında büyüyen birer sistem.

Bunun nedeni basit: bir işe alım uzmanı GitHub'ında 16 yarım kalmış küçük proje değil, **özenle büyütülmüş, anlamlı release geçmişi olan 2 sağlam proje** görmek ister. Senin git öğrenme hedefin de (feature branch, PR, squash merge, semantic commit, release tag) tam olarak bu yapıda gerçek anlamını bulur.

## 4.1 Repo A — "Kütüphane ve Ödünç Takip Sistemi" (Öğretici Mod)

**Senaryo:** Bir kütüphanenin kitap, üye ve ödünç alma süreçlerini yöneten bir backend sistemi. İlişkisel veri (kitap-yazar-kategori), zaman bazlı iş kuralları (son teslim tarihi, gecikme), bildirim ihtiyacı (e-posta hatırlatma) gibi gerçekçi senaryolar barındırdığı için her faz için doğal bir genişleme alanı sağlıyor.

**Çalışma modu:** Bu repo üzerinde Claude Code ile birlikte çalışacaksın. Burada Claude Code'un rolü kod yazıp sana teslim etmek değil:

- Her mimari karardan önce *"neden bu paket yapısını seçtik, alternatifi ne olurdu"* sorusunu sana sorar ve cevabını tartışır,
- Her sınıf/interface/annotation eklenmeden önce *"bu neden gerekli, olmasa ne kaybederdik"* sorusunu açar,
- Hazır çözüm vermek yerine seni düşündüren sorularla yönlendirir,
- Senin yazdığın kodu, senin verdiğin kararları temel alarak ilerler — pasif izleyici değil, aktif karar verici olman beklenir.

Bu modun amacı **context engineering** mantığını öğrenmen: büyük bir projenin neden o şekilde organize edildiğini okuyup anlayabilmen.

## 4.2 Repo B — "Görev ve Proje Yönetim Platformu" (Bağımsız Mod)

**Senaryo:** Mini bir Trello/Jira — kullanıcılar, projeler, görevler, roller (admin/yönetici/üye), görev atama ve durum takibi. RBAC, dosya eki, bildirim gibi konuları farklı bir iş mantığı üzerinden tekrar uygulamana imkân verir — yani aynı kavramı iki farklı bağlamda görmüş olursun, bu da gerçek öğrenmenin göstergesidir.

**Çalışma modu:** Bu projeyi sen yazarsın. Ben:

- Kod yazmam,
- Sana ipucu veririm (çözümü değil, doğru soruyu),
- Mimarini incelerim ve eksiklerini söylerim,
- Code review yaparım — gerçek bir senior'ın PR'ına yazacağı türden yorumlarla.

Bu modun amacı: gerçek bir iş ortamında karşılaşacağın "kendi başına çöz, sıkıştığında danış" deneyimini şimdiden yaşaman.

## 4.3 Checkpoint → Git Akışı Eşleşmesi

Her checkpoint'te **her iki repo için de** aynı akış işler:

1. `feature/<checkpoint-adi>` branch'i aç (örn. `feature/jwt-authentication`)
2. O checkpoint'in konularını o branch üzerinde geliştir, anlamlı aralıklarla **semantic commit** at (`feat:`, `fix:`, `refactor:`, `test:`, `docs:`)
3. Kendi kendine bir Pull Request aç, README'sinde "bu PR neyi, neden değiştiriyor" yaz (gerçek bir code review pratiği)
4. **Squash merge** ile `main`'e birleştir
5. `git tag v0.X.0` ile o checkpoint'i bir release olarak işaretle ve GitHub'da bir "Release" notu yayınla

Bu sekiz checkpoint'in sonunda her iki reponda da `v1.0.0`'a ulaşmış, **sekiz anlamlı release'lik bir geçmişe sahip**, production mantığında düşünülmüş, README ve dokümantasyonu tam iki proje olacak.

## 4.4 Her Projede Olması Gerekenler (Kalite Standardı)

- Profesyonel klasör yapısı (katmanlı mimariden Clean Architecture'a evrilen)
- Kapsamlı `README.md`: proje amacı, kurulum talimatları, mimari kararlar, API dokümantasyonu (Postman koleksiyonu veya Swagger/OpenAPI)
- `.gitignore`, ortam değişkenleri için `.env.example`
- Faz 7'den sonra: test coverage'ı görünür şekilde belirtilmiş
- Faz 12'den sonra: çalışan bir CI/CD pipeline durumu (badge ile README'de gösterilebilir)

---

# BÖLÜM 5 — FAZ 0: Ortam ve Git Temelleri

## Modül 0.1 — Geliştirme Ortamı Kurulumu

### Neden Bu Modülü Öğreniyorum?

Kod yazmadan önce çözülmesi gereken bir problem var: **tutarlı, tekrar üretilebilir bir geliştirme ortamı.** Çoğu junior'ın ilk haftalarını kaybettiği yer burasıdır — IDE ayarları, sürüm uyumsuzlukları, "bende çalışıyor ama hocada çalışmıyor" durumları. Bu modülde sadece araçları kurmuyoruz; "neden JDK'nın LTS sürümünü seçiyoruz", "IDE arka planda ne yapıyor", "terminal neden hâlâ önemli" sorularının cevabını da kuruyoruz. Bu son soru özellikle önemli: GUI bir IDE'ye güvenmek, terminalin ne yaptığını anlamadan IDE'nin "sihirli" davranışlarına bağımlı kalmana yol açar — bu da Docker, CI/CD ve Linux modüllerinde seni zorlayacak bir eksiklik olur.

### 1. Öğrenilecek Konular

- JDK kurulumu (Java 17 veya 21 LTS — neden LTS sürüm tercih edilir, "her 6 ayda çıkan" sürümlerden farkı)
- IntelliJ IDEA Community Edition kurulumu (Ultimate ile farkı, junior için neden Community yeterli)
- Terminal/komut satırı temelleri: `cd`, `ls`/`dir`, `mkdir`, `cat`, `history`, dosya yolu mantığı
- Ortam değişkenleri kavramı: `PATH`, `JAVA_HOME` — bunlar olmadan işletim sisteminin komutları nasıl bulamayacağı
- GitHub hesabı oluşturma, SSH key üretimi ve GitHub'a ekleme
- API test aracı kurulumu (Postman veya Insomnia) — ileride REST API'leri test etmek için

### 2. Öğrenme Hedefleri

Bu modülün sonunda:
- Kendi makinende sıfırdan bir Java geliştirme ortamı kurabiliyorsun
- Terminalde temel gezinme ve dosya işlemlerini yapabiliyorsun
- SSH key ile GitHub'a güvenli bağlantı kurabiliyorsun
- "Ortam tutarlılığı" probleminin ne olduğunu kavramsal olarak anlıyorsun (bu, Docker modülünün temelini oluşturacak)

### 3. Öğrenme Sırası

Ön koşul yok — bu programın ilk adımı. Sıralama: JDK kurulumu → terminalden `java -version` / `javac -version` ile doğrulama → JAVA_HOME kontrolü → IntelliJ kurulumu → ilk "Hello World" (önce terminalden elle derleyip çalıştırarak, sonra IDE üzerinden) → Git kurulumu → GitHub hesabı + SSH key → Postman kurulumu.

### 4. Mini Egzersizler

1. Terminalden `java -version` ve `javac -version` çıktısını al, JDK'nın doğru kurulduğunu doğrula
2. IDE kullanmadan bir `Merhaba.java` dosyası yaz, terminalden `javac Merhaba.java` ile derle, `java Merhaba` ile çalıştır — IDE'nin arka planda hangi adımı senin için otomatikleştirdiğini gözlemle
3. Terminalden `echo $JAVA_HOME` (Mac/Linux) veya `echo %JAVA_HOME%` (Windows) ile ortam değişkenini doğrula
4. GitHub'da boş bir repo oluştur, SSH üzerinden `git clone` ile bilgisayarına çek

### 5. Git Kullanımı

Bu modülde henüz proje kodu yazılmıyor, ama Git'in temel kurulumu burada yapılıyor: `git config --global user.name` / `user.email`, `ssh-keygen -t ed25519` ile key üretimi, public key'i GitHub'a ekleme, `git clone` ile bağlantı testi.

**Öneri:** Bu roadmap'i takip edeceğin bir `learning-log` reposu aç. Her modül sonunda kısa bir markdown not girişi yapman, hem git pratiği hem de kendi ilerlemenin somut bir kaydı olur.

### Kazanılan Yetenekler
Ortam kurma, terminal temelleri, SSH ile güvenli bağlantı kurma.

### Öğrenilen Teknolojiler
JDK (17/21 LTS), IntelliJ IDEA, Git, GitHub, Postman/Insomnia.

### Git Becerileri
`git config`, `ssh-keygen`, `git clone`.

### Yapılan Projeler
Yok — bu bir hazırlık modülü. Opsiyonel: `learning-log` reposu.

### Bir Sonraki Modüle Hazır Olma Kriterleri
Terminalde `java -version` ve `git --version` çalışıyor; GitHub hesabın SSH ile bağlı; IntelliJ'de yeni bir proje açıp basit bir programı çalıştırabiliyorsun.

### 🎓 Senior Notları
- **⚠️ Sık Yapılan Hatalar:** JDK yerine sadece JRE kurmak (sonra `javac` çalışmaz); `JAVA_HOME`'u yanlış yola işaret ettirmek; SSH yerine HTTPS+şifre ile uğraşıp her push'ta kimlik doğrulamayla boğuşmak; birden fazla JDK sürümü kurup hangisinin aktif olduğunu bilmemek.
- **🎤 Mülakat Soruları:** "JDK, JRE ve JVM arasındaki fark nedir?" / "PATH ortam değişkeni ne işe yarar?" / "Neden LTS sürüm tercih edilir?"
- **🔧 Kötü Kod → Refactor Pratiği:** (Bu modül kurulum odaklı olduğu için kod yerine) Bana "ortam kurulumumu kontrol et" de; sana bir doğrulama checklist'i veririm, çıktıları paylaş, eksik/yanlış yapılandırmaları senior gözüyle işaretleyeyim.

---

## Modül 0.2 — Git ve GitHub Temelleri

### Neden Bu Modülü Öğreniyorum?

Git'in çözdüğü problem şu: kod tek bir doğrusal zaman çizgisinde ilerlemez. Birden fazla özelliği paralel geliştirmen, hata yaptığında geri dönebilmen, başkalarının (veya gelecekteki kendinin) "bu satır neden değişti" sorusuna cevap bulabilmen gerekir. Git'in merkezi olmayan (distributed) modeli, SVN gibi eski merkezi sistemlere göre bunu çok daha esnek çözer — her geliştirici kendi tam geçmişine sahip olur, merkezi sunucuya bağımlı kalmaz. Bu roadmap'te git'i "ödev teslim aracı" olarak değil, **gerçek bir mühendislik aracı** olarak öğreniyoruz; çünkü işe alımda bakılan şeylerden biri tam olarak bu: commit geçmişinin ne kadar "düşünülmüş" olduğu.

### 1. Öğrenilecek Konular

- Temel komutlar: `init`, `clone`, `status`, `add`, `commit`, `log`, `diff`
- Staging area kavramı — neden `add` ile `commit` ayrı adımlar
- Branch yönetimi: `branch`, `checkout`/`switch`, `merge` (fast-forward vs. 3-way merge)
- Merge conflict oluşumu ve çözümü
- Remote işlemler: `push`, `pull`, `fetch` — `pull` ile `fetch`+`merge` arasındaki fark
- `.gitignore` mantığı
- **Semantic commit** standardı: `feat:`, `fix:`, `refactor:`, `docs:`, `test:`, `chore:`
- Basit bir Gitflow-lite yaklaşımı: `main` + `feature/*` branch'leri
- Pull Request kavramı ve kod incelemesi mantığı (tek kişi olsan bile)
- `rebase` — ne zaman merge, ne zaman rebase tercih edilir (rebase geçmişi "düzleştirir" ama paylaşılan branch'lerde tehlikelidir — bu fark mülakatlarda sorulur)
- **Squash merge** — birden fazla küçük commit'i tek, anlamlı bir commit'e indirgeme
- **Release tag**: `git tag v0.1.0` ve GitHub Release yayınlama

### 2. Öğrenme Hedefleri

Modül sonunda gerçek bir repository'nin geçmişini profesyonelce yönetebiliyorsun: anlamlı commit mesajları yazabiliyorsun, branch açıp birleştirebiliyorsun, conflict çözebiliyorsun, ne zaman merge ne zaman rebase kullanacağını biliyorsun, release'leri tag'leyebiliyorsun.

### 3. Öğrenme Sırası

Yerel temel komutlar (`init`, `add`, `commit`, `log`) → branching ve local merge → remote bağlantı (GitHub'a push/pull) → işbirliği kavramları (PR açma, kendi kendine review alışkanlığı) → bilinçli conflict oluşturma ve çözme → semantic commit standardı → rebase (merge'e güvendikten sonra, kafa karışıklığını önlemek için) → tag/release.

### 4. Mini Egzersizler

1. `learning-log` reposunda ilk commit'i `feat: roadmap calismasina baslandi` mesajıyla yap
2. `feature/git-pratigi` branch'i aç, üzerinde birkaç anlamlı commit yap, GitHub'da kendine bir PR aç, PR açıklamasını yaz, sonra squash merge ile birleştir
3. Bilerek bir merge conflict oluştur: iki farklı branch'te aynı dosyanın aynı satırını değiştir, birleştirmeye çalış, çıkan conflict'i elle çöz
4. `git log --oneline --graph --all` ile branch geçmişini görselleştir ve ne olduğunu yorumla
5. `v0.0.1` tag'i oluştur, GitHub'da bir Release yayınla, release notlarını yaz

### 5. Git Kullanımı

Bu modülün tamamı zaten git pratiği. Özellikle şu beceriler bu noktada netleşmeli: feature branch açma, anlamlı commit, PR açma, squash merge, semantic commit formatı, release tag. **Bu pattern, roadmap boyunca her proje checkpoint'inde tekrar tekrar kullanılacak** — burada sağlam öğrenirsen, ileride otomatik hale gelir.

### Kazanılan Yetenekler
Profesyonel git akışı yürütebilme, conflict çözme, anlamlı geçmiş oluşturma.

### Öğrenilen Teknolojiler
Git, GitHub (PR, Issues, Releases).

### Git Becerileri
`branch`, `merge`, `rebase`, conflict resolution, semantic commit, PR, squash merge, tag/release.

### Yapılan Projeler
`learning-log` reposu üzerinde git pratiği (gerçek proje değil, ama gerçek git akışı).

### Bir Sonraki Modüle Hazır Olma Kriterleri
Bir branch açıp birleştirebiliyorsun, bilerek oluşturduğun bir conflict'i çözebiliyorsun, semantic commit formatını otomatik olarak kullanıyorsun, bir tag oluşturup GitHub'da release yayınlayabiliyorsun.

### 🎓 Senior Notları
- **⚠️ Sık Yapılan Hatalar:** Her şeyi `main`'e doğrudan commit'lemek (branch kullanmamak); "fix", "update", "asdf" gibi anlamsız commit mesajları; paylaşılan bir branch'te `rebase` yapıp başkalarının (veya gelecekteki kendinin) geçmişini bozmak; `.gitignore` kurmadan `target/`, `.idea/`, `*.class` gibi dosyaları repoya yüklemek; `git push --force`'u düşünmeden kullanmak.
- **🎤 Mülakat Soruları:** "Merge ile rebase arasındaki fark nedir, hangisini ne zaman kullanırsın?" / "`git pull` ile `git fetch` arasındaki fark?" / "Squash merge ne işe yarar?" / "Bir merge conflict'i nasıl çözersin?" / "Staging area (index) nedir, neden var?"
- **🔧 Kötü Kod → Refactor Pratiği:** Bana "kötü bir commit geçmişi örneği ver" de; sana dağınık, anlamsız mesajlı, mantıksız parçalanmış bir commit serisi tarif edeyim; sen bunu interaktif rebase + squash ile temiz, anlamlı bir geçmişe nasıl çevireceğini anlat, ben kontrol edeyim.

---

# BÖLÜM 6 — FAZ 1: Java Temelleri (Başlangıç)

## Modül 1.1 — Söz Dizimi ve Temel Yapılar

### Neden Bu Modülü Öğreniyorum?

Spring Boot, Hibernate, REST API'ler — bunların hepsi Java'nın üzerine kurulu birer **soyutlama katmanı**. Bir framework'ün arkasında ne olduğunu anlamadan o framework'ü kullanmak, hata aldığında çözüm üretemeyen, sadece Stack Overflow'dan kopyala-yapıştır yapan bir geliştirici yapar seni. Bu modülde Java'yı değil, programlamanın evrensel yapı taşlarını (değişken, kontrol akışı, döngü) Java sözdizimiyle öğreniyoruz — bu bilgi, ileride başka bir dile geçsen bile (Python, Go, Node.js da geçerli backend seçenekleri) taşınabilir. Java'yı özellikle seçmemizin nedeni Bölüm 1'deki piyasa analizi: kurumsal backend dünyasında hâlâ baskın, güçlü tip sistemi sayesinde hataları derleme zamanında yakalıyor (bu, runtime'da patlayan bug'larla uğraşmaktan seni kurtarır).

### 1. Öğrenilecek Konular

- Değişkenler ve tipler: primitive tipler (`int`, `double`, `boolean`, `char` vb.) ile referans tipler arasındaki fark
- Operatörler (aritmetik, karşılaştırma, mantıksal, atama)
- Kontrol akışı: `if/else`, klasik `switch` ve modern switch expression (Java 14+)
- Döngüler: `for`, `while`, `do-while`, enhanced `for` (for-each)
- Diziler (array) — sabit boyut kavramı, neden Collections'a geçileceği (bir sonraki modülün habercisi)
- Metodlar: parametre, dönüş tipi, overloading
- String yönetimi ve **immutability** — String'in neden değiştirilemez olduğu, bunun bellek ve thread-safety açısından neden önemli olduğu
- Temel I/O: `Scanner` ile kullanıcı girdisi, `System.out` ile çıktı
- Derleme modeli: `.java` → `javac` → bytecode (`.class`) → JVM'in çalıştırması (kavramsal düzeyde)

### 2. Öğrenme Hedefleri

Modül sonunda: temel bir Java programını sıfırdan yazabiliyorsun, parametrelerin metoda nasıl geçtiğini (pass-by-value semantiği) anlıyorsun, String'in neden immutable olduğunu ve bunun pratik sonuçlarını açıklayabiliyorsun, derlenmiş bir dilin yorumlanan bir dilden (örn. JavaScript) farkını kavramsal olarak ifade edebiliyorsun.

### 3. Öğrenme Sırası

Tipler/değişkenler → operatörler → kontrol akışı → döngüler → diziler → metodlar → String derinlemesine → temel I/O. Ön koşul: Faz 0'ın tamamlanmış olması (ortamın çalışıyor olması).

### 4. Mini Egzersizler

1. Klasik FizzBuzz (1'den 100'e, 3'e bölünenlerde "Fizz", 5'e bölünenlerde "Buzz", her ikisine de bölünenlerde "FizzBuzz")
2. Komut satırından çalışan basit bir hesap makinesi (dört işlem + geçersiz girdi kontrolü)
3. Bir tam sayı dizisinde en büyük ve en küçük elemanı bulan program
4. Bir kelimenin/cümlenin palindrome (düz okunuşu ile ters okunuşu aynı) olup olmadığını kontrol eden program
5. Öğrenci notlarını bir dizide tutup ortalama, en yüksek ve en düşük notu hesaplayan program

### 5. Git Kullanımı

Bir `java-practice` reposu aç (veya `learning-log` içinde bir klasör). Her egzersiz için ayrı, anlamlı bir commit at (`feat: fizzbuzz cozumu`, `feat: palindrome kontrolu`). Henüz branching zorunlu değil ama her commit'in tek bir mantıksal değişikliği temsil etmesine özen göster — bu, Modül 0.2'de öğrendiğin disiplini gerçek pratiğe dökmen demek.

### Kazanılan Yetenekler
Temel Java programları yazabilme, kontrol akışı ve döngü mantığını kurabilme, pass-by-value ve String immutability kavramlarını açıklayabilme.

### Öğrenilen Teknolojiler
Java (temel sözdizimi).

### Git Becerileri
Anlamlı, atomik (tek konuya odaklı) commit atma alışkanlığı.

### Yapılan Projeler
5 mini egzersiz (henüz portföy projesi değil, temel pratik).

### Bir Sonraki Modüle Hazır Olma Kriterleri
Yukarıdaki 5 egzersizi başka kaynağa bakmadan (ilk denemede zorlanman normal, ama çözebiliyor olman gerekiyor) tamamlayabiliyorsun; `for` ile `while` arasında ne zaman hangisini seçeceğini açıklayabiliyorsun.

### 🎓 Senior Notları
- **⚠️ Sık Yapılan Hatalar:** String karşılaştırmasında `==` kullanmak (`.equals()` yerine) — referans mı içerik mi karşılaştırdığını karıştırmak; `double` ile para hesabı yapıp yuvarlama hatası almak (parada `BigDecimal` kullanılır); döngüde String'leri `+` ile birleştirip gereksiz nesne üretmek (`StringBuilder` varken); off-by-one (bir fazla/eksik) döngü hataları.
- **🎤 Mülakat Soruları:** "`==` ile `.equals()` arasındaki fark nedir?" / "String neden immutable'dır, avantajı nedir?" / "Java'da pass-by-value mı pass-by-reference mi vardır?" (cevap: her zaman pass-by-value, ama referans tipinde değerin kendisi bir referanstır) / "`int` ile `Integer` arasındaki fark, autoboxing nedir?"
- **🔧 Kötü Kod → Refactor Pratiği:** Bana "bu modül için kötü kod ver" de; sana iç içe geçmiş `if`'ler, `==` ile string karşılaştırması ve magic number'larla dolu bir hesap makinesi/FizzBuzz çözümü vereyim; sen temizle, ben review edeyim.

---

## Modül 1.2 — Nesne Yönelimli Programlama (OOP)

### Neden Bu Modülü Öğreniyorum?

Gerçek dünya sistemleri (kütüphane, görev yönetimi, e-ticaret) karmaşıktır; bu karmaşıklığı yönetmenin bir yolu gerekir. OOP'nin çözdüğü problem tam olarak bu: veriyi ve o veri üzerinde işlem yapan davranışı bir arada modelleyerek karmaşıklığı yönetilebilir parçalara bölmek. Alternatif bir paradigma olan prosedürel programlama (örn. C) veri ve davranışı ayırır; fonksiyonel programlama (Java 8+'ın bir kısmı da buna kayar) ise değişmezliği ve yan etkisiz fonksiyonları önceler. Java, OOP üzerine kurulu ve **Spring Framework'ün dependency injection mekanizması doğrudan OOP'nin interface/polymorphism kavramlarına dayanır** — bu yüzden burayı sağlam öğrenmeden Spring'e geçmek, temelsiz bina inşa etmek gibidir.

Önemli bir uyarı da burada başlıyor: OOP her zaman doğru çözüm değildir. Derin inheritance hiyerarşileri (3-4 seviye `extends` zinciri) gerçek projelerde bakım kâbusuna dönüşür — bunu Faz 11'de SOLID ve Design Patterns'te "composition over inheritance" prensibiyle düzelteceğiz, ama tohumunu şimdi atıyoruz.

### 1. Öğrenilecek Konular

- Sınıf (class) ve nesne (object) ayrımı, constructor (yapıcı metod), `this` kullanımı, constructor overloading
- Encapsulation: erişim belirleyiciler (`private`, `protected`, `public`), getter/setter mantığı (ve bunun her alana otomatik uygulanmaması gerektiği — "anlamlı encapsulation")
- `static` ile instance üyeler arasındaki fark, ne zaman `static` kullanılır
- Inheritance: `extends`, `super`, method overriding vs. overloading farkı
- Polymorphism: runtime'da hangi metodun çalışacağına nasıl karar verildiği (dynamic dispatch)
- Abstraction: abstract class ile interface arasındaki kritik fark — ne zaman hangisi seçilir (Spring'in interface'e bu kadar bağımlı olmasının nedeni burada netleşecek)
- `equals()`, `hashCode()`, `toString()` sözleşmeleri — neden override edilir, override edilmezse ne ters gider (örn. `HashSet` içinde "aynı" nesnelerin neden tekrar eklenebildiği)
- Composition vs. inheritance — "has-a" ile "is-a" ilişkisi arasındaki fark

### 2. Öğrenme Hedefleri

Modül sonunda: birbiriyle ilişkili birden fazla sınıftan oluşan küçük bir domain modelleyebiliyorsun; bir durumda interface, başka bir durumda abstract class seçmenin gerekçesini açıklayabiliyorsun; `equals()`/`hashCode()`'u doğru override edebiliyorsun; "neden composition genellikle inheritance'a tercih edilir" sorusuna örnekle cevap verebiliyorsun.

### 3. Öğrenme Sırası

Sınıf/nesne/constructor → encapsulation → static vs. instance → inheritance → polymorphism → abstract class → interface → `equals()`/`hashCode()`/`toString()` → composition vs. inheritance (sentez).

### 4. Mini Egzersizler

1. Bir `Animal` sınıf hiyerarşisi: `Dog` ve `Cat` sınıfları `makeSound()` metodunu override etsin, polymorphism'i bir `Animal[]` dizisi üzerinden göster
2. Bir `Shape` interface'i tanımla (`calculateArea()`), `Circle` ve `Rectangle` sınıflarıyla uygula
3. Encapsulation prensiplerine uygun bir `BankAccount` sınıfı: bakiye negatif olamaz iş kuralını constructor ve metodlarda koru (doğrudan alan erişimi yasak)
4. Bir `Person` sınıfı için `equals()`/`hashCode()` override et, sonra bunu bir `HashSet<Person>` içine koyarak "aynı" kişilerin tekrar eklenip eklenmediğini test et
5. (Sentez egzersizi) Yukarıdaki `BankAccount`'u, doğrudan inheritance kullanmadan, composition ile bir `TransactionLogger`'a sahip olacak şekilde genişlet

### 5. Git Kullanımı

`feature/oop-pratikleri` branch'i aç. Her tamamlanan egzersiz için ayrı semantic commit (`feat: animal hiyerarsisi`, `feat: bankaccount encapsulation`). Bitince GitHub'da kendine bir PR aç, PR açıklamasında hangi OOP prensibini nerede uyguladığını yaz (bu, gerçek bir code review alışkanlığının başlangıcı), sonra **squash merge** ile main'e birleştir — Modül 0.2'de öğrendiğin squash merge'ü burada ilk gerçek bağlamında kullanıyorsun.

### Kazanılan Yetenekler
Domain modelleme, doğru abstraction seçimi (interface vs. abstract class), `equals`/`hashCode` sözleşmelerini doğru uygulama, composition ile tasarım yapabilme.

### Öğrenilen Teknolojiler
Java (OOP).

### Git Becerileri
Feature branch açma, PR açıp kendi kendine review yapma, squash merge.

### Yapılan Projeler
5 OOP egzersizi (mini ölçek, ama gerçek tasarım kararları içeriyor).

### Bir Sonraki Modüle Hazır Olma Kriterleri
Bir senaryo verildiğinde interface mi abstract class mı kullanacağına gerekçeli karar verebiliyorsun; `equals`/`hashCode` override etmeden bir nesneyi `HashSet`'e koymanın neden riskli olduğunu açıklayabiliyorsun; en az bir egzersizinde inheritance yerine bilinçli olarak composition seçtiğini gösterebiliyorsun.

### 🎓 Senior Notları
- **⚠️ Sık Yapılan Hatalar:** Her alana otomatik getter/setter üretip encapsulation'ı sözde bırakmak (anlamsız "anemic" model); derin inheritance zincirleri kurmak (`extends` üstüne `extends`); `equals()` override edip `hashCode()`'u unutmak (sözleşme ihlali, HashMap/HashSet'te bug); interface yerine concrete sınıfa bağımlılık (Spring DI'ı zorlaştırır); `protected` alanları gereksiz yere public davranışa açmak.
- **🎤 Mülakat Soruları:** "Abstract class ile interface arasındaki fark, ne zaman hangisi?" / "Polymorphism runtime'da nasıl çalışır (dynamic dispatch)?" / "`equals()` ve `hashCode()` sözleşmesi nedir, biri olmadan diğeri neden yetmez?" / "Composition'ı inheritance'a neden tercih ederiz?" / "Method overloading ile overriding farkı?"
- **🔧 Kötü Kod → Refactor Pratiği:** Bana "kötü OOP örneği ver" de; sana 4 seviye derin inheritance zinciri, `hashCode()`'suz `equals()` ve her alanı public olan bir domain modeli vereyim; sen composition'a çevir, encapsulation'ı düzelt, ben senior gözüyle review edeyim.

---

# Devam Planı

Bu doküman v2'ye güncellendi — dış review sonrası eksikler eklendi. Şu an detaylı olan kısım hâlâ Faz 0 + Faz 1'in ilk iki modülü; geri kalanı sen yaklaştıkça açılacak. Sırada şunlar var:

- **Hemen sıradaki (Faz 1'in kalanı):** Modül 1.3 (Collections & Generics), 1.4 (Exception Handling), 1.5 (Java 8+ Modern Özellikler), 1.6 (Concurrency), **1.7 (DSA & Big O — yeni, mülakat için kritik)**, **1.8 (Debugging — yeni)**, **1.9 (JVM Temelleri — yeni)**
- **Sonrasında:** Faz 2 (Veritabanı ve SQL, N+1 + isolation level dahil) — tam detaylı
- **Sonra:** Yeni **Faz 3.5 (HTTP & Web Temelleri)**, ardından Faz 4 (Spring Framework — programın en kritik bölümü) ve **Proje Checkpoint 1**'in tam spesifikasyonu (iki repo için detaylı görev tanımı, README şablonu, kabul kriterleri)
- Devamında her faz ve her proje checkpoint'i, sen o noktaya yaklaşırken tam detayıyla ve **🎓 Senior Notları bloğuyla** eklenecek
- **Faz 14 ve İkinci Aşama içeriği:** sen ilk işi bulduktan sonra, beraber yeni bir planla detaylandırılacak

**Nasıl devam edelim?** Bana şu an şunu söyleyebilirsin:
- *"Devam et, Modül 1.3'ten itibaren detaylandır"* → hemen bir sonraki bölümü yazarım
- *"Önce Faz 0 ve Faz 1'i bitireyim, sana haber veririm"* → sen ilerlerken ben beklerim, geri geldiğinde bu dokümanı güncellerim
- *"X konusunu anlamadım, farklı şekilde anlat"* → o konuyu farklı bir açıdan, ek örneklerle yeniden işlerim
- *"Şu modül için kötü kod ver, refactor edeyim"* → 🎓 Senior Notları pratiğini başlatırız

Bu doküman senin ilerlemenle birlikte büyüyecek bir kaynak — ne zaman dönersen, olduğun yerden devam edeceğiz.
