# Client-Side Data Storage

Web sayfaları neticesinde oluşan bir kısım kişisel bilgi ve yerel kullanıma uygun verilerin kullanıcı tarafında tarayıcı içinde saklanmasına yönelik teknikler ve araçlar (IE UserData, FlashStorage,DojoStorage vb) oldukça eskiye dayanmaktadır. Ancak bu teknikler ve araçlar ihtiyaçları tam karşılayamadığı için arayışlar devam etmiş ve HTML5 standartlarının devreye girmesi developer dünyası için yeni ve farklı imkanları ortaya çıkarmıştır.

HTML5 ile birlikte Client Side veri depolama ile birlikte yeni bir takım fırsatlar ve avantajlar da ortaya çıkmıştır.
- Server tarafında sistem ve kaynak verimliği
- Client tarafında daha yüksek performans ve erişilebilirlik
- Mobile ve Offline sistemlerin geliştirilmesi/desteklenmesi/yaygınlaştırılması
- Sandbox yapısı ile daha yüksek güvenlik

Artık bir web developer, amaç ve kullanım itibarı ile farklılıkları bulunan bu teknikleri/araçları kendi ihtiyaçlarına göre optimize ederek kullanım imkanına sahip bulunmaktadır.
- Cookies
- LocalStorage & SessionStorage
- IndexedDB
- WebSQL

Tarayıcınızın gelişmiş seçeneklerini (F12) kullanarak  bulunduğunuz websitesi/sayfası üzerinde bunları kolayca görebilirsiniz.

![](http://i68.tinypic.com/wbry1z.png)


------------
#### Nerelerde kullanılıyor ?
Developer tarafından ihtiyaç duyulan yerde ve şekilde kullanılabilir olmakla birlikte genel olarak aşağıdaki alanlarda yoğun bir Client-Side Data Storage yapısının kullanıldığını gözlemlemek mümkündür.
- Kullanıcı giriş ve erişim yönetimi
- Kişiselleştirilmiş içerik yönetimi ve sunumları
- Form veri girişleri
- Alışveriş sepetleri
- Analytics veri toplama
- Reklamlar ve reklam takipleri
- Bankacılık ve kredi kartı işlemleri (sadece SessionStorage)

------------
#### 1. Cookies (Çerezler)
Client tarafında veri barındırmanın en eski yöntemlerinin başında Cookie kullanımı gelmektedir. Ancak bir kısım güvenlik zaafiyetleri oluşturması ihtimali nedeniyle, HTML5  sonrası yerini LocalStorage & SessionStorage bırakmaya başlamıştır. Ancak bununla birlikte tüm internet tarayıcıları halen cookie desteğine aynen devam ettirmektedir.

Otomatik olarak kullanım süresinin dolmasının istediğimiz zaman olarak ayarlanabilmesi en önemli avantajı olarak kabul edilmektedir. 

Developer tarafından expire tanımlaması yapılarak ve kullanıcı tarafından internet tarayıcısı özellikleri, cookie manager, vb. kullanılarak istenilen zaman silinebilmektedir.

#### 2. LocalStorage &  SessionStorage

LocalStorage, tarayıcı içindeki verilerin anahtar / değer çiftlerini (key-value) şeklinde saklanmasını sağlayan Web Storage API'nin bir türüdür.

LocalStorage kullanımında çakışabilecek anahtar kelimelerin kullanılmaması ve değerlerin hash olarak kullanılması da faydalı görülmektedir.

Teknik olarak tekil dizeler (anahtar/değer) olarak  kullanılsa da JSON şeklinde daha karmaşık ve kapsamlı şekilde verilerin depolanmasını da sağlamaktadır.

Klasik yapı/yaklaşım aşağıdaki şekilde iken;
```csharp
//Write
localStorage.setItem('name', 'Alperen');
localStorage.setItem('city', 'Ankara');

//Read
console.log('name: ' + localStorage.getItem('name'));
```
JSON yapısı bu şeklinde kullanılabilir. 
```csharp
 //Write
    var user = { name: 'Alperen', city: 'Ankara' }
    localStorage.setItem('user', JSON.stringify(user));
    
// Read
    console.log( JSON.parse(localStorage.getItem('user'))); 
```
Ancak büyük JSON veri kulanımında Memory/DOM performansını az da olsa etkileyebileceği unutulmamalıdır.

Daha büyük/fazla ve güvenli bir veri depolama imkanı sağlaması avantajının yanında sadece String değerlerin saklanabilmesi gibi bir dezavantajı da bulunmaktadır.

Şu anda modern/yeni versiyon tüm internet tarayıcıları LocalStorage & SessionStorage desteğini sunmaktadır.

SessionStorage,  tüm özellikleri itibarı ile LocalStorage ile aynı niteliktedir, aradaki fark ise SessionStorage kullanımı durumunda depolanan veriler tarayacı veya tarayacı tab'ının kapatılması ile birlikte kendiliğinden silinmesidir. (temporary)

#### 3. WebSQL (sqLite)
[WebSQL Teknik Standartları](http://www.w3.org/TR/webdatabase/"WebSQL Teknik Standartlar")


> Bugün için tüm tarayıcılar tarafından desteklenmesine rağmen tarayıcı geliştiricileri tarafından artık WebSQL için yeni geliştirmeler yapılmamaktadır. Bu nedenle yeni projelerde WebSQL yerine IndexedDB yapısının kullanılması tavsiye edilmektedir.




#### 4. IndexedDB
[IndexedDB Teknik Standartları](http://www.w3.org/TR/IndexedDB/ "IndexedDB Teknik Standartları")



------------


#### Karşılaştırma Tablosu
![](http://i68.tinypic.com/18fy3p.png)
> Not :  WebSQL yerini IndexedDB'ye bıraktığı için tabloda yer almamaktadır.

######  Ekstra Not
İhtiyaçlarınız ve fırsatlar açısından, bunlara ilaveten Cache (CacheStorage-ApplicationCache ) yapısının da incelenmesi yararlı olabilir.

------------
##### !!!  Önemli
Kişisel verilerin güvenliği ve korunması hususlarındaki bilinçlenmeye paralel olarak her geçen gün yeni kuralların ve düzenlemelerin hayata geçirilmesini zorunlu hale gelmektedir.

Bu nedenle  kullanım için yasal düzenlemeleri ve sektörel kuralları takip etmek gerekmektedir.
- [6698 sayılı Kişisel Verilerin Korunması Kanunu](http://www.mevzuat.gov.tr/MevzuatMetin/1.5.6698.pdf "6698 sayılı Kişisel Verilerin Korunması Kanunu")
- [EU - 95/46/EC - Data Protection Directive (DPD)](https://ec.europa.eu/info/law/law-topic/data-protection_en "EU - 95/46/EC - Data Protection Directive")



