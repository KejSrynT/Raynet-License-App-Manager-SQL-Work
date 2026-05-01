## 📅 1. Gün: Temeller ve Veri Çekme (SELECT)

Veritabanı, verilerin bulunduğu dijital bir kütüphanedir. **SQLite** ise bu kütüphanenin kendisidir.

- **New Database:** DB Browser'da "New Database" dediğinde aslında boş bir `.db` dosyası oluşturursun.
    
- **Tablo Yapısı:** Veriler sütunlardan oluşur. Örneğin `ogrenci_id` (sayı), `ad` (metin) gibi.
    

### Temel Komutlar:

Veri çekmek için her zaman `SELECT` (ne getirilecek) ve `FROM` (nereden getirilecek) ikilisini kullanırız.

SQL

```
-- Tüm tabloyu olduğu gibi gör
SELECT * FROM Applications;

-- Sadece uygulama adlarını listele
SELECT app_name FROM Applications;
```

---

## 📅 2. Gün: Filtreleme ve Analiz (WHERE & Operatörler)

Kütüphanede aradığın kitabı bulmak gibi, milyonlarca veri içinden sadece istediğini çekmektir.

- **WHERE:** Belirli bir şartı sağlayanları getirir.
    
- **Mantıksal Operatörler:** `AND` (ve), `OR` (veya).
    
- **LIKE:** Metin içinde arama yapar. `%` işareti "herhangi bir şey" demektir.
    
- **Sıralama:** `ORDER BY` (Sırala) ve `LIMIT` (Sadece şu kadarını göster).
    

SQL

```
-- Kategorisi 'Development' olan VE ülkesi 'USA' olanları getir
SELECT * FROM Applications 
WHERE category = 'Development' AND country = 'USA';

-- İsmi 'M' ile başlayanları alfabetik sırala ve ilk 3 sonucu ver
SELECT * FROM Vendors 
WHERE vendor_name LIKE 'M%'
ORDER BY vendor_name ASC
LIMIT 3;
```

---

## 📅 3. Gün: İlişkisel Veritabanı ve JOIN

İşte siber güvenlikçiler için en önemli kısım. Veritabanları genellikle birbiriyle bağlantılı birden fazla tablodan oluşur.

- **Primary Key (Birincil Anahtar):** Bir tablodaki her satırın eşsiz kimliğidir (Örn: `app_id`).
    
- **Foreign Key (Yabancı Anahtar):** Başka bir tabloyla bağ kuran sütundur.
    
- **INNER JOIN:** İki tablonun kesiştiği (ortak olan) verileri birleştirir.
    

SQL

```
-- Uygulama adını ve üretici şirket ismini yan yana getir
-- (Applications tablosundaki vendor_id ile Vendors tablosundaki vendor_id'yi eşle)
SELECT Applications.app_name, Vendors.vendor_name
FROM Applications
INNER JOIN Vendors ON Applications.vendor_id = Vendors.vendor_id;
LEFT JOIN Vendors ON Applications.vendor_id = Vendors.vendor_id;
```

---

## 📅 4. Gün: Veri Manipülasyonu ve Kayıt (DML)

Veritabanına yeni bir şeyler eklemek, olanı değiştirmek veya silmek için kullanılır.

- **INSERT INTO:** Yeni satır ekler.
    
- **UPDATE:** Var olan veriyi günceller (**Dikkat:** `WHERE` kullanmazsan her şey değişir!).
    
- **DELETE:** Veriyi siler (**Dikkat:** `WHERE` kullanmazsan her şey silinir!).
    

SQL

```
-- Yeni bir üretici ekle
INSERT INTO Vendors (vendor_id, vendor_name, country) 
VALUES (4, 'Adobe', 'USA');

-- ID'si 101 olan uygulamanın kategorisini güncelle
UPDATE Applications 
SET category = 'Office Suite' 
WHERE app_id = 101;

DELETE FROM Tablo_Adı WHERE Koşul;
```

### ⚠️ Kritik Operasyon: "Write Changes"

DB Browser'da kod yazıp çalıştırdığında bu değişiklikler geçici hafızada durur. Eğer sağ üstteki **"Write Changes"** butonuna basmazsan, programı kapattığında tüm yaptıkların (ekleme, silme, güncelleme) kaybolur. **Mutlaka her işlemden sonra bas!**

---

### Özet Uygulama Rehberi:

1. **DB Browser'ı aç**, hocanın verdiği uzun kodu "Execute SQL" sekmesine yapıştır ve **Play** tuşuna bas.
    
2. Ardından **Write Changes**'e bas ki tabloların kalıcı olsun.
    
3. Hocanın görevlerini (Sorgu, filtreleme vb.) yeni bir SQL sayfasında tek tek dene.
    
4. Bitince dosyayı kaydetmeyi unutma!

[[Meaning of SQL AND DATABASE]]