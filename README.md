# Fazilabi-Patika_PostgreSQL_odev12

## [academy.Patika.dev](https://academy.patika.dev/)

## Aşağıdaki sorgu senaryolarını dvdrental örnek veri tabanı üzerinden gerçekleştiriniz.
### 1. film tablosunda film uzunluğu length sütununda gösterilmektedir. Uzunluğu ortalama film uzunluğundan fazla kaç tane film vardır?
`SELECT COUNT(*) FROM film `<br>
`WHERE length > ANY`<br>
`(`<br>
`    SELECT AVG(length) FROM film`<br>
`);`

### 2. film tablosunda en yüksek rental_rate değerine sahip kaç tane film vardır?
`SELECT COUNT(rental_rate) FROM film `<br>
`WHERE rental_rate =`<br>
`(`<br>
`	SELECT MAX(rental_rate) FROM film`<br>
`);`


### 3. film tablosunda en düşük rental_rate ve en düşün replacement_cost değerlerine sahip filmleri sıralayınız.



### 4. payment tablosunda en fazla sayıda alışveriş yapan müşterileri(customer) sıralayınız. 
`SELECT customer.first_name, customer.last_name, payment.customer_id, COUNT(payment.customer_id) FROM payment INNER JOIN customer`<br>
`ON customer.customer_id = payment.customer_id`<br>
`GROUP BY customer.first_name, customer.last_name, payment.customer_id`<br>
`ORDER BY COUNT(payment.customer_id) DESC;`
