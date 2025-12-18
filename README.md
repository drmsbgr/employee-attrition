# 📊 İK Analitiği: Çalışan İstifası ve Performans Tahmini (HR Analytics)

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Library](https://img.shields.io/badge/Library-Scikit--Learn-orange)
![Interface](https://img.shields.io/badge/Interface-Gradio-purple)
![Platform](https://img.shields.io/badge/Platform-Google%20Colab-yellow)

Bu proje, veri madenciliği ve makine öğrenmesi teknikleri kullanılarak çalışanların şirketten ayrılma (attrition) olasılıklarını tahmin etmek ve İnsan Kaynakları departmanına stratejik içgörüler sunmak amacıyla geliştirilmiştir.

## 📝 Proje Konusu ve Amacı
Bu proje, çalışanların şirketten ayrılma (Attrition) risklerini hem Klasik Makine Öğrenmesi hem de 1D-CNN (Convolutional Neural Networks) mimarileri kullanarak tahmin eder. Projenin farkı, sadece tahmin yapmak değil, SHAP (Explainable AI) ile modelin kararlarını şeffaf hale getirmesidir.

## 🔗 Veri Seti Kaynağı
Projede IBM veri bilimcileri tarafından oluşturulan ve Kaggle üzerinde paylaşılan **IBM HR Analytics Employee Attrition & Performance** veri seti kullanılmıştır.

- **Veri Kaynağı:** [Kaggle - IBM HR Analytics Dataset](https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-attrition-dataset)
- **Veri Boyutu:** 1470 Satır, 35 Sütun (Öznitelik)
- **Veri Tipi:** Yapısal Veri (Structured Data)

## 📝 Güncellenmiş Proje Kapsamı
Proje, IBM HR veri setindeki 34 özelliği analiz ederek en yüksek ağırlığa sahip 8 kritik parametreyi belirlemiş ve bu parametrelerle hibrit bir tahmin sistemi kurmuştur.

Kullanılan 8 Kritik Özellik:
- Fazla Mesai (OverTime): En baskın istifa tetikleyicisi.
- Aylık Gelir (MonthlyIncome): Finansal tatmin düzeyi.
- Toplam Çalışma Yılı (TotalWorkingYears): Kariyer olgunluğu.
- Eve Uzaklık (DistanceFromHome): İş-yaşam dengesi.
- Yaş (Age): Demografik hareketlilik.
- Medeni Durum (MaritalStatus): Sosyal bağlılık faktörü.
- Hisse Opsiyon Seviyesi (StockOptionLevel): Şirket içi aidiyet ve teşvik.
- Çalışılan Şirket Sayısı (NumCompaniesWorked): Çalışanın piyasadaki hareketlilik geçmişi.

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
| **Support Vector Machine (SVM)** | %85.03 | En yüksek doğruluk oranına sahip model. |
| **K-Nearest Neighbors (KNN)** | %82.65 | Mesafe temelli sınıflandırma. |
| **Logistic Regression** | %85.37 | Temel referans (baseline) modeli. |
| **Random Forest** | **%83.33** | **Önceki seferde kullanılan model** |
| **CNN** | **%86.39** | **(Seçilen Model)** |

## 📊 SHAP ile Karar Açıklanabilirliği
Projede SHAP (SHapley Additive exPlanations) kullanılarak modelin "kara kutu" olmasının önüne geçilmiştir.

Global Önem: Hangi özelliklerin genel istifa eğilimini yönettiği görselleştirilmiştir.

Bireysel Tahmin: Her bir çalışan için riskin neden yüksek veya düşük olduğu matematiksel olarak açıklanmıştır.

## 🖥️ İnteraktif Demo (Gradio Arayüzü)
Geliştirilen arayüz, İK uzmanlarının teknik bilgiye ihtiyaç duymadan risk analizi yapmasına olanak tanır.

- Girdi: 8 farklı çalışan verisi.

- Çıktı: % cinsinden risk oranı ve sistem tarafından üretilen aksiyon önerisi.

Sistem, girilen verilere göre çalışanın istifa etme ihtimalini **yüzdesel (%)** olarak hesaplar ve risk durumuna göre uyarı verir.

## 👨‍💻 Geliştirici
**Buğra DURMUŞ**

---
*Bu proje Veri Madenciliği ve Bilgi Keşfi dersi kapsamında hazırlanmıştır.*
