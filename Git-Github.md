# Git

## Git nedir ?
**Git**, bir versiyon kontrol sistemi **VCS (Version Control System)** yazılımıdır. Yazılım geliştirme sürecinde kullanılır ve kod değişikliklerinin izlenmesine, takibine, yönetilmesine ve işbirliği yapılmasına olanak tanır.
**Git**, birçok proje için popüler bir **VCS** aracıdır ve özellikle açık kaynaklı (open source) projelerde sıkça kullanılır. **Git**, merkezi bir sunucuya gerek duymadan birçok kişinin aynı kod deposunu paylaşmasına izin verir. Ayrıca, kodun farklı sürümlerini veya dallarını oluşturarak, farklı geliştirme yolları üzerinde çalışmalarını sağlar. Bu, yazılım geliştirme sürecindeki işbirliğini ve verimliliği artırır.

**Git**, **komut satırı arayüzü (Command Line Interface)** veya **grafik arayüzü** ile kullanılabilir.
- **Git**, **Linus Torvalds** tarafından geliştirilmiştir.
- **Git**, birçok işletim sistemi üzerinde çalımaktadır.
- Tamamen **açık kaynaklı (open source)** ücretsiz bir şekilde kullanılabiliniyor.
- **Git** artık bir "**Endüstri Standardı**" olarak kullanılmaktadır.

**Github:** Bir portal, **git** repolarımızı yani projelerimizi sakladığımız bir birlerimiz ile paylaşabildiğimiz onun içerisinde interaktif işler yapabildiğimiz bir portal.

### Kullanıcı Adı ve Email Tanımlama
Kod geliştirme sürecinde birçok insanla birlikte çalışabiliriz. Bu nedenle, kimin hangi kodu yazdığı ve kimin hangi değişiklikleri yaptığı gibi bilgilerin tutulduğu bir sistem kullanmak oldukça önemlidir. **Git**, bu amaç için ideal bir araçtır. Ancak, diğer insanlarla işbirliği yaparken, hangi kullanıcının hangi değişiklikleri yaptığını bilmek için kendi kullanıcı adımızı ve email adresimizi **Git** sistemimize kaydetmemiz gerekmektedir.

Kullanıcı adınızı ve email adresinizi **Git** sistemine kaydetmek oldukça kolaydır. Terminal veya **Git Bash** gibi bir uygulama üzerinde aşağıdaki komutları çalıştırarak bunu yapabilirsiniz:

#### Kullanıcıyı **Git**'in sistemine kayıt etmek için:

> `git config --global user.name "oktay"` --> kullanıcı ismini tanımladık 
> `git config --global user.email "s.oktay.bicici@gmail.com"` --> kullanıcı mail adresini tanımladık
>``git config --global core.editor "vim"`` --> editörü tanımlıyoruz
> `git config --list` --> var olan ayarları görüntülüyoruz


> Yaptığımız config işlemlerinin 3 seviyesi vardır. Bunlar;
> -- global : Bu komutu kullandığınızda, ayarların her yerde geçerli olacağı anlamına gelir. 
> -- system : sadece login olmuş kullanıcı için etkiler 
> -- local : sadece çalıştığımız klasör için geçerli olur

## Önemli Git Terimleri 

- **Commit:** Git ile yapılan değişikliklerin kaydedildiği bir işlemdir. Bu işlem sayesinde herhangi bir zamanda geriye dönülerek değişiklikler eski haline getirilebilir.
- **Branch:** Projelerin farklı dallara ayrılarak geliştirilebilmesini sağlayan bir özelliktir. Bu sayede projenin farklı özellikleri ayrı ayrı geliştirilebilir ve sonrasında birleştirebiliriz.
- **Repository:** Git'in başlatıldığı klasördür. Bu klasördeki dosyalar ve değişiklikler Git ile kontrol altına alınır.
- **Working Directory (Çalışma Dizini):** Bu, projenin bulunduğu klasördür ve tüm dosyalar burada saklanır. Bu dizindeki dosyaları değiştirir veya yeni dosyalar eklersiniz.
- **Index - Staging Area:** Bu alana bazen _"sahne"_ denir. Bu alanda değişiklik yaptığınız dosyalar bulunur, ancak henüz projenin bir parçası değillerdir. Bu, değişiklikleri daha sonra kaydetmek üzere hazırlamak için kullanılan bir ara bölgedir. Yani, dosyalarda yaptığınız değişiklikleri, Git'e kaydetmek istediğinizde buraya eklersiniz.
- **Local Repository:** Bu, Git'in projenin tüm geçmiş sürümlerini ve değişikliklerini sakladığı yere denir. Yani, burası dosyalardaki değişiklikleri kaydettiğiniz yerdir. Local Repository, proje dizininde .git adı verilen bir klasör içinde saklanır. Bu klasör, projenin tam tarihçesini ve Git'in projeyle ilgili diğer verilerini içerir.
- **Rrepository:** Bir projenin orijinal kaynak kod deposudur. Bu genellikle bir açık kaynak yazılım projesi için bir **GitHub** deposu veya benzeri bir git barındırma servisi olabilir. Fork işlemi yapıldığında, kullanıcının hesabında bir kopya oluşturulur ve bu kopya, orijinal proje ile senkronize edilebilir. Senkronize edildiğinde, kullanıcının kopyası, değişikliklerin yapılmasına, commit edilmesine ve bir **Pull request** gönderilmesine izin verir. Repository, orijinal proje ile senkronize edildiğinde, bu değişikliklerin orijinal projeye dahil edilmesini sağlar. Bu nedenle repository, bir projenin yönetimi ve katkıda bulunulması için önemlidir.

![git]()

> `git init` --> bulunduğumuz klasöre gelerek terminalden git'i başlatıyoruz 

> `git help` --> kodlar hakkında bilgi sağlıyor
> `git stastus` --> git işleminde son durumumuzu gösteriyor

> `git add` --> staging area gönderme işlemi 
> `git add .` | `git add *` --> bulunduğumuz klasördeki tüm dosyaları add işlemi uygulayacak
> `git add <filename>` --> staging area belirlediğimiz dosyayı gönderme işlemi 

> `git commit` --> repository gönderme işlemi
> `git commit -m "message"` --> yaptığımız commit işlmine mesaj ekleyebiliyoruz.
> `git commit -am "message"` --> hem add işlemi hem mesaj ekleme işlemi
> `git commit --amend` --> son yazılan mesajı değiştirmek için kullanılır.

> `git log` --> commit geçmişini görmek için

> `git diff` --> kodlar arasındaki farkı görmek için

>`git rm` --> silmek veya geri göndermek için
>`git rm --cached` --> staging area'dan working directory'e geri gönderme işlemi

>`git checkout` --> dosyayı repodan working directory'e gönder için kullanılır.

.gitignore
> git içerisinde takip edilmek istanmeyen dosya veya belgeri, her satıra bir tanesi gelecek şekilde belirtiyoruz. 
> `*.log` --> tüm log dosyalarını atlamasını ve tutmamasını sağlıyoruz.
> `!important/*.log` --> log dosyalarından istediğimiz özel bir dosyanın takibini yapabilmesi için belirtiyoruz.
> file --> dosyayı yazabiliyoruz
> folder/ --> dosya yolu yazabiliyoruz.

### Remote Repository (**Github**)
> `git clone <url>` --> işlem yapacağımız repoyu çekiyoruz. Bunu 1 defa yapmamız yeterli
> `git clone <url> .` --> clonaldığınız repo, klonlanan dosya içerisine dosya oluşturmadan klonlanacak

>`git pull` --> çekmiş olduğumuz reponun son değişikliklerini çekiyoruz. pull ( fetch + merge ) iki işemi birden yapar. fetch(kodun son halini ğc getirir) merge (kodun son halini elimizdeki kod ile birleştirir.)

> `git push` --> yazdığımız kodu githuba gönderir

![git-2]()

## Branch 
Branch, Git'te ana projeden ayrılan farklı bir projenin kopyasıdır. Bu, bir projenin farklı sürümlerinin yönetilmesini sağlar. Ana projeden yeni bir dal alarak, o dalda yapılan değişiklikler ana projeyi etkilemez. Böylece birden fazla kişi aynı proje üzerinde çalışırken, farklı dalarda çalışarak kodları yönetebilirler. Ayrıca, farklı özelliklerin geliştirilmesi, hata düzeltmeleri gibi farklı görevleri üstlenebilirler. Branch'ler, daha sonra birleştirilebilir veya silinebilir.

#### Head
HEAD, Git'in içinde bulunduğumuz konumu belirten bir referanstır. Genellikle en son commit'i işaret eder. Bu, nerede olduğumuzu ve hangi commit üzerinde çalıştığımızı belirlememizi sağlar.

> `git branch` --> Mevcut branch'leri görüntülüyoruz.
> `git branch -r` --> github'daki branchleri gösterir.
> `git branch -a` --> tüm brachleri gösterir

> `git branch <branch name>` --> yeni bir branch oluşturmak için kullanıyoruz
> `git checkout <branch name>` --> olduğumuz branchden ismini yazdığımız branche gideriz.
> `git chechout -b <branch name>` --> ismini yazdığımız branci oluşturur ve o branche geçişi sağlar 
> `git switch <branch name>` --> branch'lar arası geçiş yapmaya sağlar.

> `git branch -d <branch name>` --> branchi siler
> `git branch -D <branch name>` --> branchi siler


### Merge
Git'te merge, farklı branch'lerin birleştirilmesini sağlayan bir işlem olarak tanımlanır.

> `git merge <branch name>` --> Komutu ile ismini verdiğimiz branch'i master branch'ine birleştirebiliriyoruz. 

![merge]()

#### Fast Forward 
Fast forwarding, birleştirme işlemi sırasında, kaynak branch'in (genellikle feature branch) değişikliklerinin, hedef branch'e (genellikle master branch) direk olarak uygulanmasıdır. Bu işlem sırasında, herhangi bir çakışma olmadığı ve her iki branch'in de aynı değişiklikleri içerdiği varsayılır.

![fast-forward]()

#### Merge Conflict
Merge Conflict, Git branch'leri arasındaki değişikliklerin birleştirilmesi sırasında ortaya çıkan çakışmaları ifade eder. Bir Merge Conflict, aynı dosyanın aynı satırlarında farklı değişikliklerin yapıldığı durumlarda oluşur. 
Bu durumda, Git çakışan dosyaları işaretleyerek, kullanıcının bu dosyalarda çakışan değişiklikleri elle birleştirmesine olanak sağlar. Kullanıcılar, conflict'in olduğu dosyalarda çakışan değişiklikleri elle birleştirerek veya belirli bir sürümü kabul ederek (theirs veya ours seçeneklerini kullanarak) conflict'i çözebilirler.

#### Stash 
Stash: Saklamak veya depolamak anlamlarını taşır.

Git stash, Git versiyon kontrol sistemi kullanılarak yapılan değişiklikleri geçici olarak kaydetmenizi sağlayan bir özelliktir. Bu, henüz tamamlanmayan bir iş üzerinde çalışırken veya bir dal üzerinde çalışırken aniden başka bir acil işle ilgilenmeniz gerektiğinde özellikle kullanışlıdır.

> `git stash` --> komutu ile add işlemi yapmak istemediğim daha sonra eklmeyi düşündüğüm değişiklikleri gizlemek için kullanıyoruz. 

Yapılan stash işlemleri sırası ile `stash@{0}` - `stash@{1}` şeklinde sırası ile kaydedilmekte. 
> `git stash list` --> Kaydedilen stash'leri görüntülememizi sağlar.

> `git stash clear` --> kaydedilen stash'leri siler

> `git stash pop` --> kaydedilen stashi geri yükler ve listeden kaldırır

> `git stash apply` -->  En son kaydedilen stash'i geri yükler ve listeden silmez
> `git stash apply stash@{n}` -->  Belirtilen numaralı stash'i geri yükler.

> `git stash drop` --> En son kaydedilen stash'i siler.
> `git stash drop stash@{n}` --> Belirtilen numaralı stash'i siler.


## Geçmişe Dönme

### Checkout

commit atmadan önce :
> `git restore <belge ismi>` --> bir önceki commite geri döner 

Checkout, belirtilen bir commit'e veya dalın bir önceki commit'ine geri dönmemizi sağlar. Bu işlem sonrasında HEAD işaretçisi, doğrudan commit veya dalı gösterir. Ancak, git checkout komutu ile commit'e geri döndüğümüzde Detached HEAD durumuna düşeriz. Bu durumda, HEAD işaretçisi doğrudan bir commit'i işaret eder ve mevcut konum geçici bir durumdur.

![git-chechout]()

> `git switch master` diyerek head'ı master'a geri getirebiliriz.

![git-chechout_2]()

yada farklı bir branch açarak ordan devam edebiliriz. 


### Reset ve Revert
Reset ve Revert, git'te geçmişe dönmek için kullanılan iki farklı yöntemdir. 

> `git reset <commit id>` --> belirtilen id sahip commite geri döner, belirlenen commite kadar olan değişiklilkleri tutar, commitleri siler
> `git reset --hard <commit id> `  --> belirtilen id sahip commite geri döner, belirlenen commite kadar olan değişiklilkleri ve commitleri siler

> `git revert <commit id>` --> Bu komutu kullandığınızda, belirtiğimiz commit'i geri alıyoruz ve bu işlem sonucunda yeni bir commit oluşur. Bu sayede, Git geçmişi değiştirilmemiş, ancak istenmeyen değişiklikler geri alınmış oluyor.

### Git Diff
Git versiyon kontrol sistemi ile çalışırken, değişiklikleri görüntülemek için kullanılan bir komuttur. Bu komut, dosya veya dizinler arasındaki farkları gösterir ve değişikliklerin tam olarak neler olduğunu ayrıntılı olarak açıklar.
Mevcut çalışma kopyası ve son commit arasındaki farkları görebilirsiniz. Bu, yeni eklenen veya silinen dosyaları, değiştirilen satırları ve dosyaların farklı sürümlerindeki değişiklikleri gösterir.
Farklı branch'ler arasındaki farkları, değiştirilmiş veya silinmiş dosyaları, değiştirilmiş satırları ve farklı sürümlerdeki dosyaları göstermek için kullanılabilir. Bu, birden fazla kişiyle çalışırken, değişiklikleri birbirleriyle karşılaştırmanızı ve senkronize etmenizi sağlar.

> `git diff HEAD` --> Değiştirilmiş veya eklenen dosyaları son commit ile karşılaştırır. "HEAD" son commit'i ifade eder. Bu komutu kullanarak, son commit'ten önceki tüm değişiklikleri görebilirsiniz.

> `git diff <commit1> <commit2>` --> Commitler arasındaki farkı gösterir.

> `git diff <branch> <branch2>` --> Branchler arasındaki farkı gösterir.

> `git diff --cached` --> Bu, "staged" (commit öncesi hazırlanan) değişiklikleri gösterir. Yani, henüz commit etmeden önce, "git add" komutu ile hazırlanmış değişiklikleri gösterir.

Ayrıca, git diff --color-words komutu kullanılarak, değişen kelime veya karakterlerin renkli olarak gösterilmesi sağlanabilir. Bu, değişiklikleri daha ayrıntılı ve kolay anlaşılır hale getirir.

### Rebase
Git'te "rebase" komutu, bir dalı diğerine eklemek için kullanılır ve birleştirme işlemi yaparken diğer dalın değişiklikleri geçerli dala uygulanır. Bu, daha temiz bir Git geçmişi sağlar ve uzun süreli projelerde sıkça kullanılır.

![rebase_1]()

![rebase_2]()

## Github

### ### GitHub Nedir

**Git Nedir:** Sürüm kontrolü sistemi olarak bilinir. Sürüm kontrolü, bir projenin değişikliklerinin kaydedilmesi, takip edilmesi ve yönetilmesi için kullanılan bir teknolojidir. Git, birçok kişinin aynı projede çalışması durumunda kullanışlıdır.

**GitHub Nedir:** Bu versiyon kontrol sistemi ile birlikte kullandığımız projeleri depolayabileceğimiz bir portal

### Git ve GitHub Arasındaki Farklar

Git, sadece bir sürüm kontrolü sistemidir ve yerel bir bilgisayarda çalışırken **GitHub**, Git üzerine inşa edilmiş bir bulut barındırma hizmetidir.

Git, bir projenin sürüm kontrolünü yönetirken, **GitHub**, projenin paylaşımı, işbirliği, sorun takibi ve kod incelemesi gibi ek özellikler sunar.

**Star:** **GitHub**'daki bir projeyi beğenmek ve ileride kolayca erişmek istediğinizi belirtmek için kullanılan bir özelliktir.

**Explore:** İlgi alanlarınıza göre önerilen projeleri ve popüler projeleri gösteren bir özelliktir.

### Github Repo

İlk repo oluşturmak için aşağıdaki adımları takip edebilirsiniz:

1. Github hesabınıza giriş yapın.
2. Sağ üst köşedeki '+' butonuna tıklayarak "New repository" seçeneğini seçin.
3. Repository adını ve açıklamasını girin. Repository adınızın benzersiz olması gerektiğini unutmayın.
4. Public veya Private olarak repo ayarlarını belirleyin. Public seçeneği herkese açık olurken, Private seçeneği sadece sizin veya ekibinizin erişebileceği şekilde oluşturulur.
5. README dosyası oluşturma seçeneğini seçin. Bu seçenek, repo sayfanızda görüntülenen açıklama sayfasıdır.
6. Lisans seçeneğini belirleyin. Eğer projeniz açık kaynak ise bir lisans seçmeniz gerekmektedir.
7. "Create repository" butonuna tıklayın ve ilk repo'nuzu oluşturun.

Artık ilk repo'nuzu oluşturduğunuza göre, projenizi bilgisayarınızdan Github'a yüklemeye başlayabilirsiniz. Bunun için öncelikle bilgisayarınıza git yüklemeniz ve projenizi local olarak oluşturmanız gerekiyor.

Github'da repo oluştuduktan sonra kendi klasörümüz ile bağlantı kurabilmek için 3 seçenek sunuyor.

![github-git-bağlantı]()

1. seçenekte klasöre git init yaparak bağlantı sağlıyoruz. 
2. seçenekte init yapılmış klasörle github bağlantısı sağlıyoruz. 
3. Seçenekte farklı bir repodan kod seçerek repomuzla işlem yapıyoruz.

### Git Push
> `git push -u origin main`

-->  **-u (upstream)** ifadesi, varsayılan yukarı akış depoya **(origin)** ve ana dal **(main)** için bir yer işaretçisi belirler. Bu işaretçi sayesinde, bir sonraki git push komutunu çağırdığınızda, Git, origin main argümanlarını tekrarlamak yerine bu yer işaretçisini kullanarak push işlemi yapar.

Bu sayede, git push komutunu çağırdığınızda, Git otomatik olarak belirlenen yer işaretçisine göre işlem yapar.

> `git push` --> diyerek doğrudan origin içerisine pushlamış oluyoruz.
> `git push origin main` --> main branch'i ile origine pushlamış oluyoruz.
> `git push origin <branh ismi>` --> hangi branch ve o branchdeki değişiklikleri pushlamak istiyorsak branch ismini yazıyoruz.

>`gir branch -r` --> remote branchleri görüntüleriz.

### Git Push
> `git push -u origin main`

-->  **-u (upstream)** ifadesi, varsayılan yukarı akış depoya **(origin)** ve ana dal **(main)** için bir yer işaretçisi belirler. Bu işaretçi sayesinde, bir sonraki git push komutunu çağırdığınızda, Git, origin main argümanlarını tekrarlamak yerine bu yer işaretçisini kullanarak push işlemi yapar.

Bu sayede, git push komutunu çağırdığınızda, Git otomatik olarak belirlenen yer işaretçisine göre işlem yapar.

> `git push` --> diyerek doğrudan origin içerisine pushlamış oluyoruz.
> `git push origin main` --> main branch'i ile origine pushlamış oluyoruz.
> `git push origin <branh ismi>` --> hangi branch ve o branchdeki değişiklikleri pushlamak istiyorsak branch ismini yazıyoruz.

>`gir branch -r` --> remote branchleri görüntüleriz.

### Pull Request
**Pull request** **(PR)**, bir yazılım projesinde değişiklik yapmak isteyen bir kullanıcının, projenin sahibi ya da ekibinin dikkatini çekmek ve değişikliklerinin ana kod tabanına (master dalı gibi) birleştirilmesini talep etmek için yaptığı bir istektir.
Bir kullanıcı, projenin bir kopyasını (fork) oluşturarak değişikliklerini yapar ve bu değişiklikleri commit ederek kendi fork dalında saklar. Daha sonra, bu değişiklikleri orijinal projenin sahibine göstermek için bir **Pull request** açar. **Pull request**, değişikliklerin açıkça açıklandığı bir iletişim kutusu görevi görür ve projenin sahibi ya da ekibi tarafından incelenir.
Eğer değişiklikler onaylanırsa, projenin sahibi ya da ekibi, **Pull request**'i kabul ederek değişiklikleri ana kod tabanına (master dalı gibi) birleştirir. Bu sayede, projeye katkıda bulunan herkesin değişiklikleri, ana kod tabanına dahil edilerek projenin geliştirilmesine katkı sağlar.

### Fetch ne Pull
Fetch ve Pull, Git'te uzak bir deposundan (remote repository) yeni değişiklikleri alma işlemleridir.
Fetch işlemi, uzak depodaki yeni değişiklikleri lokal depoya indirir ancak lokaldeki çalışma dizinine (working directory) birleştirmez. Bu işlem, uzak depodaki değişikliklerin var olup olmadığını kontrol etmek için kullanılabilir.

> `git fetch` --> Değişiklikleri al lokale getir.

Pull işlemi ise, uzak depodaki yeni değişiklikleri hem indirir hem de lokaldeki değişikliklerle birleştirir. Bu işlem, uzak depodaki değişiklikleri lokaldeki çalışma dizinine (working directory) eklemek istediğinizde kullanılır.

> `git pull` --> `git fetch` + `git merge`
> `git pull origin main` --> Uzak depodaki (remote repository) "origin" adlı depodan "main" adlı dalın (branch) değişikliklerini indirerek lokal depoya (local repository) birleştirir. Yani, bu komut, uzak depodaki en güncel "main" dalındaki değişiklikleri indirir ve lokaldeki "main" dalıyla birleştirir.

Kısacası, **Fetch** işlemi sadece uzak depodaki değişiklikleri indirirken, **Pull** işlemi hem indirme hem de birleştirme işlemlerini gerçekleştirir.

### Clone
Clone işlemi github da bulunan repoyu kendi local dosyalarımıza indirmemizi sağlıyor. Bu şekilde tüm commit geçmişi ve branchler ile birlikte dosya kendi bilgisayarımızda yer alıyor. Fakat herhangi bir commiti push edemiyoruz, eğer iznimiz yoksa.

> `git clone <repo link>` 

### Fork
Fork ile istediğimiz public bir repoyu kendi github hesabımızda bir repo olarak çekebiliriz. Çektiğimiz repo üzerinde istediğimiz her değişikliği yapabiliriz. Yaptığımız değişiklikleri **Pull Request** işlemi ile fork ettiğimiz repoya eklemeye çalışabiliriz. Repo sahibinin onayı ile ekleme gerçekleşir. 