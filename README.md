# BG-NBD ve Gamma-Gamma ile CLTV Tahmini

## Proje Açıklaması ✨🚀🌟  
Bu proje, Miuul'un CRM analitiği eğitimi kapsamında geliştirilmiş bir case study'dir. FLO'nun satış ve pazarlama faaliyetleri için müşteri yaşam boyu değerini (Customer Lifetime Value - CLTV) tahmin ederek stratejik kararlar alınması hedeflenmiştir. BG-NBD ve Gamma-Gamma modelleri kullanılarak müşterilerin gelecekte şirkete sağlayacağı potansiyel değerin hesaplanması amaçlanmıştır.

## Kullanılan Teknolojiler 🛠️  
- Python: Genel programlama ve veri işleme için.  
- Pandas: Veri manipülasyonu ve analizi için.  
- NumPy: Sayısal işlemler ve veri yapılandırması için.  
- Matplotlib/Seaborn: Verilerin görselleştirilmesi için.  
- Lifetimes: BG-NBD ve Gamma-Gamma modellerinin uygulanması için.

## Veri Seti Bilgileri 📊  
Veri seti, FLO’nun 2020-2021 yılları arasında OmniChannel (hem online hem de offline) alışveriş yapan müşterilerinin geçmiş alışveriş davranışlarına dayanmaktadır. Aşağıdaki değişkenlerden oluşmaktadır:

- master_id: Eşsiz müşteri numarası  
- order_channel: Alışveriş yapılan platform (Android, iOS, Desktop, Mobile)  
- first_order_date: Müşterinin yaptığı ilk alışveriş tarihi  
- last_order_date: Müşterinin yaptığı son alışveriş tarihi  
- order_num_total_ever_online: Müşterinin online platformlarda yaptığı toplam alışveriş sayısı  
- order_num_total_ever_offline: Müşterinin offline platformlarda yaptığı toplam alışveriş sayısı  
- customer_value_total_ever_online: Müşterinin online alışverişlerde harcadığı toplam tutar  
- customer_value_total_ever_offline: Müşterinin offline alışverişlerde harcadığı toplam tutar  
- interested_in_categories_12: Müşterinin son 12 ayda alışveriş yaptığı kategoriler

## Proje Adımları ⚙️  

### Görev 1: Veriyi Hazırlama 🤔  
1. flo_data_20K.csv verisini okuyun.  
2. Aykırı değerleri baskılamak için gerekli fonksiyonları oluşturun.  
   - outlier_thresholds ve replace_with_thresholds fonksiyonları.
3. Belirli değişkenlerdeki (ör. order_num_total_ever_online, **customer_value_total_ever_online**) aykırı değerleri baskılayın.  
4. Müşterilerin toplam alışveriş sayısı ve harcaması için yeni değişkenler oluşturun.  
5. Tarih değişkenlerini datetime formatına çevirin.  

### Görev 2: CLTV Veri Yapısının Oluşturulması 🤩 
1. Analiz tarihi olarak veri setindeki en son alışveriş tarihinden 2 gün sonrasını alın.  
2. Yeni bir CLTV DataFrame oluşturun (**customer_id**, recency_cltv_weekly, T_weekly, frequency, **monetary_cltv_avg**).  

### Görev 3: BG/NBD ve Gamma-Gamma Modellerinin Kurulması  
1. BG-NBD modelini kurarak müşterilerin 3 ve 6 ay içinde beklenen satın almalarını tahmin edin.  
   - Sonuçları exp_sales_3_month ve exp_sales_6_month olarak kaydedin.  
2. Gamma-Gamma modelini kullanarak müşterilerin ortalama bırakacakları değeri tahmin edin (**exp_average_value**).  
3. 6 aylık CLTV'yi hesaplayarak cltv değişkenine ekleyin.  
   - En yüksek CLTV değerine sahip 20 müşteriyi gözlemleyin.  

### Görev 4: CLTV Değerine Göre Segmentlerin Oluşturulması  
1. Müşterileri 6 aylık CLTV değerine göre 4 segmente ayırın (ör. A, B, C, **D**).  
2. Segment bilgilerini veri setine ekleyin ve her segment için analiz yapın.  

## Lisans 📜  
Copyright © Miuul, Inc. All Rights Reserved
