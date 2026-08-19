# Finansal Müşteri İlişkileri Yönetimi Uygulaması

Finansal Müşteri İlişkileri Yönetimi Uygulaması, kişisel veya kurumsal finansal verilerinizi, banka hesaplarınızı, harcamalarınızı ve faturalarınızı yönetebileceğiniz kapsamlı bir masaüstü uygulamasıdır. C# ve Windows Forms kullanılarak geliştirilmiş olup, veritabanı işlemleri için Entity Framework (.NET Framework) tercih edilmiştir.

## 🚀 Özellikler

Uygulama temel olarak 3 ana modülden (formdan) oluşmaktadır:

### 1. Dashboard (Gösterge Paneli)
- **Genel Bakış:** Toplam banka bakiyenizi ve en son gerçekleşen banka işleminin tutarını anlık olarak görebilirsiniz.
- **Grafiksel Analiz:** 
  - Banka bakiyelerinizi karşılaştırmalı olarak gösteren **Sütun Grafiği** (Bar Chart).
  - Fatura ve ödeme tutarlarınızın oransal dağılımını gösteren **Halka Grafiği** (Doughnut Chart).
- **Dinamik Fatura Takibi:** Arka planda çalışan bir zamanlayıcı (Timer) sayesinde; Elektrik, Doğalgaz, Su ve İnternet faturaları gibi periyodik ödemeleriniz döngüsel olarak gösterge panelinde ekrana yansıtılır.

### 2. Bankalar (Banks Form)
- **Banka Bakiyeleri:** Ziraat Bankası, Vakıfbank ve İş Bankası gibi farklı hesaplarınızdaki güncel bakiyeleri tek ekrandan görüntüleme.
- **Son İşlemler:** Veritabanına kayıtlı en son 5 banka hareketini (tarih, açıklama ve tutar bilgisiyle birlikte) kronolojik olarak özet halinde görebilirsiniz.

### 3. Ödeme & Faturalar (Billing Form)
- **Fatura Yönetimi:** Sisteme kayıtlı tüm faturaları DataGridView bileşeni üzerinde detaylı olarak listeleyebilirsiniz.
- **CRUD İşlemleri (Ekleme/Silme/Güncelleme):**
  - Yeni fatura ve ödeme kayıtları oluşturma.
  - Mevcut fatura bilgilerini (Başlık, Tutar, Periyot) güncelleme.
  - Ödenmiş veya iptal edilmiş faturaları id bazlı sistemden silme.

## 🛠 Kullanılan Teknolojiler

- **Programlama Dili:** C#
- **Platform:** .NET Framework 4.7.2, Windows Forms
- **Veri Erişim Teknolojisi (ORM):** Entity Framework (Database First yaklaşımı / EDMX)
- **Veritabanı:** MS SQL Server
- **Görselleştirme:** System.Windows.Forms.DataVisualization.Charting
- **Sorgulama:** LINQ to Entities

## ⚙️ Kurulum ve Çalıştırma Yönergeleri

Projeyi kendi bilgisayarınızda derleyip çalıştırmak için aşağıdaki adımları izleyebilirsiniz:

1. Bu depoyu (repository) yerel ortamınıza klonlayın:
   ```bash
   git clone <github-repo-url>
   ```
2. `MyFinancialCrm.sln` çözüm dosyasını **Visual Studio** ile açın.
3. Proje bağımlılıklarını (Entity Framework) indirmek için **NuGet Package Manager** üzerinden paketleri geri yükleyin (Restore NuGet Packages).
4. SQL Server Management Studio (SSMS) üzerinde gerekli veritabanını ve tabloları (`Banks`, `Bills`, `BankProcesses`, vb.) oluşturun veya Entity Framework Model'inden veritabanı script'ini üreterek (Generate Database from Model) çalıştırın.
5. Projedeki `App.config` dosyasını açıp, `<connectionStrings>` etiketi altında yer alan `FinancialCrmDbEntities1` bağlantı dizesini (Connection String) kendi lokal SQL sunucu bilgilerinize göre güncelleyin.
6. Uygulamayı başlatın (F5 veya Start butonu).

## 📸 Uygulamadan Görüntüler
*(Uygulamanın Dashboard, Bankalar ve Faturalar ekranlarına ait ekran görüntülerini ilerleyen aşamalarda buraya ekleyebilirsiniz.)*

---
*Bu uygulama, C# Windows Forms ve Entity Framework konularında pratik yapmak, UI ve veritabanı bağlama (Data Binding) operasyonlarını kavramak amacıyla geliştirilmiştir.*
