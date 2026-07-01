# 📖 Yazılım Sözlüğü — Efe'nin Öğrenme Defteri

> Bu dosya, öğrendiğim **komutları ve kavramları** basit açıklamalarla biriktirdiğim kişisel sözlüğüm. Unuttukça buraya bakarım. İlerledikçe büyüyecek.
>
> **Kapsam:** terminal komutları, git komutları, kavramlar (JDK/JVM gibi), araçlar. Kodun kendisi ve syntax açıklamaları burada değil — onları kendi `.java` dosyalarımda açıklama satırlarıyla tutuyorum.
>
> **Son güncelleme:** Faz 0 + Modül 1.1 (değişkenler, isimlendirme kuralları, primitive vs reference tipler)

---

## 🖥️ Terminal (PowerShell) Komutları

Bunlar işletim sistemiyle (Windows) konuşmak için kullandığım komutlar. Terminal = bilgisayara yazıyla komut verdiğim siyah pencere.

| Komut | Açılımı / Anlamı | Ne işe yarar |
|-------|------------------|--------------|
| `cd <klasör>` | **c**hange **d**irectory | Bir klasörün içine girer (klasör değiştirir). Örn: `cd Documents` |
| `cd ~\Documents` | — | `~` = kullanıcı ana klasörüm. Yani Belgeler'e gider. |
| `mkdir <isim>` | **m**a**k**e **dir**ectory | Yeni bir klasör oluşturur. Örn: `mkdir learning-log` |
| `ls` | **l**i**s**t | İçinde bulunduğum klasörün içeriğini listeler (dosya/klasörleri gösterir). |
| `explorer .` | — | Windows dosya gezginini, **şu an bulunduğum klasörde** açar. `.` = "buradaki klasör". |
| `cat <dosya>` | con**cat**enate | Bir dosyanın içeriğini ekrana yazdırır. Örn: `cat ~/.ssh/id_ed25519.pub` |

**Faydalı kısayollar:**
- `.` → "şu an bulunduğum klasör"
- `~` → "kullanıcı ana klasörüm" (C:\Users\dalba gibi)

---

## 🔧 Git Komutları

Git = kodumun değişikliklerini takip eden, geçmişini tutan araç. GitHub = bu kodu internette sakladığım yer.

| Komut | Ne işe yarar |
|-------|--------------|
| `git config --global user.name "..."` | Git'e adımı tanıtır (bir kere yapılır). Commit'lerde kimin yazdığı görünsün diye. |
| `git config --global user.email "..."` | Git'e e-postamı tanıtır (bir kere yapılır). |
| `git init` | İçinde bulunduğum klasörü bir git deposuna çevirir. Gizli bir `.git` klasörü oluşur (git'in hafızası). |
| `git status` | Şu anki durumu gösterir: hangi dosyalar değişmiş, hangileri takip ediliyor/edilmiyor. **En çok kullanılan komut — git'in kafasını okumanın yolu.** |
| `git add .` | Tüm değişiklikleri "staging area"ya (sahneye) koyar. `.` = "buradaki her şey". "Bunları bir sonraki commit'e dahil edeceğim" demek. |
| `git commit -m "mesaj"` | Sahnedeki değişiklikleri kalıcı bir snapshot (anlık görüntü) olarak kaydeder. `-m` = mesaj. |
| `git branch -M main` | Ana branch'in adını `main` yapar (modern standart). |
| `git remote add origin <url>` | Yerel repomu GitHub'daki repoya bağlar. `origin` = GitHub'daki uzak reponun takma adı. |
| `git push` | Yerel commit'lerimi GitHub'a gönderir. (İlk seferde `git push -u origin main`) |
| `git pull` | GitHub'daki (uzaktaki) son hali bilgisayarıma çeker. `push`'un tersi. |

### Temel Git Döngüsü (her değişiklikten sonra)
```
git add .
git commit -m "mesaj"
git push
```
Bu üçlü, sürekli kullanacağım temel akış: değiştir → kaydet → gönder.

### Semantic Commit (anlamlı commit mesajları)
Profesyonel standart. Mesaja şu öneklerle başlanır:
- `feat:` → yeni özellik eklendi
- `fix:` → hata düzeltildi
- `docs:` → dokümantasyon değişikliği
- `refactor:` → kod düzenlendi (davranış değişmeden)
- `test:` → test eklendi/değiştirildi
- `chore:` → ufak bakım işleri

> **Not:** Commit mesajlarını İngilizce ve ASCII karakterlerle yazmak yaygın standarttır (Türkçe karakter bazı sistemlerde bozulabilir). Örn: `feat: add roadmap` ✅

---

## 🔐 SSH Kavramı

SSH = GitHub'a her seferinde şifre girmeden güvenli bağlanmamı sağlayan yöntem.

| Komut | Ne işe yarar |
|-------|--------------|
| `ssh-keygen -t ed25519 -C "email"` | Bir SSH key çifti oluşturur: **private key** (gizli, kimseyle paylaşmam) + **public key** (paylaşılabilir). |
| `ssh -T git@github.com` | GitHub bağlantısını test eder. "successfully authenticated" görürsem çalışıyor demektir. |

**Önemli kural:** Public key'i (`.pub` ile bitenı) GitHub'a koyarım, güvenli. Private key'i ASLA kimseyle paylaşmam.

---

## ☕ Java — Temel Kavramlar

### Java nasıl çalışır? (derleme zinciri)
```
.java dosyası   →  javac (derleyici)  →  .class (bytecode)  →  java/JVM  →  program çalışır
(yazdığım kod)                          (ara dil)                         (sonuç)
```

| Kavram | Anlamı |
|--------|--------|
| **JDK** | Java Development Kit. Java *geliştirmek* için gereken tam paket (derleyici + çalıştırıcı + araçlar). |
| **JRE** | Java Runtime Environment. Sadece Java programlarını *çalıştırmak* için yeterli olan kısım (geliştirmeye yetmez). |
| **JVM** | Java Virtual Machine. Bytecode'u benim işletim sistemime çeviren ve çalıştıran sanal makine. |
| **Compiler (Derleyici)** | Yazdığım insan-okuyabilir kodu (`javac`), bilgisayarın anlayacağı bytecode'a çeviren program. Kodda yazım hatası varsa, derleyici bunu yakalar ve hata verir. |
| **Bytecode** | `.class` dosyasındaki ara dil. Ne tam insan dili ne tam makine dili — JVM bunu okur. Java'nın "bir kez yaz, her yerde çalıştır" gücünün sırrı budur. |
| **`javac`** | Java derleyici komutu (kodu derler). |
| **`java`** | Java çalıştırıcı komutu (derlenmiş programı çalıştırır). |

> 📝 **Not:** Kodun *syntax* açıklamaları (örn. `println` ne yapar, `;` nereye konur, `class`/`main` ne demek) bu sözlükte değil, kendi `.java` dosyalarımda açıklama (comment) satırları olarak yaşıyor. Bu sözlük sadece **kavramları** tutar; kod ve kod açıklamaları repodaki Java dosyalarında.

### İsimlendirme Kuralları (Naming Conventions)
Java'da isimler belli bir geleneğe göre yazılır. Kod *çalışır* ama bu kurallara uymak profesyonellik göstergesidir (işe alımda fark eder).

| Kural | Nasıl yazılır | Nerede kullanılır | Örnek |
|-------|---------------|-------------------|-------|
| **camelCase** | İlk kelime küçük, sonraki kelimeler büyük başlar | Değişken ve metot isimleri | `ogrenciNotu`, `aracHizi`, `hesaplaToplam()` |
| **PascalCase** | Her kelime büyük başlar (UpperCamelCase) | Class isimleri | `OgrenciKaydi`, `Main`, `Variables` |

> Kural özeti: **değişken/metot → küçük harfle başla** (`int sayi`), **class → büyük harfle başla** (`class Sayi`).
> Ek ipucu: İsimlendirmede tek dil seç (hep Türkçe ya da hep İngilizce), karıştırma. Profesyonel projeler genelde İngilizce gider.

### Primitive Tipler vs Reference (Referans) Tipler
Java'da iki temel tip kategorisi var — **`String` neden büyük harfle başlıyor** sorusunun cevabı da burada:

| Kategori | Örnekler | Yazım | Ne olduğu |
|----------|----------|-------|-----------|
| **Primitive (ilkel)** | `int`, `double`, `char`, `boolean`, `byte`, `short`, `long`, `float` | küçük harf, dilin **anahtar kelimesi** | Class değil — dile gömülü en temel veri birimleri |
| **Reference (referans)** | `String`, `Integer`, `ArrayList`, ve yazdığım her class | **büyük harf**, PascalCase | Gerçek class'lar (`java.lang` paketinden ya da kendi yazdığım) |

> **`String` aslında bir class** (`java.lang.String`) — benim `public class Operators` yazmam ile aynı mantık. Java ona özel muamele yapıp tırnakla yazmama ve `+` ile birleştirmeme izin veriyor (operator overloading), ama arka planda gerçek bir nesne. İleride `Integer`, `Double` gibi primitive'lerin "wrapper class" (sarmalayıcı) karşılıklarını göreceğim — aynı mantığın devamı.

---

## 🛠️ Araçlar

| Araç | Ne işe yarar |
|------|--------------|
| **IntelliJ IDEA** | Java kodu yazdığım program (IDE). Kodu yazar, derler, çalıştırır — hepsini bir yerden. |
| **Git** | Kod değişikliklerini takip eden araç (komut satırından kullanırım). |
| **GitHub** | Kodumu internette sakladığım, paylaştığım platform. |
| **PowerShell** | Windows'ta komut yazdığım terminal. |
| **PATH** | İşletim sistemine "komutları nerede arayacağını" söyleyen ortam değişkeni. `java` komutunun her yerden çalışmasını sağlar. |
| **JAVA_HOME** | Java'nın kurulu olduğu klasörü gösteren ortam değişkeni. Birçok araç buna bakar. |

---

*Bu sözlük büyüyen bir doküman. Yeni bir komut/kavram öğrendikçe Claude'dan güncellenmiş halini isteyip buraya ekliyorum.*