# EDA ve Veri Ön İşleme Özeti

## 1. Giriş
Bu proje, ilaç kullanımına bağlı oluşan yan etkiler veri kümesindeki eksik verileri ve aykırı değerleri analiz etmek, veriyi temizlemek ve kategorik değişkenleri sayısal forma dönüştürmek amacıyla tasarlanmıştır. Verinin genel yapısı, temel istatistikleri ve değişkenler arasındaki ilişkileri incelemek için çeşitli görselleştirme ve analiz yöntemleri kullanılmıştır.

## 2. Kullanılan Kütüphaneler
- `pandas`
- `numpy`
- `matplotlib`
- `seaborn`
- `scikit-learn`
- `scipy`

## 3. Veri Yükleme
Veri, `load_data(file_path)` fonksiyonu aracılığıyla yüklenmektedir. Excel formatındaki veri dosyası belirtilen dosya yolundan okunur.

## 4. Eksik Verilerin Görselleştirilmesi
`visualize_missing_data(df)` fonksiyonu ile eksik verilerin dağılımı görselleştirilir. Bu, hangi değişkenlerin eksik veriye sahip olduğunu anlamaya yardımcı olur.

## 5. Aykırı Değerlerin Görselleştirilmesi
`visualize_outliers(df)` fonksiyonu, sayısal değişkenlerin aykırı değerlerini incelemek için kutu grafikleri kullanır.

## 6. Temel Bilgilerin Gösterilmesi
`display_basic_info(df)` fonksiyonu, veri çerçevesinin boyutunu, değişken isimlerini, veri tiplerini ve eksik değer sayısını gösterir. Ayrıca temel istatistikleri ve veri çerçevesinin bilgilerini sağlar.

## 7. Veri Temizleme ve Doldurma
`clean_and_fill_data(df)` fonksiyonu, eksik değerlerin doldurulmasını ve belirli değişkenlerin temizlenmesini sağlar:
- `Cinsiyet` değişkeni, il bazında doldurulmaktadır.
- `Kan Grubu`, `Alerjilerim` ve `Kronik Hastaliklarim` gibi değişkenler, uygun stratejilerle doldurulmaktadır.
- Sayısal veriler için KNN imputation kullanılmaktadır.

## 8. Kategorik Değişkenlerin Analizi
`categorize_chronic_diseases(df)` ve `categorize_medication_names(df)` fonksiyonları ile kronik hastalıklar ve ilaç adları kategorize edilmiştir. En sık görülen 30 ilaç, "Diğer" kategorisiyle birleştirilmiştir.

## 9. Kategorileştirme
`apply_categorization(df)` fonksiyonu, kilo, boy ve yaş gibi sayısal değişkenlerin kategorilere ayrılmasını sağlar.

## 10. Chi-Square Testi
`chi_square_test(df, col1, col2)` fonksiyonu, iki kategorik değişken arasındaki bağımsızlık ilişkisini test etmek için Chi-Square testi uygular. Test sonuçları bir DataFrame içinde toplanarak sunulmuştur.

## 11. Sonuçlar
Sonuçlar, Chi-Square testinin p değerleri ve istatistikleri ile birlikte görüntülenmiştir. Bu, değişkenler arasındaki ilişkilere dair önemli bilgiler sağlar.

## 12. Uygulama
Kodun çalıştırılması için `main_pipeline(file_path)` fonksiyonu kullanılarak veri yüklenir ve tüm ön işleme adımları gerçekleştirilir.

## 13. Kullanılan Veri
Veri, `side_effect_data.xlsx` dosyasından yüklenmektedir.
