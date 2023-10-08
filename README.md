# Version_Kontrol_Sistemleri

![version_kontrol](https://github.com/Teknoloji-Filozofu/Version_Kontrol_Sistemleri/blob/main/_media/version_kontrol.webp)

Version Control System bir döküman (yazılım projesi, ofis belgesi…) üzerinde yaptığımız degişiklikleri adım adım kaydeden ve isterseniz bunu internet üzerinde depoda (respository) saklamamızı ve yönetmemizi sağlayan bir sistemdir.

### **Neden Versiyon Kontrolü?**
- Projelerde birden fazla kişi çalıştığını düşünürsek, gelişimin hızlanmasını sağlar.
- Projede geliştirme yaparken, bulunduğumuz konuma nereden geldiğimizi anlamak için eski ve yeni kodumuz arasında karşılaştırma yapmamızı sağlar.
- Projede hatayla karşılaştığımız durumlarda eski kod kaydına dönmemizi sağlar.
- Açık kaynaklı projeler baz alınarak geliştirilecek yeni projelerde, süreci kolaylaştırmayı sağlar.

## **Versiyon Kontrol Sistem Tipleri**

### Local Versiyon Kontrol Sistemleri
En eski versiyon kontrol sistemi yaklaşımıdır. Çalıştığımız projemiz ve yaptığımız değişiklikler kullanıcı makinası üzerindeki veritabanında tutulur. Her yapılan commit bir versiyon olarak tutulur ve commit değerine hash ataması yapılarak her versiyon birbirinden ayırt edilmektedir. Ayrıca versiyon görüntüleme imkanını sağlar. Ancak bu sistemde sadece bir kullanıcı etkin bir şekilde çalışabilir.

![local_vcs](https://github.com/Teknoloji-Filozofu/Version_Kontrol_Sistemleri/blob/main/_media/local_vcs.webp)

### Merkezi Versiyon Kontrol Sistemleri
Birden fazla kişinin bir proje üzerinde etkin çalışması için ortaya atılmış versiyonlama sistemidir. **CVS, SVN** birer merkezi versiyon kontrol sistemleridir. Bu sistemde proje ortak bir respository’de tutulur ve birden fazla geliştirici aynı respository üzerinde checkout ve commit işlemlerini gerçekleştirmektedir. Bu yöntemde herkesin projeye katkı sağlamasının yanısıra bazı ciddi sorunları vardır. Tek merkezli sunucu 1 saatliğine arızalanması durumunda, kullanıcılar 1 saat boyunca çalışmalarını veya çalıştıkları projenin sürümlenmiş kopyalarını kaydetmeleri mümkün olmayacaktır.

![merkezi_vcs](https://github.com/Teknoloji-Filozofu/Version_Kontrol_Sistemleri/blob/main/_media/merkezi_vcs.webp)

### Dağıtık Versiyon Kontrol Sistemleri
Merkez versiyon sistemlerinin geliştiricilerin offline çalışabilmesi ve respository’nin zarar görmesi durumunda geri getirme gibi eksikliklerinden dolayı ortaya atılmış bir versiyon sistemidir. **Git**, **Mercurial**, **BitKeeper**… dağıtık versiyon sistemleri örnek gösterilebilir. Bu sistemlerde merkezi bir respository olmayıp, proje üzerinde çalışan her makine, projenin kopyasını kendi yerel bilgisayarında tutmaktadır. Geliştiriciler proje üzerinde değişiklik yapmak veya proje geçmişine göz atmak istediklerinde, uzak depo ile iletişime geçmek zorunda değildir. Sunuculardan biri çökerse ve o sunucu üzerinde ortak çalışma yürüten sistemler varsa, geliştircilerden birinin projeyi sunucuya geri yükleyerek sistem kurtarılabilir.

![dağıtık_vcs](https://github.com/Teknoloji-Filozofu/Version_Kontrol_Sistemleri/blob/main/_media/da%C4%9F%C4%B1t%C4%B1k_vcs.webp)

### Dağıtık Sistemler İle Merkezi Sistemler Karşılaştırması
Dağıtık versiyon kontrol sistemleri (DVCS), merkezi sistemlerin tercih ettiği istemci-sunucu (client-server) yerine sürüm kontrolü için eşler arası (peer-to-peer / P2P) yaklaşımını temel alır. Dağıtık sistem repository (yazılım/dosya havuzu) senkronizasyonunu eş paylaşımı üzerinden pacth’leri değiştirerek gerçekleştirir. Kod tabanının tek bir merkezi sürümü yoktur; bunun yerine, her kullanıcı işleyen bir kopyaya ve tam bir değişiklik geçmişine sahiptir.

Dağıtık sistemlerin (DVCS) merkezi sistemlere (CVCS) kıyasla sundukları avantajları ve dezavantajları şu şekilde listeleyebiliriz ;
- Network bağlantısı olmasada kullanıcılar ilgili repo üzerinde çalışabilirler,
- DVCS ortak işlemleri (commits, işlem geçmişinin görüntülenmesi ve değişikliklerin geri alınması gibi) daha hızlı işler, çünkü merkezi bir sunucuyla iletişim kurmaya gerek yoktur. DVCS bu iletişime değişikliklerin diğer ortaklarla (peer) paylaşılacağı zaman ihtiyaç duyar.
- Özel (private) çalışma alanları oluşturmak mümkündür. Böylece, kullanıcılar paylaşmak istemedikleri taslaklardaki (draft) değişiklikleri de kullanabilirler.
- Üzerinde çalışılan kopyalar aynı zamanda uzak yedek (remote backup) görevi görürler. Bu sayede herhangi bir donanım hatasından (kırılma noktası gibi) etkilenmezler.
- Farklı geliştirme modelleri (development branches, commander/kieutenant model gibi) kullanılanibilir.
- Projenin release version’unun kontrolü merkezi olarak gerçekleştirilebilir.
- FOSS (Free and Open-source Software / Özgür ve Açık Kaynaklı Yazılım) yazılım projelerinde, liderlik çatışmaları veya tasarımdaki anlaşmazlıklar nedeniyle durdurulmuş bir proje kolaylıkla çatallanarak (fork) sürdürülebilir.

Elbette her şey toz pembe değil. Dağıtık sistemlerin sundukları avantajların yanı sıra bazı dezavantajları da mevcut ;
- Bir repo’nun checkout edilmesi merkezi sistemlere göre daha yavaştır, çünkü tüm dallar (branch) ve revizyon geçmişi varsayılan olarak yerel makineye kopyalanır.
- Dağıtık sistemlerin, çoğu merkezi sistemin önemli bir parçası olan ve grafik dökümanlar, kompleks binary dosyaları, XML paketleri (ofis dokümanları, PowerBI dosyaları vb.) gibi birleştirilemeyen dosyalar (non-mergeable binary files) için kullanılabilen kilitleme mekanizmalarına (locking mechanism) sahip olmaması önemli bir eksikliktir.
- Kod tabanı geçmişinin tamamının tam bir kopyası olması demek aynı zamanda her kullanıcı için ek depolama alanı demektir.

## Popüler Versiyon Kontrol Sistemleri

Geliştirilen sistemler çerçevesinde kişisel ve/veya kurum ölçeğinde pek çok alternatif değerlendirilebilir ve süreç içerisinde de pazarda yeni oyuncular olacağı ve yeni sistemlerin de geliştirileceği aşikar. Bu anlamda, en azından bugün için referans olması amacıyla aşağıda öne çıkan bazı sistemlere yer vermeye çalıştım.

#### CVS Version Control (Concurrent Versions System)
[CVS](https://www.nongnu.org/cvs/) en eski sürüm kontrol sistemlerinden biridir ve hem ticari hem de açık kaynaklı geliştiriciler arasında iyi bilinen bir araçtır. Diğer versiyon kontrol sistemleri (SVN, Git vb.) CVS özellikleri / eksiklikleri temel alınarak geliştirilmişlerdir.

#### Git-GitHub
![Github - Git](https://github.com/Teknoloji-Filozofu/Version_Kontrol_Sistemleri/blob/main/Git-Github.md) yapısını kullanan bir platform. Platform olmasının sağladığı avantajlar ve sunduğu ek özellikler çerçevesinde yazılım ekipleri tüm kod değişiklik geçmişini takip edebilmekte, sürümler arasında geçiş yapabilmekte ve paylaşabilmekte. Ek olarak, açık projeler kullanıcılar tarafından fork edilebilmekte, çalışmalara dahil olabilmekte ve repo’ları edinebilmekteler.

#### GitLab
[GitLab](https://gitlab.com/), GitHub alternatifi olarak değerlendirilebilir. Ancak, GitHub’a kıyasla daha yeni bir platform olmasına karşın çok daha kapsamlı özellikler sunduğu söylenebilir.

#### Mercurial
[Mercurial](https://www.mercurial-scm.org/about), `git` yerine kendi yapısını kullanmaktadır ve `git`‘in öne çıkan alternatiflerinden biri olarak nitelendirilebilir. GitHub ve GitLab’ın sunduğu platform özellikleriyle kıyaslandığında Mercurial’ün ayrıca yapılandırılması gerekir.

#### PerForce
[Perforce](https://www.perforce.com/), sürüm kontrolü yeteneklerini HelixCore aracılığıyla sunar. HelixCore, ekip işbirliğini öne çıkaran tek bir platformla birlikte gelir ve hem merkezi hem de dağıtılmış geliştirme iş akışlarını destekler.

#### Apache Subversion
[Apache Subversion](https://subversion.apache.org/), bir diğer açık kaynaklı versiyon kontrol sistemidir ve CollabNet tarafından geliştirilmiştir. Apache Subversion, hem açık kaynak camiasında hem de kurumsal ölçekte pek çok ihtiyaca cevap verebilecek özellikler sunmaktadır.

#### Beanstalk
[Beanstalk](https://beanstalkapp.com/), tarayıcı ve cloud temelli yapısı ile remote çalışanlar için değerlendirilebilecek ideal seçeneklerden biri olarak nitelendirilebilir. Tüm işlemler (code, commit, review, deploy vb.) tarayıcı üzerinden gerçekleştirilmektedir. Hem Git hem de SVN’yi destekler ve yerleşik analitik özellikleri ile birlikte gelir.

#### AWS CodeCommit
[AWS CodeCommit](https://aws.amazon.com/tr/codecommit/), özel Git repolarının yönetiminde kullanılan bir versiyon kontrol sistemidir. Kodlar AWS ortamında barındırılır. Amazon Web Servisleri (AWS) altındaki diğer ürünlerle sorunsuz bir şekilde entegre olur ve bu nedenle özellikle AWS kullanıcıları için değerlendirilmektedir.

#### Azure DevOps Server
[Azure DevOps Server](https://visualstudio.microsoft.com/tr/tfs/), eski adı ile Microsoft Team Foundation Server (TFS), Microsoft tarafından geliştirilen ve diğer Microsoft ve Azura ürünleri ile kolaylıkla entegre olabilen bir versiyon kontrol sistemidir. Özellikle kurumsal ölçekteki ihtiyaçlara yönelik çözümler sunar. Azure DevOps (VSTS) cloud temelli çözümlere sahipken, Azure DevOps Server (TFS) kişisel barındırma özellikleri ile öne çıkar.

#### Bitbucket
[Bitbucket](https://bitbucket.org/), `git` temelli bir versiyon kontrol sistemidir. Atlassian yazılım paketinin bir parçasıdır ve bu sayede HipChat, Jira ve Bamboo gibi diğer Atlassian servisleri ile kolayca entegre edilebilir.

#### Mercurial
Dağıtık bir versiyon kontrol sistemidir. **Git** ile benzer özelliklere sahiptir.

#### TFS (Team Foundation Server)
Microsoft tarafından geliştirilmiş bir merkezi versiyon kontrol sistemidir.

#### Bazaar
Dağıtık bir versiyon kontrol sistemidir. Özellikle açık kaynaklı projelerde kullanılır.

#### Darcs
Dağıtık bir versiyon kontrol sistemidir. Basitliği ve kullanım kolaylığı ile bilinir.