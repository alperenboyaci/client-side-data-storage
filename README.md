# Client Side Data Storage

Web sayfaları neticesinde oluşan bir kısım kişisel bilgi ve yerel kullanıma uygun verilerin kullanıcı tarafında saklanmasına yönelik teknikler ve araçlar oldukça eskiye dayanmaktadır. Ancak bu teknikler ve araçların ihtiyaçları tam karşılayamamasının yanı sıra HTML5 standratlarının devreye girmesi developer dünyası için yeni ve farklı imkanları ortaya çıkarmıştır.

Artık bir web developer, amaç ve kullanım itibarı ile farklılıkları bulunan bu teknikleri/araçları kendi ihtiyaçlarına göre optimize ederek kullanım imkanına sahip bulunmaktadır.
- Cookies
- LocalStorage & SessionStorage
- IndexedDB
- WebSQL

İnternet tarayıcınızın gelişmiş seçeneklerini (F12) kullanarak  bulunduğunuz websitesi/sayfası üzerinde bunları kolayca görebilirsiniz.

![](http://i68.tinypic.com/wbry1z.png)


------------
#### 1. Cookies (Çerezler)
Client tarafında veri barındırmanın en eski yöntemlerinin başında Cookie kullanımı gelmektedir. Ancak bir kısım güvenlik zaafiyetleri oluşturması ihtimali nedeniyle, HTML5  sonrası yerini LocalStorage & SessionStorage bırakmaya başlamıştır. Ancak bununla birlikte tüm internet tarayıcıları halen cookie desteğine aynen devam ettirmektedir.

Otomatik olarak kullanım süresinin dolmasının istediğimiz zaman olarak ayarlanabilmesi en önemli avantajı olarak kabul edilmektedir. 

Developer tarafından expire tanımlaması yapılarak ve kullanıcı tarafından internet tarayıcısı özellikleri, cookie manager, vb. kullanılarak istenilen zaman silinebilmektedir.

#### 2. LocalStorage &  SessionStorage

#### 3. IndexedDB

#### 4. WebSQL (sqLite)



------------


##### Karşılaştırma Tablosu
![](http://i68.tinypic.com/18fy3p.png)


------------
##### !!!  Önemli
Kişisel verilerin güvenliği ve korunması hususlarındaki bilinçlenmeye paralel olarak her geçen gün yeni kuralların ve düzenlemelerin hayata geçirilmesini zorunlu hale gelmektedir.

Bu nedenle  kullanım için yasal düzenlemeleri ve sektörel kuralları takip etmek gerekmektedir.
- [6698 sayılı Kişisel Verilerin Korunması Kanunu](http://www.mevzuat.gov.tr/MevzuatMetin/1.5.6698.pdf "6698 sayılı Kişisel Verilerin Korunması Kanunu")
- [EU - 95/46/EC - Data Protection Directive (DPD)](https://ec.europa.eu/info/law/law-topic/data-protection_en "EU - 95/46/EC - Data Protection Directive")
