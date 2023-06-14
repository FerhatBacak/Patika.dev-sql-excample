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
WHERE rental_rate = 0.99 AND (replacement_cost = 12.99 
OR replacement_cost = 28.99);

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

## SQL Ödev 02 -- BETWEEN ve IN

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
WHERE rental_rate IN(0.99,2.99,4.99) AND replacement_cost IN(12.99,15.99,28.99);

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

<br>

## SQL Ödev 04 -- COUNT ve DISTINCT

<br>

<hr>

<br>

1- <strong>film</strong> tablosunda bulunan  <strong>replacement_cost</strong> sütununda bulunan birbirinden farklı değerleri sıralayınız.

```

SELECT DISTINCT replacement_cost FROM film

```

<br>

<hr>

<br>

2- <strong>film</strong> tablosunda bulunan <Strong>replacement_cost</strong> sütununda birbirinden farklı kaç tane veri vardır?

```

SELECT COUNT (DISTINCT replacement_cost) FROM film

```

<br>

<hr>

<br>

3- <strong>film</strong> tablosunda bulunan film isimlerinde  <strong>(title)</strong> kaç tanesini T karakteri ile başlar ve aynı zamanda  <strong>rating</strong> 'G' ye eşittir?

```

SELECT COUNT(*) FROM film 
WHERE title LIKE 'T%' AND rating = 'G';

```

<br>

<hr>

<br>

4- <strong>country</strong> tablosunda bulunan ülke isimlerinden (country) kaç tanesi <strong>5</strong> karakterden oluşmaktadır?

```

SELECT COUNT(DISTINCT country) FROM country 
WHERE country like '_____';

```

<br>

<hr>

<br>

5- <strong>city</strong> tablosundaki şehir isimlerinin kaç tanesi <strong>'R'</strong> veya <strong>r</strong> karakteri ile biter ?  

```

SELECT COUNT(*) FROM city WHERE city ~~*'%R';

```

<br>

## SQL Ödev 05 -- OFFSET ve LIMIT

<br>

<hr>

<br>

1- <strong>film</strong> tablosunda bulunan ve film ismi <strong>title</strong> 'n' karakteri ile biten en uzun length 5 filmi sıralayınız.

```

SELECT title FROM film
WHERE title LIKE '%n'
ORDER BY length desc
LIMIT 5;

```

<br>

<hr>

<br>

2- <strong>film</strong> tablosunda bulunan ve film ismi <strong>title</strong> 'n' karakteri ile biten en kısa <strong>length</strong> ikinci(6,7,8,9,10) 5 filmi (6,7,8,9,10) sıralayınız

```

SELECT title FROM film
WHERE title LIKE '%n'
ORDER BY length 
OFFSET 5
LIMIT 5;

```

<br>

<hr>

<br>

3- <strong>customer</strong> tablosunda bulunan <strong>last_name</strong> sütununda göre azalan yapılan sıralamada <strong>store_id</strong> 1 olmak koşuluyla ilk 4 veriyi sıralayınız

```

SELECT * FROM customer 
WHERE store_id=1
ORDER BY last_name
LIMIT 4;

```

<br>

<hr>

<br>

## SQL Ödev 06 -- Aggregate Fonksiyonları

<br>

<hr>

<br>

1- <Strong>Film</Strong> tablosunda bulunan <Strong>rental_rate</Strong> sütunundaki değerlerin ortalaması nedir ?

```
SELECT AVG(rental_rate) FROM film; 

```
<br>

<hr>

<br>

2- <Strong>film</Strong> tablosunda bulunan filmlerden kaç tanesi 'C' karakteri ile başlar ?

```

SELECT COUNT(*) FROM film WHERE title LIKE 'C%';

```

<br>

<hr>

<br>

3- <strong>film</strong> tablosunda bulunan filmlerden <strong>rental_rate</strong> değeri 0.99 a eşit olan en uzun <strong> length</strong> filmi kaç dakikadır ?

```

SELECT MAX(length) FROM film WHERE rental_rate=0.99;

```

<br>

<hr>

<br>

4- <strong>customer</strong> tablosunda bulunan filmlerin uzunluğu 150 dakikadan büyük olanlarına ait kaç farklı
<strong>replacement_cost</strong> değeri vardır ?

```

SELECT COUNT(DISTINCT(replacement_cost)) FROM film 
WHERE length>150

```

<br>

## SQL Ödev 07 -- Group By and Having

<br>

<hr>

<br>

1- <strong>film</strong> tablosunda bulunan filmleri <strong>rating</strong> değerine göre gruplayınız.

```
SELECT rating FROM film GROUP BY rating;

```

<br>

<hr>

<br>

2- <strong>film</strong> tablosunda bulunan filmleri <strong>replacement_cost</strong> sütununa göre grupladığımızda film sayısı
50 den fazla olan <strong>replacement_cost</strong> değerini ve karşılık gelen film sayısını sıralayınız.

```
SELECT replacement_cost,COUNT(*) FROM film 
GROUP BY replacement_cost
HAVING COUNT(*)>50;

```

<br>

<hr>

<br>

3- <strong>customer</strong> tablosunda bulunan <strong>store_id</strong> değerine karşılık gelen müşteri sayıları nelerdir ?

```
SELECT store_id,COUNT(*) FROM customer
GROUP BY store_id;

```

<br>

<hr>

<br>

4- <strong>city</strong> tablosunda bulunan şehir verilerini <strong>country_id</strong> sütununa göre gruplandırdıktan sonra en fazla şehir sayısı barındıran <strong>country_id</strong> bilgisini ve şehir sayısını paylaşınız.

```
SELECT country_id,COUNT(*) FROM city
GROUP BY country_id
ORDER BY COUNT(*) DESC
LIMIT 1;

```

<br>

<hr>

<br>

## SQL Ödev 08 -- Tablo Oluşturma Verileri Güncelleme

<br>

<hr>

<br>

1- <strong>test</strong> veritabanımızda <strong>employee</strong> isimli bilgileri <strong>id integer</strong> <strong>name varchar(50)</strong>
<strong>birhday DATE</strong> <strong>email varchar(100)</strong> olan bir tablo uluşturalım

```
CREATE TABLE employee
(
	id INT,
	name VARCHAR(50),
	birthday DATE,
	email VARCHAR(50)
);

```

<br>

<hr>

<br>

2- Oluşturduğumuz <strong>employee</strong> tablosuna <strong>Mockaroo</strong> servisini kullanarak 50 adet veri ekleyelim

```
insert into employee (id, name, birthday, email) values (1, 'Celka', '2022/09/11', 'ccarroll0@w3.org');
insert into employee (id, name, birthday, email) values (2, 'Brook', '2023/03/13', 'btuson1@phoca.cz');
insert into employee (id, name, birthday, email) values (3, 'Spencer', '2023/01/14', 'sfrude2@buzzfeed.com');
insert into employee (id, name, birthday, email) values (4, 'Griffie', '2022/07/28', 'gjemmett3@biglobe.ne.jp');
insert into employee (id, name, birthday, email) values (5, 'Judy', '2023/02/21', 'jflorez4@foxnews.com');
insert into employee (id, name, birthday, email) values (6, 'Darleen', '2023/02/28', 'dwarrilow5@yolasite.com');
insert into employee (id, name, birthday, email) values (7, 'Stephana', '2023/02/17', 'sfasson6@ucoz.com');
insert into employee (id, name, birthday, email) values (8, 'Melania', '2022/12/16', 'mlouiset7@blogtalkradio.com');
insert into employee (id, name, birthday, email) values (9, 'Garey', '2023/06/03', 'gfiggs8@forbes.com');
insert into employee (id, name, birthday, email) values (10, 'Etheline', '2023/04/15', 'ehodgen9@auda.org.au');
insert into employee (id, name, birthday, email) values (11, 'Rosalia', '2023/02/07', 'rcotteya@cnbc.com');
insert into employee (id, name, birthday, email) values (12, 'Gherardo', '2022/10/01', 'gchessilb@google.ca');
insert into employee (id, name, birthday, email) values (13, 'Clarisse', '2023/02/20', 'cchilcottec@businessinsider.com');
insert into employee (id, name, birthday, email) values (14, 'Meaghan', '2023/05/29', 'mparnelld@yahoo.com');
insert into employee (id, name, birthday, email) values (15, 'Sarge', '2022/12/22', 'stinemane@tmall.com');
insert into employee (id, name, birthday, email) values (16, 'Colin', '2023/01/31', 'claisef@bandcamp.com');
insert into employee (id, name, birthday, email) values (17, 'Haily', '2022/12/22', 'hjandag@engadget.com');
insert into employee (id, name, birthday, email) values (18, 'Roseann', '2022/08/23', 'rmccreeryh@toplist.cz');
insert into employee (id, name, birthday, email) values (19, 'Catina', '2022/08/23', 'ctilstoni@goo.ne.jp');
insert into employee (id, name, birthday, email) values (20, 'Issi', '2022/10/11', 'isievewrightj@istockphoto.com');
insert into employee (id, name, birthday, email) values (21, 'Joelle', '2022/08/06', 'jlawrenzk@utexas.edu');
insert into employee (id, name, birthday, email) values (22, 'Gertrudis', '2022/12/11', 'gsandyfordl@pen.io');
insert into employee (id, name, birthday, email) values (23, 'Laureen', '2022/06/18', 'lfranssonm@uiuc.edu');
insert into employee (id, name, birthday, email) values (24, 'Dyna', '2022/12/31', 'dbenton@dagondesign.com');
insert into employee (id, name, birthday, email) values (25, 'Erskine', '2022/07/02', 'egunbyo@google.pl');
insert into employee (id, name, birthday, email) values (26, 'Shannon', '2023/05/10', 'srigebyp@shop-pro.jp');
insert into employee (id, name, birthday, email) values (27, 'Aurore', '2023/02/25', 'agillisonq@yahoo.com');
insert into employee (id, name, birthday, email) values (28, 'Kip', '2023/04/29', 'kstenniner@devhub.com');
insert into employee (id, name, birthday, email) values (29, 'Ali', '2023/05/09', 'apenkethmans@umich.edu');
insert into employee (id, name, birthday, email) values (30, 'Deidre', '2022/07/14', 'dmylchreestt@nbcnews.com');
insert into employee (id, name, birthday, email) values (31, 'Claudell', '2022/08/12', 'cstookesu@unblog.fr');
insert into employee (id, name, birthday, email) values (32, 'Giacomo', '2022/07/08', 'gwhitwoodv@blogspot.com');
insert into employee (id, name, birthday, email) values (33, 'Myer', '2023/02/16', 'mgettyw@aboutads.info');
insert into employee (id, name, birthday, email) values (34, 'Park', '2022/07/20', 'pdeyenhardtx@house.gov');
insert into employee (id, name, birthday, email) values (35, 'Anthia', '2023/05/13', 'agressy@tiny.cc');
insert into employee (id, name, birthday, email) values (36, 'Janetta', '2022/07/22', 'joxleez@comsenz.com');
insert into employee (id, name, birthday, email) values (37, 'Fiann', '2023/03/04', 'fglusby10@google.nl');
insert into employee (id, name, birthday, email) values (38, 'Hedi', '2022/10/29', 'hfranzen11@twitpic.com');
insert into employee (id, name, birthday, email) values (39, 'Lana', '2023/04/11', 'lchappel12@census.gov');
insert into employee (id, name, birthday, email) values (40, 'Catherine', '2022/08/02', 'cadds13@wordpress.com');
insert into employee (id, name, birthday, email) values (41, 'Irwinn', '2023/05/25', 'ihabershon14@homestead.com');
insert into employee (id, name, birthday, email) values (42, 'Idalina', '2022/09/29', 'ifortnam15@sina.com.cn');
insert into employee (id, name, birthday, email) values (43, 'Jeanie', '2022/08/13', 'jromanet16@dmoz.org');
insert into employee (id, name, birthday, email) values (44, 'Danyelle', '2022/11/20', 'dnesbit17@slate.com');
insert into employee (id, name, birthday, email) values (45, 'Don', '2023/02/17', 'deggle18@mysql.com');
insert into employee (id, name, birthday, email) values (46, 'Margie', '2022/08/10', 'mstigell19@barnesandnoble.com');
insert into employee (id, name, birthday, email) values (47, 'Ivor', '2023/01/25', 'igoymer1a@photobucket.com');
insert into employee (id, name, birthday, email) values (48, 'Kandy', '2022/09/18', 'kgirsch1b@netlog.com');
insert into employee (id, name, birthday, email) values (49, 'Brendin', '2023/06/07', 'bmuddle1c@archive.org');
insert into employee (id, name, birthday, email) values (50, 'Jasmina', '2022/08/06', 'jderington1d@is.gd');


```

<br>

<hr>

<br>

3- Sütunların her birine göre diğer sütunları güncelleyecek 5 adet UPDATE işlemi yapalım

```

// İsim (name) sütununu güncellemek:

UPDATE employee
SET name = 'John Doe'
WHERE name = 'Coob';


// Doğum günü (birthday) sütununu güncellemek:

UPDATE employee
SET birthday = '1990-06-15'
WHERE email = 'yserckd@home.pl';


// E-posta (email) sütununu güncellemek:

UPDATE employee
SET email = 'johndoe@example.com'
WHERE birthday = '1950/04/10';


// İsim ve doğum günü sütunlarını güncellemek:

UPDATE employee
SET name = 'Jane Smith',
    birthday = '1985-03-20'
WHERE id = 4;


// Tüm sütunları güncellemek:

UPDATE employee
SET name = 'Robert Johnson',
    birthday = '1978-12-10',
    email = 'robertjohnson@example.com'
WHERE id = 5;

```

<br>

<hr>

<br>

4- Sütunların her birine göre ilgili satırı silecek 5 adet DELETE işlemi yapalım

```

DELETE FROM employee
WHERE id = 44;

DELETE FROM employee
WHERE name ='Constantin';

DELETE FROM employee
WHERE name = 'Jane Smith' AND birthday = '1985-03-20';

DELETE FROM employee
WHERE email = 'umallinsonn@hp.com';

DELETE FROM employee
WHERE id >5
RETURNING *;

```

<br>

## SQL Ödev 09 -- INNER JOIN

1-) city tablosu ile country tablosunda bulunan şehir (city) ve ülke (country) isimlerini birlikte görebileceğimiz INNER JOIN sorgusunu yazınız.



```

SELECT ci.city, co.country
FROM city ci
INNER JOIN country co ON (ci.country_id = co.country_id);

```


<br>
<br>
<br>

2-) customer tablosu ile payment tablosunda bulunan payment_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz INNER JOIN sorgusunu yazınız.


```

SELECT p.payment_id, c.first_name, c.last_name
FROM customer c
INNER JOIN payment p ON (c.customer_id = p.customer_id);

```


<br>
<br>
<br>

3-) customer tablosu ile rental tablosunda bulunan rental_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz INNER JOIN sorgusunu yazınız.


```

SELECT r.rental_id, c.first_name, c.last_name
FROM customer c
INNER JOIN rental r ON (c.customer_id = r.customer_id);

```

<br>

## SQL Ödev 10 -- LEFT JOIN, RIGHT JOIN, FULL JOIN

1-) city tablosu ile country tablosunda bulunan şehir (city) ve ülke (country) isimlerini birlikte görebileceğimiz LEFT JOIN sorgusunu yazınız.



```

SELECT c.city, co.country
FROM city c
LEFT JOIN country co ON (c.country_id = co.country_id);

```


<br>
<br>
<br>

2-) customer tablosu ile payment tablosunda bulunan payment_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz RIGHT JOIN sorgusunu yazınız.



```

SELECT p.payment_id, c.first_name, c.last_name
FROM customer c
RIGHT JOIN payment p ON (c.customer_id = p.customer_id);

```


<br>
<br>
<br>

3-) customer tablosu ile rental tablosunda bulunan rental_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz FULL JOIN sorgusunu yazınız.



```

SELECT p.payment_id, c.first_name, c.last_name FROM payment p
FULL JOIN customer c ON (c.customer_id= p.customer_id);

```


<br>

## SQL Ödev 11 -- UNION, INTERSECT ve EXCEPT

1-) actor ve customer tablolarında bulunan first_name sütunları için tüm verileri sıralayalım.



```

(SELECT first_name 
FROM actor)
UNION 
(SELECT first_name
FROM customer);

```


<br>
<br>
<br>

2-) actor ve customer tablolarında bulunan first_name sütunları için kesişen verileri sıralayalım.



```

(SELECT first_name 
FROM actor)
INTERSECT
(SELECT first_name
FROM customer);

```


<br>
<br>
<br>

3-) actor ve customer tablolarında bulunan first_name sütunları için ilk tabloda bulunan ancak ikinci tabloda bulunmayan verileri sıralayalım.



```

(SELECT first_name 
FROM actor )
EXCEPT 
(SELECT first_name 
FROM customer);

```


<br>
<br>
<br>

4-) İlk 3 sorguyu tekrar eden veriler için de yapalım.



```

(SELECT first_name 
FROM actor)
UNION ALL
(SELECT first_name
FROM customer);


(SELECT first_name 
FROM actor)
INTERSECT ALL
(SELECT first_name
FROM customer);


(SELECT first_name 
FROM actor )
EXCEPT ALL
(SELECT first_name 
FROM customer);

```

<br>

## SQL Ödev 12 -- Sorgu Senaryoları

1-) film tablosunda film uzunluğu length sütununda gösterilmektedir. Uzunluğu ortalama film uzunluğundan fazla kaç tane film vardır?



```

SELECT COUNT(*)
FROM film
WHERE length > (
  SELECT AVG(length)
  FROM film
);

```


<br>
<br>
<br>

2-) film tablosunda en yüksek rental_rate değerine sahip kaç tane film vardır?


```

SELECT COUNT(*)
FROM film
WHERE rental_rate = (
  SELECT MAX(rental_rate)
  FROM film
);

```


<br>
<br>
<br>

3-) film tablosunda en düşük rental_rate ve en düşün replacement_cost değerlerine sahip filmleri sıralayınız.


```

SELECT * FROM film
WHERE rental_rate = (
  SELECT MIN(rental_rate)
  FROM film
)
AND replacement_cost = (
  SELECT MIN(replacement_cost)
  FROM film
);

```


<br>
<br>
<br>

4-) payment tablosunda en fazla sayıda alışveriş yapan müşterileri(customer) sıralayınız.


```

SELECT customer_id, COUNT(*) AS transaction_count
FROM payment
GROUP BY customer_id
ORDER BY transaction_count DESC;


```

### Paylaşılan içerikler PostgreSQL de yazılmıştır.






































