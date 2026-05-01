Şu an elinde iki ayrı kağıt parçası (tablo) var:

1. **Applications (Uygulamalar) Kağıdı:** Burada uygulama isimleri (`app_name`) ve onları üretenlerin kimlik numaraları (`vendor_id`) yazıyor.
    
2. **Vendors (Üreticiler) Kağıdı:** Burada ise o kimlik numaralarının (`vendor_id`) hangi şirketlere (`vendor_name`) ait olduğu yazıyor.
    

Bu kodun yaptığı işi adım adım inceleyelim:

### 1. Seçim Aşaması (`SELECT`)

`SELECT Applications.app_name, Vendors.vendor_name` Burada veritabanına diyorsun ki: "Bana iki sütun getir; biri `Applications` tablosundaki uygulama ismi, diğeri `Vendors` tablosundaki şirket ismi olsun."

### 2. Kaynak Belirleme (`FROM`)

`FROM Applications` "İşe ilk olarak Uygulamalar tablosuna bakarak başla."

### 3. Masaları Birleştirme (`INNER JOIN ... ON ...`)

`INNER JOIN Vendors ON Applications.vendor_id = Vendors.vendor_id` İşin büyüsü burada. "Git `Vendors` tablosunu getir ve iki kağıdı üst üste koy. Ama sadece **kimlik numaraları (vendor_id) birbirine tam uyanları** eşleştir."