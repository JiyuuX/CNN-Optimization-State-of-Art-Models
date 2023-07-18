# CNN-Optimization-State-of-Art-Models

Evrişimli Sinir Ağlarının (Convolutional Neural Network) Temel Bileşenleri

Convolutional Neural Network(CNN), derin öğrenme kapsamında, görsel verilerin
sınıflandırılması, analiz edilmesi için geliştirilmiş bir Yapay Sinir Ağıdır. CNN kullanarak,
fotoğraflar, videolar, tıbbi görüntü vb. verilerden nesneleri, yapıları tanımak, sınıflandırmak,
öneride bulunmak için kullanılırlar. Convolutional Neural Network, yukarıda bahsedilen
eylemleri gerçekleştirebilmek için veriyi katmansal bir yapı, mimari içerisinde işler. Temel
olarak, Convolutional Layer, Activation Layer, Pooling Layer (Downsampling), Flattening
Layer ve Fully-Connected Layer olmak üzere beş katmandan oluşur.

--Convolutional Layer (Evrişim Katmanı)

Evrişimli katman, resim veya görüntünün belirli özelliklerinin tespit edilmesi ve
belirlenmesinden sorumlu katmandır. Evrişimli katmanda, resim ya da görüntü içerisindeki
objelerin, şablonların bir nevi tanımlanma işlemi yapılır. Evrişimsel Sinir Ağlarında resim,
görüntü, video v.b. veri formatları, bir matris içerisinde ikilik formatta temsil edilir. Ardından
bu matris üzerinde, yine başka bir matris olan bir filtre gezdirilir. Görüntüyü temsil eden
matris ile filtre sol birinci pixel'den başlayarak soldan sağa doğru gezdirilir, gezdirilme işlemi
esnasında görseli temsil eden matris içerisindeki indis değerleri ile filtre matrisinin değerleri
çarpılar toplanır ve toplanan değerler her bir pixel indisi için Feature Map(Özellik Haritası)
adı verilen başka bir matriste tutulur. Bu süreç sayesinde görüntü üzerindeki özelliğin tespiti
sağlanmış oluyor. Eğer görüntü üzerinde birden fazla özellik tespit edilmek isteniyor ise bir
başka filtre matrisiyle bu işlemler tekrarların ve bir başka Özellik Haritası oluşturulur.

--Activation Layer

Aktivasyon Katmanı, Evrişimli Katmandan çıkan matris'in aktivasyon fonksiyonlarından
birinden geçirildiği katmandır. Aktivasyon fonksiyonlarının kullanılma amacı matrisi
oluşturan veriler arasında standartlaştırma işlemi yapmaktır. Aktivasyon fonksiyonu olarak,
Sinir Ağının eğitilmesi sürecindeki sürenin azaltılması gerektiği durumlarda ReLu (Rectifier)
Aktivasyon fonksiyonu kullanılır.

--Pooling Layer

Havuzlama Katmanında, üretilen Özellik Haritası matrisindeki indislerin sayısının azaltılması
ve bu sayede hesaplama sürecinin hızlandırılması için daha önce oluşturulmuş matris, başka
bir matriste temsil edilir.

--Flattening Layer ve Fully-Connected Layer

Flattening Layer, Evrişimsel Sinir Ağının (CNN-Convolutional Neural Network) son
katmanından bir önceki katmandır. Bu katmanın amacı Convolutional ve Pooling
katmanından türetilmiş olan çok boyutlu matrislerin, tek boyutlu bir dizi haline
dönüştürülmesidir. Fully-Connected Layer ise CNN'nin son katmanıdır ve öğrenmenin asıl
olarak gerçekleştiği katmandır.

--SOTA (State Of The Art) Modelleri

Birden fazla Convolutional Katmanı ve Aktivasyon fonksiyonunun bir araya getirilmesiyle
oluşturulmuş sabit CNN mimarili, önceden eğitilmiş ve dolayısıyla önceden özel olarak,
belirli görevleri yerine getirmek için belirli ağırlık değerleri olan modellerdir. SOTA(State Of
The Art) adı verilen bu mimari modeller belli başlı görevlerin iyi sonuçları verilmesi için özel
olarak tasarlanmış modellerdir.

--Transfer Learning

Aktarım Öğrenmesi, özel olarak belirlenen bir probleme çözüm üretebilen bir makine
öğrenmesinin veya derin öğrenmenin, öğrenme işlemi tamamlandıktan sonra öğrendiği
bilgiyi depolayıp daha önceki problemden farklı bir problem üzerinde daha önceki bilgisini
kullanarak çözmeyi ve sonucunda yeniden öğrenmeyi temel alan bir öğrenme yöntemidir.
Geleneksel Makine Öğrenmesi yöntemleriyle arasındaki en önemli fark, geleneksel Makine
Öğrenmesinde her problem bağımsızdır ve o problemin çözülmesi için o probleme özgü ağ
tasarlanmaya çalışılır. Öğrenilen bilgi aktarımı söz konusu değildir, ancak Aktarım
Öğrenmesiyle önceden Makine Öğrenmesinin tamamladığı görevleri, dolayısıyla öğrendiği
bilgileri bir başka probleme çözüm üretmek için tasarlanan yeni Makine Öğrenmesi modeline
aktarılarak çözüm üretebilmektedir.


![image](https://github.com/JiyuuX/CNN-Optimization-State-of-Art-Models/assets/139239394/56ea4bd0-15cf-466a-a94d-af7e148545dc)


Örneğin, görsellerdeki kedi ve köpeği sınıflandırmak için eğitilen bir Sinir Ağı burada
öğrendiği bilgileri kullanarak X-ray görüntüleri üzerindeki oluşumların tespit edilmesinde
bile kullanılabilir. Aktarım Öğrenmesi oluşturulurken temelde yapılan işlem daha önceden
eğitilen bir ağın son katmanı kaldırılarak bu katmanın yerine yeni bir katman veya birden
fazla katman eklenerek yeni bir çıkış katmanı oluşturulur. Oluşturulan bu çıkış katmanı,
devamında oluşturulacak olan yeni ağın giriş katmanı olmuş olacaktır.
Aktarım Öğrenmesinin bu özelliğinden dolayı hem eğitim modellerinin eğitim sürelerinin
kısaltılmasında hem de maliyetleri düşürmekte büyük bir katkı sağlamaktadır. Ek olarak, yeni
probleme çözüm üretmek için elimizde yeteri kadar veri olmadığında yeni oluşturulacak olan
ağı eğitmek için yeterli veri kümesi bulunmadığında, Aktarım Öğrenmesi kullanılabilir aksi
durumda kullanımı ağın verimini düşürebilir. Eğer yeni problem için kullanılacak veri
kümesi, daha önceki problemin çözülmesinde kullanılan veri kümesinden büyükse Aktarım
Öğrenmesinin uygulanması ağın verimini düşürebilecektir. Aktarım öğrenmesindeki bir diğer
önemli koşul da aktarım yapılacak olan ağ ile aktarım alınacak olan ağ aynı girişlere sahip
olması gerekir.

--Cross Validation

Çapraz Doğrulama (Cross Validation), veri kümesi'nin eğitim ve test verisi olarak
ayrıştırılması için kullanılan istatistiksel bir yöntemdir. Makine Öğrenmesi uygulamalarında
genel olarak, veri kümesi'nin 20%'lik bölümü test verisi, 80%'lik bölümü eğitim verisi olarak
kullanılır. Ancak veri kümesindeki verilerin, hangi sıralamada alındığı, Makine Öğrenmesi
uygulamalarının sonuçları üzerinde farklı sonuçlar doğurabilmektedir. Örneğin, rastgelelik
üzerine seçilen 20% test ve 80% eğitim verisi'nin ürettiği doğruluk, Makine Öğrenmesi tekrar
çalıştırıldığında rastgelelelik'den dolayı eğitim ve test verisi yüzdelik olarak aynı olmalarına
rağmen farklı verileri içereceklerinden dolayı farklı doğruluk değerleri üretilebilmektedir. Bu
problemin önüne geçmek için Çapraz Doğrulama adı verilen istatistiksel yöntemler
kullanılarak modelin doğrulanması amaçlanır. Literatürde K-Fold Cross Validation, Leave
One Out Cross Validation, Holdout Cross Validation, Time Series Cross Valdiation v.b. bir
çok Çapraz Doğrulama teknikleri bulunmaktadır.


--Öğrenme Katsayısı (Learning Rate)

Gradyan İniş ile minimum değerin bulunması için her bir iterasyondan sonra atılan adımların matematiksel boyutunu temsil eder.
Öğrenme katsayısının kesin olarak ne olması gerektiği hakkında kolektif bir kabul olmasa da öğrenme katsayısı ne çok az ne de çok fazla
seçilmedilir. Öğrenme katsayısının çok fazla olması durumunda her bir iterasyonda attığı adım boyutu fazla olacağı için
minimum değerin ıskalama riski taşırlar, çok küçük olması durumunda, minumum değeri bulma konusunda daha fazla kesinlik sağlarken aynı zamanda 
daha fazla zaman ve hesaplama gerektiğinden dolayı ağın verimliliği büyük ölçüde azaltabilir.

---Maaliyet Fonksiyonu(Cost-Lost Function)

Eğitimi tamamlanmış modelin gerçek çıktı değeriyle tahmin edilen değerin ne kadar doğru olup olmadığını ölçmek için maaliyet fonksiyonlarından biri kullanılır. 
Kullanılacak olan Maliyet Fonksiyonu çözülmesi istenilen probleme göre Ortalama Hata(Mean Error-ME) ,
Ortalamaların Kareleri Hata(Mean Squared Error-MSE), Ortalama Mutlak Hata(Mean Absolute Error-MAE), Cross-Entropy v.b. 
Maliyet Fonksiyonlarından biri seçilmesi gerekmektedir. Maliyet Fonksiyonuyla hesaplanan hata ağın ağırlıklarını güncellemek 
için kullanılacaktır.


--Gradyan İniş (Gradient Descent) ve Stokastik Gradyan İniş (SGD-Stochastic Gradient Descent)

Gradyan İniş, matematik biliminde türevi alınabilen bir fonksiyonun yerel minimum değerinin bulunmasıdır. 
Yapay Sinir Ağları kapsamında ise Eğitim Setiyle eğitilen Yapay Sinir Ağının, Test verilerine verdiği cevaplar arasındaki hatanın en aza
indirilmesi için kullanılan bir optimizasyon algoritmasıdır. Gradyan İniş bize local(bölgesel) minumum değerini bulmakta yarar sağlar 
ancak ileriki iterasyonlarda oluşabilecek local minimumları kaçırma riski taşıdığı için Stokastik Grasyon İniş ile genel(global) minimum 
değerinin bulunması ağırlıkların daha doğru güncellenmesine ve dolayısıyla öğrenmenin daha doğru bir şekilde gerçekleşmesine sebep 
olacaktır.
Gradyan İniş ve Stokastik Gradyan İniş'ten türetilmiş Adam, Adagrad, Adadelta gibi farklı optimizasyon algoritmaları da mevcuttur. 
Adagrad, eğitim süresi boyunca, ağırlık, öğrenme katsayısı gibi bir parametrenin hangi frekansta güncelleneceğine göre adapte olan bir 
optimizasyon algoritmasıdır. Adadelta, AdaGrad algoritmasının farklı bir versiyonudur.Adadelta, daha önce yapılmış tüm geçişleri,
güncellemelerin toplamını kullanmak yerine, o anda anlık olarak gerçekleştirilen gradyan değerine göre öğrenme katsayısını değiştiren 
başka bir optimizasyon metodudur.Adagrad ile kıyaslandığında, Adadelta, öğrenme başlangıcında bir başlangıç öğrenme katsayısı atanmasını
gerektirmez. Adam, iterasyon sonucu var olan gradyana çok fazla güvenmek yerine, bir dizi iterasyon sonucu gradyanların bu bir dizi 
iterasyon sonucundaki genel davranışının dikkate alındığı bir optimizasyon algoritmasıdır.


--Aktivasyon Fonksiyonları (Activation Functions)

Aktivasyon Fonksiyonları, Yapay Sinir Ağlarında Giriş ve Ağırlık Değerlerinin matematiksel işlemleri sonucunun çeşitli Aktivasyon 
Fonksiyonları kullanılarak ölçeklendirmemize imkan tanır. Aktivasyon Fonksiyonu kullanılmasının amacı, Aktivasyon Fonksiyonundan 
önce gelen katmandaki verinin belirli bir değer aralığında sıkıştırılmasıdır.Bu sayede gerçek değerli veriyi ölçeklendirilmiş 
formatta kullanabilmemizi sağlarlar.Aktivasyon Fonksiyonları hangi değerin çıktı olarak iletileceğini ve hangi değerlerin çıkış 
olarak iletilmeyeceğini belirler.




-KANSERLİ HÜCRELERİN VÜCUTTAKİ DAĞILIMI

![image](https://github.com/JiyuuX/CNN-Optimization-State-of-Art-Models/assets/139239394/2df8c0bd-d477-46dc-9d76-68b9427d5cbc)


LEZYON GÖRSELLERİ

![image](https://github.com/JiyuuX/CNN-Optimization-State-of-Art-Models/assets/139239394/5ea0e776-d5a1-4149-a21b-378348583724)


ACCURACY- EPOCH

![image](https://github.com/JiyuuX/CNN-Optimization-State-of-Art-Models/assets/139239394/901a933a-ec61-4175-a89b-dde9fe79d939)


Learning Rate Optimization

![image](https://github.com/JiyuuX/CNN-Optimization-State-of-Art-Models/assets/139239394/926bbef2-7f36-4075-883c-dc7b4481d161)


NOTE:

SOTA(DenseNet121, MobileNet ResNet18, ResNet50, VGG, EfficientNetB0 ve Xception)
modelleri üzerindeki performansı, Keras kütüphanesi ile SOTA modellerinin optimizasyon
algoritmalarıyla (Adam, AdaDelta, AdaGrad v.b.) optimize edildikten sonraki performansı incelenmiş, en iyi sonucu xception modeli vermiştir.








