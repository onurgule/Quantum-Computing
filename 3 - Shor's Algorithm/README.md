# Shor's Algorithm - Shor Algoritması

Shor Algoritması, kuantum bilgisayarlarda çok çok çok büyük sayıları kolaylıkla asal çarpanlarına ayıran, kriptolojiyi altüst eden bir algoritmadır.
1994'te geliştirilmiştir(Çok yakın bir tarih.).
Eğer kuantum bilgisayarları yeterince kullanışlı hale gelirse bugün çok iyi diye kullandığımız şifreleme yöntemleri güvenliği sağlayamayacak.
Shor Algoritması, O(n!) olan uygulamayı O(n^2)'ye dönüştüren bir algoritmadır.

#Örnek:
RSA-768 şifreli bir metin nasıl çözülür?
Normalde bu şifreli metni kırmak için klasik bir bilgisayarın 1500 yıl~ açık durması gerekmektedir ya da 1500 bilgisayarın 1 yıl~.

RSA-768 normalde 768 karakterden oluşur. Ben burda çözümlemeye çalışmaktan ziyade Shor Algoritmasını uygulayarak nasıl olacağını gösteceğim.


Şifreli metnimiz: 314159253589793238... diye devam eden 768 karakterden oluşsun buna N diyelim..

Şifreyi çözümlememiz için bu çok çok büyük N sayısının asal çarpanlarını bulmamız gerekiyor. Ancak asal çarpanlarını değil de başka çarpanlarını bulup asal çarpanlarına doğru Euclid's Algorithm (Öklid Algoritması) sayesinde gidebiliriz.

Algoritmayı çalıştıralım.

Rastgele olarak 123123123 diye bir sayı üretelim ve buna g diyelim.

N,g olarak iki sayımız mevcut.

Öklid Algoritmasına göre: g^p = m*N + 1 olacak şekilde bir p sayısı mevcuttur.

p sayısını bulmak çok zor. Biraz daha açalım:

g^p - 1 = m*N

(g^(p/2) - 1^(p/2))*(g^(p/2) + 1^(p/2)) = m*N

p'yi bulduk diyelim...

(g^(p/2) - 1^(p/2)) ve (g^(p/2) + 1^(p/2)) sayılarını bulmuş oluruz.

Bunlar N'nin katları olmalı, ancak olmak zorunda da değil. 

Burdan sonra devreye Kuantum Fourier Dönüşümü giriyor.

(g^x = m*N + r ; g^(x+p) = m*N + r ; g^(x+2p) = m*N + r)

N ve (g^(p/2) +- 1^(p/2))'yi Kuantum Fourier Dönüşümüne girdi olarak veriyoruz ve çıktı olarak bize tam olarak gerekli asal çarpanları veriyor.

Bu asal çarpanlar ile metni çözümleyebiliyoruz.



#Basitleştirilmiş Sayısal Örnek:

Şifreli metnimiz N = 15 olsun.

Rastgele ürettiğimiz sayı g = 7 olsun.

p'yi bulmamız gerekiyor, küçük sayı olduğu için zor olmayacaktır.

g^p = m*N+1 

7^2 = 3*15+4

7^3 = 22*15+13

7^4 = 160*15+1 (+1'i bulduğumuza göre p = 4 çıkacaktır.)

(g^(p/2) - 1^(p/2))*(g^(p/2) + 1^(p/2)) = m*N

(7^(4/2) - 1^(4/2))*(7^(4/2) + 1^(4/2)) = m*15

50*48 = 15m

Burada 50 ve 48 sayıları 15'in katı değiller.

Kuantum Fourier Dönüşümü uygulayalım.

15,50 -> QFT -> 5 (15 ve 50 sayılarını Kuantum Fourier Dönüşümü sistemine veriyoruz ve çıktı olarak bize tam ihtiyacımız olan sayıyı veriyor. Biraz karmaşık bir sisteme sahip.)

15,48 -> QFT -> 3

3 ve 5 sayılarını verdi! Şifreli metnimiz olan N=15'in asal çarpanları 3 ve 5.

Bu sayede şifreli metni çözümleyebiliyoruz.



Not: Rastgele seçtiğimiz g sayısının doğru çıkma olasılığı 37.5%'dir. 10 kez rastgele seçtiğimizde olasılık 99%'ye kadar çıkmaktadır. 

Bu işlemler klasik bilgisayarlarda bu kadar hızlı yapılamamaktadır. (3 ve 5 verme olayı, p sayısını bulma)



N: Şifreli metin (crypted text)

g: Rastgele seçilen sayı (random guess)

p: tekrar eden sayı (repeating property)







