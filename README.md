<br>

<br>

 ![Image](https://r.resimlink.com/QvqbJzUg.png)
 
<br>

 # SQL Eğitim Patika 
 
#### Bu repo'da [Patika](https://academy.patika.dev/) SQL eğitiminde yapmış olduğunuz bütün ödevler bulunmaktadır.

<br>

## SQL Ödev 01 -- Where ve Karşılaştırma & Mantıksal Operatörler

<br>

<hr>

<br>

1- <Strong>Film</Strong> tablosunda bulunan <Strong>title</Strong> ve <Strong>description</Strong> sütunlarındaki verileri sıralayınız.

```
SELECT title, description FROM film;

```
<br>

<hr>

<br>

2- <Strong>film</Strong> tablosunda bulunan tüm sütunlardaki verileri film uzunluğu <Strong>length</Strong> 60 dan büyük ve 75 ten küçük olma koşullarını sıralayınız.
```
SELECT * FROM film
WHERE length > 60 AND length < 75;

```
<br>

<hr>

<br>

3- <strong>film</strong> tablosunda bulunan tüm sütunlardaki verileri  <strong>rental_rate</strong> 0.99  <strong>VE</strong>  <strong>replacement_cost</strong> 12.99  <strong>VEYA</strong> 28.99 olma koşullarıyla sıralayınız.

```
SELECT * FROM film
WHERE rental_rate = 0.99 AND replacement_cost = 12.99 
OR replacement_cost = 28.99;

```
<br>

<hr>

<br>

4- <strong>customer</strong> tablosunda bulunan <strong>first_name</strong> sütunundaki değeri 'Mary' olan müşterinin <strong>last_name</strong> sütunundaki değeri nedir?

```
SELECT last_name FROM customer
WHERE first_name = 'Mary';

```

<br>

<hr>

<br>

5-<strong>film</strong>  tablosundaki <strong>uzunluğu(length)</strong>  50 ten büyük OLMAYIP aynı zamanda <strong>rental_rate</strong>  değeri 2.99 <strong>veya</strong>  4.99 OLMAYAN verileri sıralayınız.

```
SELECT * FROM film
WHERE length <= 50 
AND NOT (rental_rate = 2.99 OR rental_rate = 4.99);

```

<br>

## SQL Ödev 02 | BETWEEN ve IN

<br>

<hr>

<br>

1- <strong>film</strong> tablosunda bulunan tüm sütunlardaki verileri <strong>replacement cost</strong> değeri 12.99 dan büyük eşit ve 16.99 küçük olma koşuluyla sıralayınız ( BETWEEN - AND yapısını kullanınız.)

```
SELECT * FROM film 
WHERE replacement_cost BETWEEN 12.99 AND 16.99;

```

<br>

<hr>

<br>

2- <strong>actor</strong> tablosunda bulunan <strong>first_name</strong> ve <strong>last_name</strong> sütunlardaki verileri <strong>first_name</strong> 'Penelope' veya 'Nick' veya 'Ed' değerleri olması koşuluyla sıralayınız. ( IN operatörünü kullanınız.)

```
SELECT first_name, last_name FROM actor 
WHERE first_name IN ('Penelope', 'Nick', 'Ed');

```

<br>

<hr>

<br>

3- <strong>film</strong> tablosunda bulunan tüm sütunlardaki verileri <strong>rental_rate</strong> 0.99, 2.99, 4.99 VE <strong>replacement_cost</strong> 12.99, 15.99, 28.99 olma koşullarıyla sıralayınız. ( IN operatörünü kullanınız.)

```
SELECT * FROM film 
where rental_rate IN(0.99,2.99,4.99) and replacement_cost IN(12.99,15.99,28.99);

```

<br>

## SQL Ödev 03 | LIKE ve ILIKE

<br>

<hr>

<br>

1- <strong>country</strong> tablosunda bulunan  <strong>country</strong> sütunundaki ülke isimlerinden 'A' karakteri ile başlayıp 'a' karakteri ile sonlananları sıralayınız.

```
SELECT country FROM country
WHERE country ~~ 'A%a' 

```

<br>

<hr>

<br>

2- <strong>country</strong> tablosunda bulunan <strong>country</strong> sütunundaki ülke isimlerinden en az 6 karakterden oluşan ve sonu 'n' karakteri ile sonlananları sıralayınız.

```
SELECT country FROM country 
WHERE country LIKE '_____%n' 

```

<br>

<hr>

<br>

3- <strong>film</strong> tablosunda bulunan <strong>title</strong> sütunundaki film isimlerinden en az 4 adet büyük ya da küçük harf farketmesizin <strong>'T'</strong> karakteri içeren film isimlerini sıralayınız.

```
SELECT title FROM film 
WHERE title ~~* '%T%T%T%T%' 

```

<br>

<hr>

<br>

4- <strong>film</strong> tablosunda bulunan tüm sütunlardaki verilerden <strong>title</strong> 'C' karakteri ile başlayan ve uzunluğu (length) 90 dan büyük olan ve <strong>rental_rate</strong> 2.99 olan verileri sıralayınız.

```
SELECT * FROM film 
WHERE title LIKE 'C%' AND length > 90 AND rental_rate = 2.99; 

```











