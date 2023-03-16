# Linux İşletim Sistemlerine Giriş

## Linux nedir?

 Linux tek başına işletim sistemi değil çekirdektir. _**GNU/Linux**_ dediğimiz bütün aslında bir işletim sistemine karşılık gelir. GNU(GNU is Not Unix) ise Open Source araçlardır. Yani farklı dağıtımlarda Çekirdek yapısı dediğimiz Linux değişmezken yanındaki araçlar, arabirimler değişerek ihtiyaçlara göre farklı distrolar (dağıtımlar) oluşturuyor. Örneklendirecek olursak; siber güvenlikte kullandığımız Kali, Linux'un dağıtımı olan Debian'ın alt dağıtımıdır. Çekirdek kavramını biraz açarsak kullanıcının kullandığı araçlardan gelen emirleri donanıma yaptıran birim oluyor.

## Linux nasıl ortaya çıktı?

İlk UNIX sistemleri çıktığında lisans ücretlerinden dolayı kullanıcılar kendi işletim sistemlerini yazmaya başladılar. Linux da bunlardan biri aslında. Linus Torvalds tarafından UNIX'den esinlenerek yazıldı. MacOS da bir Unıx tabanlı işletim sistemidir, bu yüzden komut yapıları benzerlik göstermekte. Linux geliştirildiğinde içinde GNU dediğimiz araçları bulundurmuyordu. Daha sonra büyük topluluklara ulaşarak düzenlemelerle geliştirildi.

İhtiyaçlara göre GNU'larla farklı distrolardan bahsedecek olursak; örneğin serverlarda verim açısından grafiksel arayüze ihtiyaç duyulmazken ev, ofis kullanıcıları grafiksel arabirimlerini kullanıcıların rahat yönetebileceği şekilde seçerler.

### Peki neden LINUX?

- Burada Open Source olmasının aslında kullanıcıların özgür bi şekilde istedikleri yazılımları kullanıyor olmaları Linux'un ne kadar kullanışlı olduğunu gösteriyor.

- Derleyicilerle beraber gelmesi, karşılaştıracak olursak bu Windows'ta olan bir özellik değil.

- Terminal üzerinden istediğiniz paketi indirebilmeniz kolaylık sağlıyor. Apt-get install komutu burada bize yardımcı oluyor.

- Diğer işletim sistemlerinden daha güvenli olması.
  

  ![Linux Kernel Yapısı](https://developer.ibm.com/developer/default/articles/l-linux-kernel/images/figure2.jpg)

## Open Source (Açık Kaynak) Yazılımlar

***Open source kavramı tam olarak ne anlama geliyor?***
Linux'un kaynak kodlarının hepsi topluma açık halde bulunuyor, bu sayede farklı kullanıcılar kendilerine göre uyarlayıp geliştirmesine imkan sunuyor.
### Distrolar (Dağıtımlar)
https://distrowatch.com/ farklı distrolar  hakkında bilgi alabileceğiniz bir web sitesi.

Ben anlatımlar sırasında siber güvenlik alanında sıklıkla kullanılan Debian tabanlı _**"Kali Linux"**_ dağıtımı üzerinden ilerliyor olacağım.

## Çalışılacak Ortamlar


- **Sanal olarak kurulum (Vmware & Virtualbox):**

Sabit bir diske bağlamadan kendi işletim sisteminiz üzerinden kullanmanızı sağlıyor. vmware ve virtualbox gibi yazılımlar kullanabilirsiniz.

- **İkincil işletim sistemi olarak kurmak (Dualboot):**

İkinci bir işletim sistemi olarak bilgisayarınızda kullanabiliyorsunuz.

- **Live versiyon olarak kullanmak (USB):**

USB ile başlatıp bu disk üzerinden çalıştırmanızı sağlıyor.

- **Linux VPS aracılığı ile kullanmak:**

Uzaktaki bir sunucuya bağlanarak çalışabilirsiniz. Bu versiyonu ücretlidir.

## Shell Nedir?

Kullanıcı ile Kernel arasında bi aracı olarak görebiliriz. Çeşitli Shell programları vardır. Bunlardan biri de Bash. Bash ise kullanıcıyla Shell arasında iletişimi sağlayan komut arayüzüdür.

## Temel Komutlar

`setxkbmap tr`

Bu komut klavyenizi türkçe klavye yapmanızı sağlıyor. Her açtığınızda çalıştırmak zorunda kalmamanız için **Settings > Session and Startups > Application Autostart kısmından + butonundan her login olduğunda setxkbmap tr komutunu çalıştıran seçeneği oluşturmalısınız.** Yeniden login olduğunuzda komutunuz kendi kendine çalışacaktır.

İlk olarak kali versiyonunda gösteriyorum, hacking toolları için **sudo apt-get update** ve **sudo apt-get upgrade** komutlarını çalıştırmanız gerek. Burda sudo root kullanıcısı ile komutunuzu çalıştırmanızı sağlıyor, çünkü yapacağımız işlemler root kullanıcı yetkisini gerektiriyor. Yaptırdığımız işlemler ise versiyonumuza göre yenilenen toolları makinemize indirmemizi sağlıyor.


 `Pwd `   "Print working directory"→ bize hangi dizinde olduğumuzu gösterir 

 `ls` komutunu çalıştırıyorum → Bu dizinde klasör var mı görmek istiyorum 

`cd ..` ya da `..` komutlarını kullanıyorum → Kali dizininden geri home'a gitmek için

`cd /` → En alt dizine (kök ) tek seferde gitmek için

`mkdir xxx` →  dizin oluşturmak için

`rmdir xxx` → dizini silmek için

`cd ..` → kök dizinine gitmek için

`sudo touch xxx` → dosya oluşturmak için yine sudo ile çalıştımam gerek

`cat xxx` → içeriğini okumak için

`sudo nano xxx` → içine herhangi bir şey yazabilmek için 

## Dosya Taşıma ve Kopyalama Komutları 

`sudo cp xxx/home` → Touch xxx farklı bir dizine de koymak için

`mv xxx yyy` → xxx'i yyy dosyası haline getirir

## Dosya konumu bulma 

`locate shadow` → shadow dosyasının nerde olduğunu gösterir

`find "konum" -name "dosya adı" `→ dosyanın konumunu verir

**Grep**  komutu: 
logs adında bir dosyam olduğunu farz edelim, içinde INFO karakterleri geçen satırları bulmasını isteyeceğim, aşağıdaki komutu kullanıyorum:
`cat "logs" | grep INFO`
## Head ve Tail komutları
`head logs` →  ilk 5 satırı gösteriyor<br />
`head -n 15 logs` → ilk 15 satırı verecek<br />
`tail -n 15 logs` → sondan 15 satırı veriyor
## Kullandığınız işletim sistemini çekirdek sürüm bilgisini nasıl öğrenebiliriz?
`Uname `→ kullandığım işletim sistemini gösterir.<br />
`Uname -a` → işletim sistemiyle ilgili detaylı bilgi verir.<br />
`Cat /etc/*-release `→ Çekirdek sürüm bilgisi için komut:
## Help ve MAN PAGE 
Zaman zaman unuttuğumuz ya da ne işe yaradığını hangi parametrelerle nasıl seçeneklendirdiğimizi görebilmek için kullandığımız komutları göreceğiz.
Örneğin ls komutunun ne işe yaradığını unuttuk.<br />
`Man ls` → Hangi parametreleri aldığını ne işe yaradığını görüyorum.<br />
`Man history` → bu komutla eski komutlarımı görebiliyorum, bu komut hakkında bilgi almış oldum.<br />
**Help** komutu: 
 man page'in özetlenmiş hali gibidir.<br />
 Bu komutu siber güvenlikte kullanılan nmap toolu ile görelim:<br />
`nmap --help `
## Prosesde çalışan programları ve programların ne kadar cpu kullandığını gösteren komutlar
`top` → ne kadar süredir çalışıyor hangi kullanıcılar tarafından çalıştırılıyor<br />
`ps `→ prosesleri listeliyor tümünü görmek için<br />
`ps -aux` <br />
`ps -aux | grep root` → grep komutuyla sadece root olarak çalışan programları gördük 
## Dosya indirme komutları 
Wget komutu yanında dosya url adresi ile girilmesi gerek, site url si yazarsanız web sitesinin kaynak kodlarını indirecektir.<br />
git clone komutunda ise indireceğiniz github reposu urlsi komutun yanında bulunmalı<br />
`Wget` https://www. <br />
`Git clone `https://github.com/ 
## Ping Komutu
`ping Google.com` → istek atmış oluyorum ve sitenin ip adresini görüyorum.
Aynı zamanda şunu anlıyorum: Geri dönüt alıyorum ki bu site ayakta, sürekli ping atmaya devam ediyor.<br />
`Ping -c 10 Google.com ` → 10 tane ping atacaktır
## Kısayollar
Normalde yaptığımız Control C-V gibi kısayollar terminal üstüne geçtiğimizde Control-Shift-C oluyor. Ve ileri geri gelmek için Mouse kullanamıyorsunuz, bu yüzden kısayolları kullanmaya alışmak gerekiyor. Aynı makine üzerinde bu şekilde oluyor. Sanal makinede çalışıyorsanız kendi sisteminizden sanal makineye bir şey kopyalamanız gerektiğinde de makinenin ayarlar kısmından değiştirmeniz gerekebiliyor, dikkat edelim.
Sistemden default gelen kısayolları da aslında değiştirebiliyorsunuz. Terminal'in üst kısmında yer alan sekmelerden **File > Preferences > Shortcuts** diyerek değiştirebilirsiniz.<br />
**Ctrl + A** imleç satır başına gider.<br />
**Ctrl + E** imleç satır sonuna gider.<br />
**Ctrl + P** önce çalıştırılmış komut gösterilir.<br />
**Ctrl + N** sonra çalıştırılmış komut gösterilir.<br />
**Alt + B** sola doğru(geri) bir kelime kadar imleç kayar.<br />
**Alt + F** sağa doğru(ileri) bir kelime kadar imleç kayar.<br />
**Ctrl + F** imleç bir karakter ileri gider.<br />
**Ctrl + B** imleç bir karakter geri gider.<br />
**Ctrl + XX** geçerli imleç konumundan, imleç satır başına geçer.<br />
**Ctrl + L** ekran temizlenir ve imleç en üst satıra çıkar yani clear komutu ile aynı işlemi yapar.<br />
**Alt + D** imleçten sonraki kelimeyi siler.<br />
**Ctrl + U** imlecin solundaki her şeyi siler.<br />
**Ctrl + K** imlecin sağındaki her şeyi siler.<br />
**Ctrl + Y** kesilmiş olan son metni ekrana yapıştırır.<br />
**Esc + T** imleçten önceki iki kelime yer değiştir.<br />
**Ctrl + H** sola doğru tek tek karakterleri siler.(yani Backspace gibi davranır)<br />
**Alt + U** imlecin başladığı yerden sözcüğün sonuna kadar bütün karakterleri büyük harf yapar.<br />
**Alt + L** imlecin başladığı yerden sözcüğün sonuna kadar bütün karakterleri küçük harf yapar.<br />
**Alt + C** imlecin üstünde bulunduğu karakteri büyük harf yapar.<br />
**Ctrl + C** komutu durdurur/keser.<br />
**Ctrl + R** daha önce kullanılmış olan komutlar arasında arama yapma ve o komutu tekrardan kullanma imkanı sağlar.<br />
**Ctrl + Z** çalışan süreci arka plana atar ve duraklatır.<br />
**Ctrl + D** Veri girişinin sonunu temsil eden yani mevcut terminali sonlandırır.<br />
**TAB** Otomatik tamamlamayı sağlar. Konsol üzerinden bir kısmını yazmış olduğunuz, dosya, dizin ve komut türevi her türlü ifadeyi otomatik tamamlar. Ayrıca iki kez üst üste basıldığında da yazmış olduğunuz ifade ile başlayan tüm içeriği listeler.<br />
**Crtl + Alt + (f1, f2, f3, f4, f5, f6)** kısayolu ile komut satırını açabiliriz.
