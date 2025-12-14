# 📊 İK Analitiği: Çalışan İstifası ve Performans Tahmini (HR Analytics)

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Library](https://img.shields.io/badge/Library-Scikit--Learn-orange)
![Interface](https://img.shields.io/badge/Interface-Gradio-purple)
![Platform](https://img.shields.io/badge/Platform-Google%20Colab-yellow)

Bu proje, veri madenciliği ve makine öğrenmesi teknikleri kullanılarak çalışanların şirketten ayrılma (attrition) olasılıklarını tahmin etmek ve İnsan Kaynakları departmanına stratejik içgörüler sunmak amacıyla geliştirilmiştir.

## 📝 Proje Konusu ve Amacı
Şirketler için nitelikli çalışanları elde tutmak (retention), yeni çalışan bulmaktan daha az maliyetlidir. Bu projenin temel amacı:
1.  Çalışanların **istifa etme olasılıklarını** makine öğrenmesi ile önceden tespit etmek.
2.  Sadece tahmin yapmak değil, **"Çalışanlar neden ayrılıyor?"** sorusuna cevap vererek kök nedenleri (fazla mesai, maaş, uzaklık vb.) analiz etmek.

## 🔗 Veri Seti Kaynağı
Projede IBM veri bilimcileri tarafından oluşturulan ve Kaggle üzerinde paylaşılan **IBM HR Analytics Employee Attrition & Performance** veri seti kullanılmıştır.

- **Veri Kaynağı:** [Kaggle - IBM HR Analytics Dataset](https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-attrition-dataset)
- **Veri Boyutu:** 1470 Satır, 35 Sütun (Öznitelik)
- **Veri Tipi:** Yapısal Veri (Structured Data)

## ⚙️ Kullanılan Yöntemler ve Teknolojiler
Proje **Python** dili kullanılarak **Google Colab** ortamında geliştirilmiştir. Aşağıdaki kütüphaneler ve algoritmalar kullanılmıştır:

### Kütüphaneler
* **Veri İşleme:** Pandas, NumPy
* **Görselleştirme:** Matplotlib, Seaborn
* **Makine Öğrenmesi:** Scikit-learn (sklearn)
* **Arayüz (UI):** Gradio

### Algoritmalar ve Model Karşılaştırması
Proje kapsamında 4 farklı sınıflandırma algoritması eğitilmiş ve performansları karşılaştırılmıştır:

| Model | Doğruluk (Accuracy) | Açıklama |
| :--- | :---: | :--- |
| **Support Vector Machine (SVM)** | %87.53 | En yüksek doğruluk oranına sahip model. |
| **K-Nearest Neighbors (KNN)** | %87.30 | Mesafe temelli sınıflandırma. |
| **Logistic Regression** | %86.62 | Temel referans (baseline) modeli. |
| **Random Forest** | **%85.71** | **(Seçilen Model)** |

### 🚀 Neden Random Forest Seçildi?
Tabloda görüldüğü üzere SVM en yüksek doğruluğu vermiş olsa da, proje için nihai model olarak **Random Forest** seçilmiştir. Bunun nedenleri:
1.  **Yorumlanabilirlik (Explainability):** İK yönetimine "Neden?" sorusunun cevabını verebilmek için Random Forest'ın `feature_importances_` özelliği kullanılmıştır.
2.  **Dengesiz Veri:** Veri setindeki dengesizliğe (Imbalanced Data) karşı karar ağacı tabanlı yapıların daha dirençli olması.

## 🖥️ İnteraktif Demo (Gradio Arayüzü)
Projenin son kullanıcı (İK Uzmanları) tarafından kolayca deneyimlenmesi amacıyla **Gradio** kütüphanesi kullanılarak web tabanlı bir arayüz geliştirilmiştir.

Kullanım kolaylığı sağlamak adına, 35 sütunluk veri seti içerisinden **en kritik 5 özellik** seçilerek model bu özelliklerle optimize edilmiştir. Kullanıcılar aşağıdaki parametreleri girerek anlık risk analizi yapabilirler:

1.  **Fazla Mesai (OverTime)**
2.  **Aylık Gelir (MonthlyIncome)**
3.  **Toplam Çalışma Yılı (TotalWorkingYears)**
4.  **Eve Uzaklık (DistanceFromHome)**
5.  **Yaş (Age)**

Sistem, girilen verilere göre çalışanın istifa etme ihtimalini **yüzdesel (%)** olarak hesaplar ve risk durumuna göre uyarı verir.

## 📊 Önemli Bulgular
Modelin analizine göre istifayı tetikleyen en önemli 3 faktör:
1.  **OverTime (Fazla Mesai):** Evet olanlarda risk çok yüksektir.
2.  **MonthlyIncome:** Düşük gelir grubu risk altındadır.
3.  **TotalWorkingYears:** Kariyerinin başındaki çalışanlar daha hareketlidir.

## 👨‍💻 Geliştirici
**Buğra DURMUŞ**

---
*Bu proje Veri Madenciliği ve Bilgi Keşfi dersi kapsamında hazırlanmıştır.*
