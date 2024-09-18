
# Machine Learning with US Airline Flight Routes and Fares 1993-2024 Dataset Supervised-and-Unsupervised-Algorithm

## Projenin Amacı:
Bu proje havayolu firmalarının fiyatlandırmayı optimize etmesine ve rotaları daha etkili bir şekilde planlamasına yardımcı olmayı amaçlıyoruz. 


**Projenin EDA kısmının bulunduğu kaggle notebook**
*  --> https://www.kaggle.com/code/akadir0223/flights-eda

**Projenin kısa bir veri analiziyle birlikte model oluşturma kısmının bulundauğu kaggle notebook**
*  --> https://www.kaggle.com/code/akadir0223/flights-fare-prediction

## Veri Seti
Kullanılan dataset, 245,955 satır and 23 sütundan oluşmaktadır. Sütunlar sırasıyla şu şekilde:

- **tbl**: Tablo kimliği
- **Year**: Veri kaydının yılı
- **quarter**: Yılın çeyreği (1-4)
- **citymarketid_1**: Kalkış şehir pazar kimliği
- **citymarketid_2**: Varış şehir pazar kimliği
- **city1**: Kalkış şehri adı
- **city2**: Varış şehri adı
- **airportid_1**: Kalkış havaalanı kimliği
- **airportid_2**: Varış havaalanı kimliği
- **airport_1**: Kalkış havaalanı kodu
- **airport_2**: Varış havaalanı kodu
- **nsmiles**: Havaalanları arasındaki mesafe (mil cinsinden)
- **passengers**: Yolcu sayısı
- **fare**: Ortalama bilet fiyatı
- **carrier_lg**: En fazla yolcusu olan hava yolu kodu
- **large_ms**: En büyük taşıyıcının pazar payı
- **fare_lg**: En büyük taşıyıcının ortalama bileti
- **carrier_low**: En düşük bilet fiyatına sahip hava yolu kodu
- **lf_ms**: En düşük bilet fiyatına sahip taşıyıcının pazar payı
- **fare_low**: En düşük bilet fiyatı
- **Geocoded_City1**: Kalkış şehri için coğrafi koordinatlar
- **Geocoded_City2**: Varış şehri için coğrafi koordinatlar
- **tbl1apk**: Rota için benzersiz kimlik
----

bağımlı değişken "fare" olarak belirlenmiştir.
Çeşitli algoritmalar kullanılmaya çalışlıarak "fare" değeri tahmin edilmeye çalışılmıştır.
Sonradan silinmiş olsa da tüm regresyon algoritmaları denenmiş en sonunda RandomForestRegressor() en iyi çalışan algoritma olduğu için onunla devam edilmiştir.
Unsupervised Learning algoritmalarından KMeans kullanılmıştır.

model skoru hiperparametre optimizasyonu yapılarak geliştirilmiştir.

Değerlendirme sonucu RandomForestRegressor için aşağıdaki gibidir : 
----

**Model Performance**
* Average Error: 18.5220 degrees.
* Accuracy = 91.00%.
* Mean Squared Error: 755.4095027366814
* Mean Absolute Error: 18.522000200718868
* R² Score: 0.843834237560804
* sonuçlar optimizasyon sonrası bu hale gelmiştir.
---
KMeans için elde edilen skorlar aşağıdaki gibidir : 
---
* Aşağıdaki Performans metrikleri, kümelerin kalitesini ölçer. Kümeleme performansına dair metrikler yani : 
*  Silhouette Score for 4 clusters: 0.46371227067631293
* Davies-Bouldin Index for 4 clusters: 0.7062882332826151
---

### Sonuçların Değerlendirilmesi
**RondomForest**
* model %91 doğrulukla tahmin yapıyor.Bu, modelin tahminlerinin büyük bir kısmının gerçek değerlere oldukça yakın olduğunu gösterir.
* 0.8438'lik bir R² skoru, modelin hedef değişkenin %84.38'ini açıkladığını gösterir. Yani, model veriye dayalı güçlü bir tahmin gücüne sahiptir.


## Algoritmalar arasındaki Başarı Farkına Dair Yorum
K-Means algoritması kümeleme için tasarlanmış bir algoritmadır ve regresyon problemlerinde doğrudan kullanılmaz. Kümeleme algoritmaları, veri noktalarını kümelere ayırmaya yönelik olup, sürekli bir hedef değişkenin tahmininde zayıf performans sergiler. Bu nedenle, K-Means ile ortalama bilet fiyatı gibi sayısal bir değeri tahmin etmek uygun bir yaklaşım değildir.

Ancak KMeans gibi Unsupervised ML algoritmaları özellik seçimi konusunda regresyon problemlerinde dolaylı olarak kullanılırlar. BU çalışmada başarısız olmuş olması regresyon problemleri için tamamen önemsiz olduğu anlamına gelmez.
