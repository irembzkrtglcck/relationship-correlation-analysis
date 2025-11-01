# Makine Öğrenmesi Araçlarıyla Duygusal Dinamikleri Analiz Etmek

**Proje:** İkili ilişkilerde korelasyon analizi - Spearman korelasyonu ile duygusal dinamiklerin sayısal incelenmesi

**Yazar:** İrem Bozkurt Gülçiçek  
**Tarih:** 2025  
**Lisans:** MIT

---

## Proje Hakkında

Bu proje, makine öğrenmesinde kullanılan korelasyon analizlerini ikili ilişkilerdeki duygusal dinamiklere uygulamaktadır. Elektrik-elektronik mühendisliği perspektifinden, psikolojik verilerin Python araçlarıyla nasıl analiz edilebileceğini göstermektedir.

**Amaç:** İlişki psikolojisinde sıklıkla kullanılan korelasyon analizlerini, mühendislik bakış açısıyla, adım adım kod ile uygulamak ve multicollinearity gibi makine öğrenmesi kavramlarını ilişki dinamiklerine taşımak.

---

## Detaylı Açıklama

Projenin teorik altyapısı, bulguların yorumlanması ve psikolojik bağlam için LinkedIn blog yazısı:

**LinkedIn:** [Makine Öğrenmesi Araçlarıyla Duygusal Dinamikleri Analiz Etmek](https://www.linkedin.com/pulse/bir-elektrik-elektronik-m%C3%BChendisinin-psikoloji-merak%C4%B1-i%CC%87rem-7b00f/?trackingId=lrRhghL2idYDa7PmCXtYtw%3D%3D)

Yazıda bulacaklarınız:
- Korelasyon teorisi (Pearson vs Spearman)
- Multicollinearity nedir ve neden önemlidir?
- Pozitif ve negatif korelasyonlar
- Kısır döngüler ve sistemik yaklaşım
- Psikolojik değişken tanımları ve yorumlar

---

## Temel Bulgular

### İkili Değişkenli Analiz
- **Mehmet'in Stresi - İrem'in Tepkiselliği:** Spearman ρ = 0.929 (p = 0.003)
- **Yorum:** Güçlü pozitif korelasyon - duygusal bulaşma fenomeni

### Üç Değişkenli Analiz
- **Mehmet'in Stresi - Mehmet'in İletişimi:** ρ = 0.714 (p = 0.048)
- **Yorum:** Stres arttıkça iletişim çabası artıyor

### Çok Değişkenli Analiz
**Pozitif Korelasyonlar:**
- Stres - Tepkisellik: ρ = +0.93
- Mutluluk - Ortak Aktivite: ρ = +0.99
- Empati - Mutluluk: ρ = +0.79

**Negatif Korelasyonlar:**
- Stres - Mutluluk: ρ = -0.93
- Tepkisellik - Mutluluk: ρ = -1.00
- Tepkisellik - Ortak Aktivite: ρ = -0.99

**Multicollinearity Tespiti:**
- Tepkisellik = Gerginlik (ρ = 1.00)
- Tepkisellik vs Mutluluk (ρ = -1.00)

**Kısır Döngü:**
Stres → Tepkisellik → Mutsuzluk → Az Ortak Zaman → Daha Fazla Stres

---

## Kullanılan Yöntemler

- Spearman korelasyon analizi (sıralı veriler için)
- İkili, üçlü ve çok değişkenli korelasyon matrisleri
- Görselleştirme: Scatter plot, heatmap, bar chart, histogram
- Multicollinearity tespiti
- İstatistiksel anlamlılık testleri (p-değeri)

---

## Teknolojiler

**Programlama Dili:** Python 3.8+

**Kütüphaneler:**
- pandas 1.3.0+ (Veri manipülasyonu)
- numpy 1.21.0+ (Sayısal hesaplamalar)
- scipy 1.7.0+ (İstatistiksel testler)
- matplotlib 3.4.0+ (Görselleştirme)
- seaborn 0.11.0+ (İstatistiksel grafikler)
- jupyter 1.0.0+ (İnteraktif analiz)

---

## Kurulum

### Gereksinimler
```bash
python >= 3.8
```

### Adım 1: Repository'yi Klonlayın
```bash
git clone https://github.com/irembzkrtglcck/relationship-correlation-analysis.git
cd relationship-correlation-analysis
```

### Adım 2: Virtual Environment Oluşturun (Önerilen)
```bash
# Windows
python -m venv venv
venv\Scripts\activate

# macOS/Linux
python3 -m venv venv
source venv/bin/activate
```

### Adım 3: Gerekli Paketleri Yükleyin
```bash
pip install -r requirements.txt
```

### Adım 4: Jupyter Notebook'u Başlatın
```bash
jupyter notebook
```

Tarayıcınızda otomatik olarak açılacak. `notebooks/` klasöründen analiz dosyalarına erişebilirsiniz.

---

## Kullanım

### Hızlı Başlangıç
```python
import pandas as pd
from scipy.stats import spearmanr

# Veriyi yükle
data = pd.read_csv('data/mehmet_irem_data.csv')

# Spearman korelasyonu hesapla
rho, p_value = spearmanr(data['Mehmet_Stres'], data['Irem_Tepkisellik'])

print(f"Spearman ρ = {rho:.3f}")
print(f"p-değeri = {p_value:.3f}")
```

**Çıktı:**
```
Spearman ρ = 0.929
p-değeri = 0.003
```

### Jupyter Notebook Analizleri

Projedeki tüm analizler Jupyter Notebook formatında hazırlanmıştır:

1. **01_ikili_degiskenli_analiz.ipynb**
   - İki değişkenli korelasyon
   - Manuel Spearman hesaplama
   - Scipy ile doğrulama
   - Scatter plot ve heatmap görselleştirmeleri

2. **02_uc_degiskenli_analiz.ipynb**
   - Üç değişkenli korelasyon matrisi
   - İletişim faktörünün etkisi
   - İstatistiksel anlamlılık testleri

3. **03_cok_degiskenli_analiz.ipynb**
   - Yedi değişkenli korelasyon matrisi
   - Multicollinearity tespiti
   - Pozitif ve negatif korelasyonlar
   - Kısır döngü analizi
   - Düzeltilmiş model (değişken çıkarma)

---

## Proje Yapısı
```
relationship-correlation-analysis/
│
├── README.md                          # Bu dosya
├── requirements.txt                   # Python bağımlılıkları
├── LICENSE                            # MIT Lisans
│
├── notebooks/                         # Jupyter Notebook analizleri
│   ├── 01_ikili_degiskenli_analiz.ipynb
│   ├── 02_uc_degiskenli_analiz.ipynb
│   └── 03_cok_degiskenli_analiz.ipynb
│
├── data/                              # Veri setleri
│   ├── mehmet_irem_data.csv           # İkili değişkenli veri
│   ├── three_variable_data.csv        # Üç değişkenli veri
│   └── seven_variable_data.csv        # Çok değişkenli veri
│
├── images/                            # Görsel çıktılar
│   └── results/
│       ├── gorsel_1_iki_degisken.png
│       ├── gorsel_2_uc_degisken.png
│       ├── gorsel_3_multicollinearity.png
│       ├── gorsel_4_kapsamli_multicollinearity.png
│       └── gorsel_5_duzeltilmis_matris.png
│
└── src/                               # Yardımcı Python modülleri (opsiyonel)
    └── correlation_utils.py
```

---

## Veri Setleri

### 1. İkili Değişkenli Veri (mehmet_irem_data.csv)

7 günlük öznel gözlem verisi:
- **Mehmet_Stres:** Günlük stres seviyesi (1-10)
- **Irem_Tepkisellik:** Günlük tepkisellik seviyesi (1-10)

### 2. Üç Değişkenli Veri (three_variable_data.csv)

İkili veriye ek olarak:
- **Mehmet_Iletisim:** İletişim kurma gayreti (1-10)

### 3. Çok Değişkenli Veri (seven_variable_data.csv)

Yedi değişken:
- Mehmet_Stres
- Irem_Tepkisellik
- Mehmet_Iletisim
- Irem_Mutluluk
- Mehmet_Empati
- Ortak_Aktivite
- Irem_Gerginlik

**Not:** Tüm değişkenler öznel puanlamadır (1-10 arası Likert tipi ölçek).

---

## Metodoloji

### Neden Spearman Korelasyonu?

**Spearman Korelasyonu (ρ) kullanıldı çünkü:**
- Veriler sıralı (ordinal) yapıda
- Öznel puanlama (1-10)
- Normal dağılım varsayımı gerektirmiyor
- Monotonik ilişkileri yakalıyor
- Aykırı değerlere karşı daha dayanıklı

**Pearson vs Spearman:**
- Pearson: Doğrusal ilişki, interval/ratio veri, normal dağılım varsayımı
- Spearman: Monotonik ilişki, ordinal veri, dağılım varsayımı yok

### Korelasyon Yorumlama

**Güç Kategorileri:**
- |ρ| > 0.90: Çok güçlü
- |ρ| 0.70-0.89: Güçlü
- |ρ| 0.40-0.69: Orta
- |ρ| 0.10-0.39: Zayıf
- |ρ| < 0.10: Çok zayıf / Yok

**İstatistiksel Anlamlılık:**
- p < 0.05: İstatistiksel olarak anlamlı
- p ≥ 0.05: İstatistiksel olarak anlamlı değil

---

## Temel Kavramlar

### Multicollinearity (Çoklu Doğrusal Bağlantı)

**Tanım:** İki veya daha fazla değişkenin birbiriyle çok yüksek korelasyona sahip olması.

**Tespit:**
- Korelasyon matrisi: |ρ| ≥ 0.95
- Bu projede tespit edilen: Tepkisellik = Gerginlik (ρ = 1.00)

**Problem:**
- Model hangisinin etkili olduğunu ayırt edemiyor
- Regresyon katsayıları kararsız oluyor
- Yorumlama zorlaşıyor

**Çözüm:**
- Değişken çıkarma (en basit)
- Değişkenleri birleştirme
- PCA (Principal Component Analysis)
- Ridge/Lasso regresyon

### Pozitif vs Negatif Korelasyon

**Pozitif (ρ > 0):**
- İki değişken birlikte artıyor veya azalıyor
- Örnek: Stres artar → Tepkisellik artar

**Negatif (ρ < 0):**
- Biri artarken diğeri azalıyor
- Örnek: Stres artar → Mutluluk azalır

---

## Sonuçlar ve Çıkarımlar

### İstatistiksel Sonuçlar

1. **Güçlü Pozitif İlişki:** Mehmet'in stresi ile İrem'in tepkiselliği (ρ = 0.929, p = 0.003)

2. **Multicollinearity Tespiti:** Tepkisellik ve Gerginlik tamamen aynı değişken (ρ = 1.00)

3. **Negatif Korelasyonlar:** Stres ile Mutluluk ters orantılı (ρ = -0.93)

4. **Kısır Döngü:** Stres → Tepkisellik → Mutsuzluk → Az Ortak Zaman → Daha Fazla Stres

### Psikolojik Yorumlar

**Duygusal Bulaşma:**
- Mehmet'in stresi İrem'i doğrudan etkiliyor
- İlişkilerde duygusal bulaşma fenomeni gözlemleniyor

**Sistemik Yaklaşım:**
- Bir değişken diğerlerini etkiliyor
- İlişki bir sistem olarak işliyor
- Erken müdahale önemli

**Pratik Öneriler:**
- Stres yönetimi bireysel değil, ilişkisel bir konudur
- İletişim ve empati koruyucu faktörler
- Ortak aktiviteler ilişkiyi güçlendirir

### Metodolojik Katkılar

1. **Öznel Verilerle Çalışma:** Spearman > Pearson

2. **Görselleştirme:** Heatmap, scatter plot, 4 panel analiz

3. **Multicollinearity Farkındalığı:** Çok değişkenli analizde dikkatli olunmalı

4. **Adım Adım Kod:** Şeffaf ve tekrarlanabilir analiz

---

## Sınırlılıklar

1. **Küçük Örneklem:** n=7 (İstatistiksel güç sınırlı)

2. **Öznel Puanlama:** Ölçüm hatası olabilir

3. **Kesitsel Veri:** Zaman içi değişim gösterilmiyor

4. **Korelasyon ≠ Nedensellik:** İlişki var ama sebep-sonuç belirsiz

5. **Tek Haftalık Veri:** Uzun dönem trend bilinmiyor

---

## Gelecek Çalışmalar

**Önerilen İyileştirmeler:**

1. **Daha Uzun Veri Toplama:** 30-90 gün

2. **Daha Sık Ölçüm:** Günde 3-5 kez (ESM - Experience Sampling Method)

3. **Objektif Ölçümler Eklemek:**
   - Kalp atış hızı
   - Uyku kalitesi (wearable cihazlar)
   - Kortizol seviyeleri

4. **Zaman Serisi Analizi:**
   - ARIMA modelleri
   - Granger nedensellik testi
   - Dinamik sistem modelleme

5. **Regresyon Modelleme:**
   - Çoklu regresyon
   - Ridge/Lasso
   - Random Forest

6. **Daha Fazla Çift:**
   - Farklı demografik gruplar
   - Karşılaştırmalı analizler

---

## Kaynaklar

**Detaylı kaynak listesi için LinkedIn blog yazısına ve notebook'lardaki referanslara bakınız.**

**Temel Kaynaklar:**

- Gottman, J. M. (1999). The Marriage Clinic: A Scientifically Based Marital Therapy
- Spearman, C. (1904). The proof and measurement of association between two things
- Karney, B. R., & Bradbury, T. N. (1995). The longitudinal course of marital quality and stability
- Dormann, C. F., et al. (2013). Collinearity: a review of methods to deal with it
- McKinney, W. (2012). Python for Data Analysis

---

## Katkıda Bulunma

Pull request'ler memnuniyetle karşılanır. Büyük değişiklikler için lütfen önce bir issue açarak ne değiştirmek istediğinizi tartışın.

**Katkı Yapabilecekleriniz:**
- Kod iyileştirmeleri
- Yeni görselleştirme yöntemleri
- İlave istatistiksel testler
- Farklı veri setleriyle deneme
- Dokümantasyon geliştirme

---

## Lisans

Bu proje MIT lisansı altındadır. Detaylar için LICENSE dosyasına bakınız.

---

## İletişim

**Yazar:** İrem Bozkurt Gülçiçek
**LinkedIn:** [https://www.linkedin.com/in/irembozkurt7/]  
**E-posta:** [7irembozkurt@gmail.com]  
**Blog:** [[LinkedIn Yazı Linki](https://www.linkedin.com/pulse/bir-elektrik-elektronik-m%C3%BChendisinin-psikoloji-merak%C4%B1-i%CC%87rem-7b00f/?trackingId=lrRhghL2idYDa7PmCXtYtw%3D%3D)]

---

## Teşekkürler

Bu proje, kaynak araştırması ve düzenleme sürecinde Claude AI desteğiyle hazırlanmıştır. Tüm içerik, fikir, yorum ve yorumlamalar yazara aittir.

---

**Not:** Bu bir eğitim projesidir. Veriler kurgusaldır ve gösterim amaçlıdır. Gerçek psikolojik araştırma yapmak için etik kurul onayı ve profesyonel danışmanlık gerekmektedir.