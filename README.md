# E-Ticaret-M-teri-Churn-Durumu

## 🎯 Problem
E-ticaret platformunda kullanıcı kaybının (churn) önceden
tahmin edilememesi ve müşteri davranışlarını etkileyen kritik
faktörlerin (harcama tutarı, ziyaret sıklığı vb.) analiz edilerek
müşteri bağlılığının artırılması ihtiyacı.

##  Yaklaşım
Veri seti, Z-Score ve IQR yöntemleri ile aykırı değerlerden
arındırılarak stabilize edildi. Müşteri bağlılığını ölçmek için
"Oturum Başı Sepete Ekleme Oranı" gibi sentetik metrikler
türetildi. XGBoost, Random Forest ve Decision Tree modelleri
üzerinden benchmarking yapıldı.

## 🛠 Kullanılan Teknolojiler
Python, XGBoost, Random Forest, Scikit-learn, Pandas,
NumPy, Min-Max Scaling.

## 📊 Önemli Bulgular
%93.00 doğruluk (Accuracy) oranı ile çalışan XGBoost modeli
başarıyla devreye alındı. Müşteri kaybını tetikleyen temel
faktörlerin; "Harcama Tutarı", "Platform Ziyaret Sıklığı" ve
"Promosyon Etkileşim Oranları" olduğu matematiksel olarak
kanıtlanarak stratejik pazarlama aksiyonları için temel
oluşturuldu.

## 🚀 Nasıl Çalıştırılır?
İlgili `.ipynb` dosyasını Jupyter Notebook veya Google Colab üzerinden açarak kodları inceleyebilirsiniz.

1. Giriş 
Bu proje, bir e-ticaret sitesinin müşteri churn (müşteri kaybı) durumunu analiz etmeyi ve bu 
durumu tahmin edebilmek için makine öğrenimi yöntemlerini kullanmayı amaçlamaktadır. 
Veri seti, kullanıcıların siteye olan etkileşimlerini, alışveriş davranışlarını ve diğer demografik 
bilgilerini içermektedir. Bu projede, çeşitli veri işleme ve modelleme teknikleri uygulanarak, 
churn durumu tahmin edilmiştir. 
2. Veri Seti Tanımlaması 
Veri seti, e-ticaret sitesi kullanıcılarının davranış verilerini içeren bir dizi sütundan 
oluşmaktadır. Verilerdeki ana hedef değişken, kullanıcıların 'Churn' (terk etme) durumudur. 
2.1 Veri Kaynağı: 
  
Bu çalışma, Kaggle platformundan edinilen Digital Marketing | E-Commerce | 
Customer Behavior (252.95 kB) 
2.2 Veri Sütunları: 
 Kategorik Sütunlar: Lokasyon_Kodu, Bildirim_İzni, Kredi_Kartı_Kaydedildi 
 Sayısal Sütunlar: Üyelik_Süresi_Gün, İstek_Listesi_Sayısı, 
Masaüstü_Oturum_Sayısı, Uygulama_Oturum_Sayısı, Masaüstü_Alışveriş_Sayısı, 
Ürün_Detay_Görüntüleme_Sayısı, Ortalama_Oturum_Süresi, 
Promosyon_Tıklama_Sayısı, Ortalama_Sipariş_Değeri, 
İndirimli_Ürün_Görüntüleme_Sayısı, Ürün_Bazlı_İndirim_Oranı, 
Uygulama_Oturumu_Başına_Detay_Görüntüleme, Uygulama_Alışveriş_Sayısı, 
Oturum_Başına_Sepete_Ekleme, Müşteri_Hizmetleri_Arama_Sayısı 
2.3 Hedef Değişken: 
 Churn: Kullanıcının e-ticaret sitesini terk edip etmediğini gösteren bir hedef 
değişkendir. 
3. Veri Ön İşleme ve Temizleme Aşamaları 
3.1 Veri Tipi ve Eksik Veri Kontrolü 
İlk olarak, veri setindeki tüm sütunların veri tipleri kontrol edilmiştir. Verinin doğru tipte 
olduğunu ve eksik değerlerin bulunmadığını belirledik: 
 İkili Kodlama (Binary Encoding): "yes" ve "no" gibi iki değerli kategorik 
değişkenler, sırasıyla 1 ve 0 değerine dönüştürme işlemi yapıldı.  
 Veri Türleri: 4 adet float64, 16 adet int64 veri tipi. 
 Eksik Değer: Veri setinde herhangi bir eksik değer bulunmamaktadır. 
3.2 Kullanıcı_ID Sütununun Çıkarılması

### 1. Sayısal Değişkenlerin Dağılım Analizi
![Sayısal Değişkenlerin Dağılım Analizi](images/1.png)
<br><br>
