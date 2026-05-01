
---

## 📂 1. Veritabanı (Database) Nedir?

Veritabanı, verilerin rastgele değil, belirli bir düzen içerisinde saklandığı **dijital bir depodur.**

Bir siber güvenlikçi olarak bunu şöyle düşünebilirsin: Bir sistemdeki kullanıcı adları, şifre karmaları (hash), log kayıtları veya ağ trafik verileri veritabanında saklanır.

- **Tablo Mantığı:** Veritabanları tablolardan oluşur. Excel dosyası gibi düşün; sütunlar (ID, Ad, Soyad) ve satırlar (Ahmet, Mehmet) vardır.
    
- **İlişkisellik:** Tablolar birbirine bağlıdır. Örneğin "Öğrenciler" tablosundaki bir öğrenci ID'si, "Notlar" tablosundaki bir notla eşleşir.
    

---

## 🛠️ 2. SQL Nedir? (Structured Query Language)

SQL, veritabanı ile konuşmak için kullandığımız **ortak dildir.** Veritabanı bir kütüphane ise, SQL o kütüphaneciden kitap isteme biçimimizdir.

- **Açılımı:** Yapılandırılmış Sorgu Dilidir.
    
- **Görevi:** Veritabanına "Şu veriyi getir", "Şu veriyi sil" veya "Şurayı güncelle" talimatlarını iletir.
    
- **Siber Güvenlikteki Önemi:** Eğer bir web sitesi kullanıcıdan aldığı veriyi düzgün filtrelemeden SQL'e gönderirse, saldırgan kendi SQL komutlarını çalıştırabilir. Buna **SQL Injection** denir ve en tehlikeli saldırı türlerinden biridir.
    

---

## 🤝 3. SQL ve Veritabanı Arasındaki Fark

|Özellik|Veritabanı (Database)|SQL|
|---|---|---|
|**Nedir?**|Verilerin saklandığı depo (Kütüphane).|Verileri yönetme dili (Kütüphaneciyle konuşmak).|
|**Fiziksel mi?**|Evet, bir dosyadır (.db, .sql, .mdb).|Hayır, sadece komut dizileridir.|
|**Örnek**|SQLite, MySQL, PostgreSQL, Oracle.|`SELECT`, `INSERT`, `UPDATE`, `DELETE`.|