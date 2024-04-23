#  Java Spring REST API

### Proje Kurulumu
Projeyi öncelikle forklayın ve clone edin.
Daha sonra projeyi IntellijIDEA kullanarak açınız. README.md dosyasını dikkatli bir şekilde okuyarak istenenleri yapmaya çalışın.
Proje sayımız ilerledikçe proje yönetimimizi kolaylaştırmak adına projelerimizi belli klasör kalıplarında saklamak işimizi kolaylaştırmak adına iyi bir alışkanlıktır.
Örnek bir Lokasyon: Workintech/Sprint_1/Etud.

### Hedeflerimiz:

### Secure Rest Api

 ### Başlangıç
 * Proje içerisinde ```Spring Web```, ```Spring Boot Security``` dependency mutlaka olmalı.
 * Maven dependency management sistemini kullanarak tüm dependencyleri install edin.
 * Uygulamanızı  ```9000``` portundan ayağa kaldırın.
 * Bir banka için rest api dizayn etmeniz istenmektedir.
 * schema olarak ```bank``` isminde bir schema oluşturun ve tüm veritabanı tablolarınızı bu schema içerisinde tanımlayın.

### Amaç
 * Spring Boot Security ile yapılabilen security türlerini tanımak ve uygulamak
 
 ### Görev 1
 * main metodunuzun olduğu paket altında ```controller```, ```config```, ```entity```, ```dao```, ```service``` isminde 5 adet daha paket oluşturunuz.
 * Project Lombok'u dependency olarak uygulamanıza ekleyin.
 * ```entity``` paketinin altına JDBCAuthentication için ```Member``` adında bir sınıf tanımlayınız. İçerisinde instance variable olarak ```id, email, password``` isminde 3 tane değişken oluşturun.
 * ```entity``` paketinin altına JDBCAuthentication için ```Role``` adında bir sınıf oluşturunuz içerisine ```id, authority``` adında 2 field ekleyiniz.
 * Member ve Role arasında many-to-many bir ilişki tanımlamalısınız.
 * ```entity``` paketinin altına JDBCAuthentication için ```Account``` adında bir sınıf tanımlayınız. İçerisinde instance variable olarak ```id, name``` isminde 2 tane değişken oluşturun.
 * ```dao``` paketinin altına ```MemberRepository``` adinda bir interface tanımlayınız. İçerisinde emaile göre kullanıcıları almalı.
 * Lombok ve JPA annotation larını uygulayarak bütün sınıfı bir veritabanı tablosu olucak şekilde işaretleyiniz.
 * ```application.properties``` dosyanızı kullanarak veritabanı bağlantınızı kurun.
 * Spring uygulamasının veritabanı loglarını açarak veritabanına yolladığınız her sorguyu inceleyin.
 * dto paketi altında ```RegisterResponse``` ve ```RegistrationMember``` adında 2 tane record tanımlayın.
 * ```RegisterResponse``` AuthController sınıfında register metodunun dönüş tipi olmalıdır. 
 * ```RegistrationMember``` AuthController sınıfında register metodunun parametresinin tipi olmalıdır.

### Görev 2
 * Service ve Dao paketi katmanlarını yazmalısınız. 
 * Account objesi MVC kurallarına uygun olarak veritabanı işlemlerini yapabilmeli.
 * CRUD işlemlerini Service katmanı karşılayabilmeli

 ### Görev 3
 * ```controller``` paketi altında ```AccountController, AuthController``` adında 2 tane controller yazmalısınız.
 * AccountService sınıfını AccountController sınıfı altında ```Dependency Injection``` yöntemini kullanarak çağırınız.
 * İlk olarak Member kaydebilmek için [POST]/workintech/auth/register şeklinde bir endpoint tanımlayın ve buradan bir adet user rolünde bir adet admin rolünde kullanıcı tanımlayın.
 * Amacımız CRUD işlemlerini tanımlayan endpointler yazmak.
 * [GET]/workintech/accounts/ => tüm account listini dönmeli.
 * [GET]/workintech/accounts/{id} => İlgili id deki account objesini dönmeli. 
 * [POST]/workintech/accounts => Bir adet account objesini veritabanına kaydeder.
 * [PUT]/workintech/accounts/{id} => İlgili id deki account objesinin değerlerini yeni gelen data ile değiştirir.
 * [DELETE]/workintech/accounts/{id} => İlgili id değerindeki account objesini veritabanından siler.
 

### Görev 4
 * ```application.properties``` dosyasına kendi kullanıcı isminizi ve şifrenizi giriniz.
 * Basic auth yöntemini kullanarak sistemdeki tüm endpointlere ulaşmayı deneyiniz.
 * JDBCAuthentication yöntemi ile  tüm endpointlere ulaşmayı deneyiniz. 
 * [POST]/workintech/auth/register => member tablosunda yeni bir kullanıcı oluşturmalı.
 * [GET] requestlerine ```user ve admin``` rolündeki kullanıcılar request atabilmeli.
 * [POST], [PUT], [DELETE] requestlerine sadece ```admin``` rolündeki kullanıcılar request atabilir.
 * OAuth2 yöntemini kullanarak Github ile uygulamanızdaki [GET]endpointlerine ulaşmayı deneyiniz.
