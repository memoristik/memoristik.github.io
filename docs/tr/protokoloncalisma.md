# Protokol Ön Çalışması

Halihazırda kullanımda olan farklı protokol ve altyapıların, oluşturulacak çalışma grupları içerisindeki tartışmalar ve verilen ortak kararlar doğrultusunda çeşitli düzenlemeler ve eklemeler yapılarak kullanıcılar için daha kullanışlı ve güvenli hale getirilmesi düşünülmektedir. 

İlk aşamada ele alınacak 3 temel konu için öneriler şu şekilde:

- ## Dijital Kimlik Veritabanı (diDb)

    [W3C](https://www.w3.org/) tarafından da onaylanmış ve desteklenmekte olan ["Merkeziyetsiz Kimlik(did)"](https://www.w3.org/TR/did-core/) standardı, hazırlanacak olan bu veritabanının temel düşüncesini oluşturmaktadır.

    Memoristik projesinin önem verdiği konulardan birisi olan "minimum miktarda ve hızlı veri aktarımı" sebebiyle, mevcut "did" yapısı üzerinde bazı değişiklikler yapılabilir, metin tabanlı JSON yerine kullanım sırasında Protobuf ya da alternatif sistemlere geçilebilir.

    Gerçek kişi ve kurum kimlikleri için oluşturulacak veritabanı Blokzincir üzerinde, diğer her şeye ait kimlikler Merkle Ağacı üzerinde tutularak birbirleriyle iletişimleri sağlanacaktır.
    (Kişiler için Blokzincir tercih edilmesinin sebebi ["Sabit Kimlik ve Giriş Kartı"](#sabit-kimlik-giris-kart) kısmında açıklanıyor. Tartışma ve Çalışma Gruplarından çıkacak karara göre değişiklik yapılabilir.)

    Herhangi bir nesne ya da konu için, "eşsiz" bir kimlik numarasının belirlenecek olan standartlara göre oluşturulmasının sağlanması öncelikli konulardan birisi.

    "Git"[^1] üzerinden örnek verilecek olursa,

    [^1]: "Git", üzerinde yapılabilecek bazı değişiklik ve eklemelerle kullanıma neredeyse hazır gibi görünüyor, proje veritabanı için farklı bir Merkle Ağacına karar verilecek olursa bile HASH'leme altyapısı kullanılabilir durumda. Kimlik numarası vermek konusundaki asıl amaç güvenlik olmadığı ve herkes tarafından deşifre edilebilir olacağı için daha basit MD5 gibi çözümler bile kullanılabilir. Önemli olan konu çakışmanın engellenmesi.

    > "Doctor Who" -> "33f7107b0566df9c4500ba05a32bd78a0360e2a1"

    şeklinde sabit bir örnek kimlik numarası oluşturabiliriz.

    Elde ettiğimiz bu kimlik numarası, "kendi başına ve eşsiz" bir şekilde açıkta duruyor ve içeriğine katılacağı her yerde kullanılabilir durumda, diDb'ye eklendikten sonra, artık konu ya da nesneyle ilgili bütün referanslar kolaylıkla bu kimlik numarasına bağlanabilir.

    Aynı örnek üzerinden giderek biraz genişletelim:

    "Liste" formatında bazı "Başlık"lar oluşturalım ve kimlik numaralarını yine git'ten alalım,

    > "(List) Language" -> "f595be573723b6e7aadccc36192fcc33a8a5547b"
    >
    > "(List) Lisan" -> "e8a2b31e17e7a279fad38eec9c3acd3508d3aecd"
    >
    > "(List) TV Series" -> "e01648324ef822e2713fe01dc3a56b2b0e00912d"
    >
    > "(List) TV Dizileri" -> "c01830f432a3accafa83bcc548ec947b10caa91e"
    >
    > "(List) Soundtrack" -> "099287d6456509d139a65c4e07cf1abb56873721"
    >
    > "(List) Book" -> "68c2d94ee2d424a3204c2366bd5180de67972c17"
    >
    > "(List) Broadcasting Platform" -> "c6baf462ed7f13c32e92c48163eec785a4f3c4a3"

    İlk aşamada kullanabileceğimiz birkaç kimlik numarasını ekleyelim,

    > "English" -> "fb54c64e2c893efc35e89dfdf1192d380cba9fb5"
    >
    > "Türkçe" -> "b51132e2ea5faf8253cc594cd14a245dfb68a197"


    Artık elimizde kimlik numaralarıyla hızlıca sorgulayabileceğimiz bir miktar veri var. Merkle Ağacı yapısını kullanarak da bunları birbirine eşitleyebilir (Language=Lisan) ve listelerin altına eklemeler (Language/Lisan -> English/Turkish -> TV Series/TV Dizileri) yapabiliriz.

    Kullanıcılar elimizdeki bu içeriklerle şuna benzer takipler yapabilir duruma gelir:

    - "Doctor Who"yla ilgili bir gelişme olunca,
    - Yeni bir Film Müziği albümü çıkınca ya da Doctor Who'nun film müziği listesine yeni parça eklenince,
    - Yeni bir kitap yayınlanınca ya da sadece Doctor Who'yla ilgili bir kitap yayınlanınca,
    - Takip ettiğim yayın platformuna yeni bir film/dizi gelince,
    - Doctor Who, takip ettiğim yayın platformlardan birisine eklenince,
    - Türkçe bir içerik yayınlanınca,
    - TV Dizilerine Türkçe bir yayın eklenince,
    - Takip ettiğim bir sanatçının Soundtrack albümü çıkınca,
    vb.

    Buraya kadar verdiğimiz örnekler çoğunlukla kullanıcıların veri eklemesine fazla ihtiyaç duymayan, sabit ve net içeriklere sahip "Çekirdek Veritabanı" işlemlerinden oluşuyor.

    Kimlik numaraları üzerinden içerik erişiminin sağlanması, dağıtık yapıdaki sunuculara kolayca bölünebilmesi açısından önemli. Böylelikle metin içeren bütün verilerin alınmasına gerek kalmadan daha hızlı erişim sağlanabilir.

    Kullanıcılar, Çekirdek Veritabanında oluşturulmuş kimlik verilerini ya da hazırlanmış listeleri kullanarak kendi özel ya da halka açık listelerini oluşturabilirler, başkalarının hazırladığı listelerden faydalanabilirler.

    Örnek olarak,

    - Kişisel film, müzik, kitap vb. listeler,
    - Aktiviteler,
    - Belirli bir konu üzerinde odaklanmış listeler,
    - Diğer listelere yeni maddeler eklemek,
    - Kullanmak istediği kadar veriyi süzüp, yeni listeler oluşturabilmek,

    Hem kim tarafından hazırlandığı hem de çakışmaların önlenmesi amacıyla, kullanıcılar tarafından oluşturulan aynı isimli listeler, farklı kimlik numaralarına sahip olur,

    > (Memoristik Kullanıcısı) TV Dizileri" -> "3388ccadcaecab0383f1cb9bc6a8e9e3043063b7"

    (Daha fazla örnek kullanım için: [Kullanım Alanları ve Örnekler](/tr/ornekler/))

- ## diDb Adaptasyonu

    Projenin en önemli amaçlarından birisi, farklı platformlar üzerinden diDb sistemine erişimin sağlanabilmesi için var olan protokol ve servisler üzerinde geliştirmeler yapmak.

    Kullanılabilecek teknik altyapılar sistem geliştiricileri tarafından tartışılıp kararlaştırılmak üzere, örnek bir kullanım şuna benzer bir şekilde olacak:

    Markdown/HTML Dokümanlar üzerinde,

    **{@kişiadı}** : Sabit Kimlik edinmiş ve diDb kaydı olan kişiler için,
    
    **{@#kişiadı}** : {@kişiadı} kimliğine sahip kişilere hashtag oluşturmak için,
    
    **{#konu}** : Herhangi bir konuda hashtag oluşturmak ve diDb bağlantısıyla (destekleyen) platformların hepsinden veri alabilmek için,
    
    **{!konu}** : diDb'deki Çekirdek Veritabanında oluşturulan ana başlıklara erişmek için,

    Örneğin, bir kullanıcı kullandığı yazılımında ayarlamalar yaptıktan sonra, herhangi bir web sitesi üzerinde karşılaştığı şöyle bir cümle için,

    "{#doctorwho} 60 yaşında..."

    Sayfada oluşacak link kişiye özel hale gelir, diDb'den örneğin sadece "yayınlandığı platform, yayın günü" bilgilerini listeleyebilir, kullandığı yazılıma bağlı olarak, link üzerinde tıkladığında pop-up açılabilir.

    Ya da {!music:band:megadeth:tour:türkiye} gibi bir sorguyu bildirimlerine ekleyip bekleyebilir.

    Son örnekteki ilk 3 veri Çekirdek Veritabanından, "tour" verisi de farklı bir listeden alınıyor olabilir. "Tour" verilerinin kaynağını da kullanıcı kendisi belirleyebilir, direk olarak gruptan ya da güvendiği bir hayrandan alabilir örneğin.


- ## Dijital Kullanıcı Kimliği Veritabanı - diDMe

    **(Sabit Kimlik & Giriş Kartı, Kişiler & Gruplar)**

    Blokzincir teknolojisiyle birlikte hızlanan "Dijital Cüzdan" ve "Doğrulanabilir Kimlik"ler, şimdilik kısıtlı bir şekilde, kullanıldığı ortam sınırları içerisinde çalışmakta.

    Memoristik Projesinin diDMe alt projesinin amacı, var olan cüzdan ve doğrulanabilir kimlikleri, güvenli bir şekilde ve her platformdan erişilebilir biçime getirmek ve kullanıma sokmak. Şimdilik Güvenlik ve Kolay erişim gibi sebeplerle Blokzincir üzerinde geliştirilmesi düşünülmekte.

    diDMe veritabanı üzerinde oluşturulacak olan bu kimlikler, Anonim kalabilme hakkını da içererek, talep eden yerlere sadece gerektiği kadar bilgi gönderecek ve tamamen kullanıcının kendi kontrolünde olacak.

    Güvenlik konusu bu veritabanı için çok önemli olduğundan, kullanıma hazır hale gelene kadar sadece bu konuda yoğunlaşmış bir çalışma grubu tarafından yürütülmesi planlanıyor.

    Amaçlanan hedefe ulaşıldığı zaman, kullanıcılar kendilerine ait her türlü içerik ve veriyi, eş zamanlı olarak sistemi kullanan bütün platformlarda senkron olacak biçimde, kendi istedikleri doğrultuda düzenleyebilecekler.

    Örnek bir kullanım olarak,

    - Telefon No
    - E-posta
    - Web adresi
    - Avatar
    - Ev adresi
    - CV
    vb. kişisel her türlü veriyi tutabilirler.

    İletişim kurmak istedikleri kişiye sadece {@kullanıcı adı} bilgisini vermeleri yeterli olacak. Bu veriler üzerinde her türlü kısıtlama, karşısındaki kişiye belli bir miktarını göstermek gibi yetkileri olacak. Yapılan herhangi bir değişiklik, karşı tarafa eş zamanlı olarak yansıyacak.

    Örneğin, e-posta ya da telefon numarası değiştiğinde, kimseye haber vermek zorunda kalınmayacak.

    Aynı şekilde, farklı sosyal medya hesapları için her birisini tek tek yazmak gerekli olmayacak.

    Kurumlar için de farklı kullanımlar olabilir, {@kurum adı/iletişim}, {@kurum adı/müşteri temsilcisi} şeklinde müşterileri için hızlı erişimler sağlanabilir.

    diDMe sistemi kullanılarak ve güvenilir kurumlar aracılığıyla onaylanmış gerçek kimlikler, diDb ile iletişim kurularak kendi isimleriyle oluşturulmuş hashtag'ler de birbirine bağlanabilir, kullanıcıların kendisini takibi kolaylaşır.

    > (diDMe)/{@memoristik} <-> (diDb){#memoristik}


