# 🛒 Market Segmenti və Xərc Analizi (SQL)

Bu layihə, bank müştərilərinin alış-veriş vərdişlərini mağaza kateqoriyalarına görə analiz etmək üçün hazırlanmışdır. Layihənin əsas məqsədi bankın hansı sektorlarda (Market, Restoran, Aptek və s.) daha çox dövriyyəyə malik olduğunu müəyyən etməkdir.

## 🛠️ Texniki Struktur
Layihədə 3 əsas cədvəl arasında **Relational (Əlaqəli)** struktur qurulmuşdur:
- **Cards:** Müştəri kart məlumatları.
- **Stores:** Mağaza adları və kateqoriyaları.
- **Transactions:** Kartlar və mağazalar arasındakı əlaqəni (Foreign Key) saxlayan mərkəzi cədvəl.




- 🛠️ İstifadə Olunan Alətlər
PostgreSQL (Verilənlər bazası)
DBeaver (SQL Client)


## 📊 Analitik Hesabat
Aşağıdakı SQL sorğusu vasitəsilə kateqoriya üzrə cəmi xərclər hesablanmışdır:

```sql
SELECT 
    stores.category, 
    SUM(transactions.amount) 
FROM transactions 
JOIN stores ON transactions.store_id = stores.id
GROUP BY stores.category;
