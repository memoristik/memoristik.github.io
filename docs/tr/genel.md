# Genel Bakış

## **Amaç**
Web3, Blokzincir & Merkle Ağacı vb. teknolojiler kullanılarak çok katmanlı ve açık kaynaklı bir altyapının oluşturulması ve üzerinde:

- Kullanıcıların kendisine ait ve kendi ürettiği her türlü veri üzerinde hak sahibi olmasının ve bu verilerin güvenliğinin, devamlılığının sağlanması,
- Verilerin serileştirilerek birbirleriyle iletişim kurabilmesinin sağlanması ve bütün verilere kolay, hızlı ve güvenli bir şekilde erişilebilmesi,
- (Kullanıcıların kendisine ait kişisel veya ürettiği) verilerin kaynağının ve doğruluğunun saptanabilmesi.

---

## **Motivasyon**

Memoristik Projesi, senelerdir hem kullanıcı hem geliştirici olarak karşımıza çıkan bazı problemlerin çözüm yollarını bulmak, kişisel haklarımızı korumaya çalışmak, elimizin altındaki teknolojiyi daha verimli kullanmak, üretilen verilerin paylaşımını ve işlevselliğini artırmak gibi sebeplerle ortaya çıktı.**

Bu ve benzeri amaçlarla, çalışma gruplarının ve ortamının oluşturulması, farklı alanlarda geliştirilmiş açık kaynaklı projelerin bir araya getirilmesi, kullanıma ve amaca uygun şekilde değişiklikler yapılması, eksik olanların tamamlanması, RFC'lerin hazırlanması ve ___yeni bir İnternet Protokolünün kullanıma sokulması___ planlanmaktadır.

Teknik altyapının tamamlanması ve oluşturulan protokolün kullanılmaya başlanması sonrasında, farklı gruplar kurularak Kimlik, Akademi, Medya, Sürdürülebilirlik, İletişim, Güvenilir & Takip Edilebilir Kaynaklar gibi konularda eğitim ve veri paylaşımı çalışmalarının başlatılması, protokolün verimli kullanımı için uygulamalar hazırlanması öngörülmektedir.

---

## **Öncelikli Problemler**

İnternet kullanımı sırasında alışkanlık haline gelmiş ve olmazsa olmaz olarak düşünülen pek çok konu kullanıcılar açısından olası riskler taşıyor, problemler yaşatıyor, kullanımı zorlaştırıyor.

Protokol altyapısı oluşturulurken öncelik verilecek problemlerden bazılarını özetleyecek olursak:

- ### Alan Adları

    Ücretli, zaman süreli olduğu ve çoğunlukla kiralama yöntemiyle kullanıldığı için uzatılmayan alan adları üzerinde duran veriler belirli bir süre sonra erişilemez duruma gelebilir. Kullanıldığı süre içerisinde dışarıdan bu alan adına verilen referans linkleri, üzerinde kullanılan e-posta gibi servisler yine bu duruma bağlı olarak geçersiz hale gelecektir.

    Ülke yönetimleri, sabit birkaç sunucuya bağlı olarak çalışan alan adı sistemi üzerinden vatandaşlarının bu hizmetlere ve verilere erişmesini kolaylıkla engelleyebiliyor.


- ### Eski, Kirli, Doğrulanmamış Veri ve Kaynaklar

    Arama motorları, kullanıcıyı güvenilir ve doğru bilgiye ulaştırma konusunda çoğu zaman yetersiz kalmaya başladı. Artık geçerliliği kalmamış, yenilenmiş veriler kullanıcıların kendileri tarafından elenip doğrulanmak zorunda. Elde edilen bir bilginin kaynağının doğrulanması da ek bir işlem olarak yine kullanıcı tarafından yapılmak zorunda.

    Günümüz algoritmaları ve yapay zeka destekli çözümleri henüz bu konuları çözmekten uzaktalar.

- ### Veri Deposu

    Merkezi sunucularda tutulan veriler, sunucu sahiplerinin müsaade ettiği ölçüde var olmaya devam edebiliyor. Özellikle, kullanıcılara sahip ve onlar tarafından üretilen veriler her an ortadan kaldırılabilme tehlikesiyle yüz yüzeler. Şirketler ve kişiler, kendilerine ait olan verilerin geleceğine, sunucu sahipleri kadar karar verici durumda değil.
    
    Bu duruma en güzel örnek olarak kapatılan onlarca Google servisi verilebilir.

- ### Kullanıcı Giriş İşlemleri, Kişisel Veriler, E-Posta

    Merkezi sunuculara sahip pek çok kurum ve şirket kullanıcılardan elde edebileceği maksimum seviyede kişisel bilgiyi toplamaya çalışıyor ve kendi veritabanlarını oluşturuyor. Kullanıcılar bu hizmetleri kullanabilmek için en iyi ihtimalle, diğer bilgilerini vermek zorunda kalmasalar bile, e-posta adresleriyle giriş yapıyor. Günümüzde ise bu daha da artarak devam etmeye başladı ve kullanıcılar herhangi bir sitedeki herhangi bir makaleyi, blog yazısını okuyabilmek için bile e-posta adresleriyle giriş yapmak zorunda bırakılıyor. Toplanan bu kişisel verilerin ne şekillerde kullanılabileceğine ise kullanıcılar kendi adlarına karar veremiyor.
    
    Ayrıca, alternatif ve daha güvenli iletişim araçlarının geliştirilmiş olmasına rağmen, e-posta altyapısının uzun zamandır gelişim sürecinin yavaşlamış olması, güvenlik açıklarının olması ve yine de bu tür sebeplerle kullanılmaya mecbur kalınması diğer bir problem. (Ek olarak, yukarıda bahsi geçen alan adı problemi e-posta sistemini de etkiliyor.)

- ### Takip Edilebilirlik

    Pek çok kişi farklı konularda yapmak istediği işlemler için farklı sistemleri kullanmak zorunda olduğundan takip edilebilirliği, diğer kullanıcılarla iletişimi zorlaşıyor. Örneğin, akademik ortamdan bir kişinin çalışmaları kullanıcılar tarafından takip edilmek istendiği zaman, çalışmaların yer aldığı her bir ortamın ayrı ayrı bulunması gerekebiliyor. Ya da yine aynı şekilde akademik bir konu üzerindeki takip edilmek istenen gelişmeler apayrı ortamlar tek tek taranarak ulaşılabilir oluyor. Tek bir ortam içerisinde "hashtag" benzeri uygulamalarla bir miktar çözüme ulaşılsa da yeterli gelmediği çok durum var.

- ### Tekrarlanan Gereksiz Veriler

    Özellikle "ürün"ler konusunda, aynı veriler o ürünün yer aldığı her farklı ortam içerisinde tekrarlanıyor. Örneğin, bir ürüne ait teknik bilgiler, aynı içeriğe sahip olmasına rağmen, o ürünün satışının yapıldığı sitelerde her seferinde baştan giriliyor.

- ### Platform Bağımlılıkları

    Kullanıcıların birbirleriyle paylaşmak istedikleri bazı veriler, farklı seçenekler olmasına rağmen, kullanıcıları belli başlı platformları kullanmaya zorluyor. Örneğin, paylaşılan bir müzik listesi, aynı içeriklere sahip bir başka platformdan açılamıyor. Herkesin kullanımı için oluşturulan veri setleri oluşturulduğu ortam içerisinde sınırlı kalıyor, bir başka ortama aktarılabilse bile üzerine dışarıdan yapılabilecek katkılar ortak bir platformda kolayca birleşemiyor.
    
    Aynı veriler üzerinde yapılacak ortak çalışmalar kişinin istediği, rahat ettiği bir ortamda devam edemeyebiliyor.

- ### Veri İşleme, Kullanma Yetkileri, Erişim Hakları

    Çoğunlukla bağımsız, bireysel kişiler tarafından ortaklaşa oluşturulan veriler, farklı kurum ve şirketler tarafından sahipleniliyor ve bu bilgiyi ortaya koyan kişilerin özgürce kullanmasına izin verilmiyor. Farklı ortamlarda ve farklı şekillerde ortaya çıkan bu veriler karşılaştırmalı olarak ele alınamaz duruma geldi.
    
    Önceden hiç olmazsa API'ler aracılığıyla yapılabilir durumda olan bu işlemler gün geçtikçe bahsedilen ortam sahipleri tarafından engellenir duruma geldi.

- ### Doğrulanabilir Kimlik Bilgileri, Anonimlik Hakkı

    İnternet kullanıcılarının en önemli haklarından birisi istediği zaman anonim kalabilmektir. Hem Anonimlik Hakkı hem de gerektiği durumlarda kullanılabilecek olan gerçek kimlik kullanımı henüz tam çözüme ulaşabilmiş ve netleşmiş konular değil.
    
    Kimlik Doğrulama Yöntemleri ve doğrulayanların güvenilirliği öncelikli olarak çözülmesi ve netleştirilmesi gereken konular.
    
    Ayrıca, doğrulanmış ve güvenilirliği ortaya koyulmuş bilgilerin ne kadarı, kimlerle, ne şekilde paylaşılacak soruları da tam olarak kesin cevaplara ulaşmış değil.

- ### Trol Hesaplar ve Dolandırıcılık

    Özellikle finans konularında, karşısındaki kişilerin gerçekliğini ve güvenilirliğini tespit edecek yeterli teknik bilgiye sahip olmayan kullanıcılar, dolandırılma tehlikesiyle daha çok karşı karşıya geliyorlar.
    
    Herhangi bir konuda karşılarındaki kişilerin trol hesap olup olmadığı, yönlendirildikleri web sitelerinin güvenilir olup olmadığı, aldıkları e-posta’ların kimlerden geldiği gibi konuların çözüme ulaştırılabildiği belirgin yöntemler netleşmiş değil.

- ### Bildirimler & Haber Kaynakları

    Kullanıcılar herhangi bir konuda bildirim alabilmek için servis sahibinin tercih ettiği farklı sosyal medya hesapları, mesajlaşma ve sohbet uygulamaları, SMS, E-posta sistemlerinden birisini ayrı ayrı kullanmak zorunda kalıyor. Bazı bildirimlere erişebilmek için kişisel telefon numaralarının verilmesi bile gerekebiliyor.

