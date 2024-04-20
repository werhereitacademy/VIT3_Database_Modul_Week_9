### 1) İlk isminde Nick, Ed ve Jennifer adları bulunan aktörlerin adını ve soyadını gösterin.

```sql
SELECT first_name, last_name 
FROM  public.actor
WHERE first_name IN ('Nick', 'Ed', 'Jennifer');
```

### 2) İlk isminde adları Ed, Nick ve Jennifer olan aktörün sadece soyadını gösterin.

```sql
SELECT last_name

FROM public.actor

WHERE first_name IN ('Nick', 'Ed', 'Jennifer');
```
 ### 3) Adres tablosunun bütün ayrıntılarını gösterin.

```sql
 SELECT * FROM public.address
```

### 4) Adres tablosunda ilçe ve telefonu (district & phone) azalan sırada gösterin.

```sql
SELECT district, phone 
FROM public.address
ORDER BY district DESC, phone DESC;
```

### 5) Film ve envanter tablosundaki film_id’yi kullanarak, Film tablosundan film_id’yi, title’ i ve Envanter tablosundan envanter_id'sini gösterin. 

```sql
SELECT film.film_id, film.title, inventory.inventory_id
FROM public.film
JOIN inventory ON film.film_id = inventory.film_id;
```

### 6) Envanter tablosu ve rental tablosundan oluşan ilk 5 satırı gösterin. 

```sql
--SELECT * FROM public.inventory 

--UNION ALL
--SELECT * FROM public.rental
--LIMIT 5;

SELECT * 
FROM inventory 
JOIN rental ON inventory.inventory_id = rental.inventory_id
LIMIT 5;
```

### 7) Rental ve Payment tablolarından oluşan amount a göre azalan olarak sıralanmış rental_id, rental_date, payment_id ‘den oluşan ilk 10 satırı gösterin

```sql
SELECT rental.rental_id, rental.rental_date, payment.payment_id
FROM public.rental
JOIN payment ON rental.rental_id = payment.rental_id
ORDER BY payment.amount DESC
LIMIT 10;
```

### 8) Actor tablosunda actor_id 'nin boş olduğu satırların diğer detaylarını gösteriniz.

```sql
SELECT * FROM actor WHERE actor_id IS NULL
```


### 9) Actor tablosunda actor_id 'nin boş olmadığı satırların diğer detaylarını gösteriniz.

```sql
SELECT * FROM Actor WHERE actor_id IS NOT NULL
```


### 10) Film tablosunda boş olmayan satırların sayısını bulunuz.

 ```sql
 SELECT COUNT(*) FROM public.film WHERE description IS NOT NULL;
 ```

### 11) Payment tablosundan amount’un toplamını çıktı başlığı sum_amt olarak gösteriniz.

```sql
SELECT SUM(amount) AS toplam_miktar FROM Payment;
```

### 12) Payment tablosundan maximum ve minimum amount ‘u gösteriniz.

```sql
SELECT MAX(amount) AS maximum_amount, MIN(amount) AS minimum_amount FROM payment
```

