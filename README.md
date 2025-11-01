# 🧠 Makine Öğrenmesi Araçlarıyla Duygusal Dinamikleri Analiz Etmek

[![Python Version](https://img.shields.io/badge/python-3.8%2B-blue.svg)](https://www.python.org/downloads/)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)

Makine öğrenmesi araçlarını kullanarak ikili ilişkilerdeki duygusal dinamikleri Spearman korelasyon analizi ile inceleme.

## 📰 Blog Yazısı

Bu projenin detaylı açıklaması ve teorik altyapısı için LinkedIn yazım:

👉 **[Makine Öğrenmesi Araçlarıyla Duygusal Dinamikleri Analiz Etmek](linkedin-linkiniz)**

Yazıda şunları bulacaksınız:
- 📚 Korelasyon teorisi (Pearson vs Spearman)
- 🧮 Multicollinearity nedir?
- 💡 Mühendislik perspektifinden ilişki analitiği
- 📊 Psikolojik değişken tanımları

---

## 🎯 Proje Özeti

**Bulgular:**
- Spearman ρ = 0.929 (p = 0.003)
- Mehmet'in stresi ↔ İrem'in tepkiselliği: **Güçlü pozitif korelasyon**
- Multicollinearity tespiti: İrem_Tepkisellik ↔ İrem_Gerginlik (ρ = 1.00)

**Kullanılan Yöntemler:**
✅ Spearman korelasyon analizi  
✅ İkili, üçlü ve çok değişkenli korelasyon  
✅ Görselleştirme (Scatter, Heatmap, Bar charts)  
✅ Multicollinearity tespiti

---

## 🚀 Hızlı Başlangıç

### Kurulum
```bash
# Repo'yu klonla
git clone https://github.com/kullaniciadin/relationship-correlation-analysis.git
cd relationship-correlation-analysis

# Virtual environment oluştur
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate

# Paketleri yükle
pip install -r requirements.txt

# Jupyter başlat
jupyter notebook
```

### Kullanım
```python
import pandas as pd
from scipy.stats import spearmanr

# Veriyi yükle
data = pd.read_csv('data/mehmet_irem_data.csv')

# Spearman hesapla
rho, p = spearmanr(data['Mehmet_Stres'], data['Irem_Tepkisellik'])
print(f"Spearman ρ = {rho:.3f} (p = {p:.3f})")
```

---

## 📁 Proje Yapısı
```
├── notebooks/          # Jupyter Notebook analizleri
├── data/              # CSV veri setleri
├── src/               # Yardımcı fonksiyonlar
├── images/results/    # Çıktı görselleri
└── README.md          # Bu dosya
```

---

## 📚 Kaynaklar

Detaylı kaynak listesi için [LinkedIn yazıma](linkedin-linkiniz) bakınız.

**Temel kaynaklar:**
- Spearman, C. (1904). The proof and measurement of association
- Gottman, J. M. (1999). The Marriage Clinic
- McKinney, W. (2012). Python for Data Analysis

---

## 🤝 Katkıda Bulunma

Pull request'ler memnuniyetle karşılanır!

## 📄 Lisans

MIT License

---

⭐ Bu projeyi beğendiyseniz yıldız vermeyi unutmayın!