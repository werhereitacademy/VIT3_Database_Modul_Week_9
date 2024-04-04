### 2) İlk isminde adları Ed, Nick ve Jennifer olan aktörün sadece soyadını gösterin.


```sql
SELECT last_name

FROM public.actor

WHERE first_name IN ('Nick', 'Ed', 'Jennifer');
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

### 10) Film tablosunda boş olmayan satırların sayısını bulunuz.

 ```sql
 SELECT COUNT(*) FROM public.film WHERE description IS NOT NULL;
 ```

