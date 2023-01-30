# res03-MySql-j1

ex 1
SELECT * FROM users

ex 2
SELECT last_name FROM users

ex 3
SELECT * FROM users ORDER BY registration_date DESC LIMIT 1

ex 4
SELECT * FROM users WHERE birthdate LIKE "%-01-%"

ex 5
SELECT COUNT(*) FROM users

ex 6
SELECT users.* , addresses.city
FROM users JOIN addresses
ON users.address_id = addresses.id

ex 7
SELECT users.* , addresses.number 
FROM users JOIN addresses
ON users.address_id = addresses.id 
WHERE addresses.number IS NULL 

ex 8
SELECT price 
FROM products
WHERE price > 1000

ex 9
SELECT products.* , pictures.*
FROM products JOIN pictures
ON products.id = pictures.product_id

ex 10
SELECT products.* , categories.title
FROM products 
JOIN products_categories
ON products.id=products_categories.product_id
JOIN categories
ON products_categories.category_id=categories.id
WHERE categories.title="Voyage"

ex 11
SELECT users.*
FROM users
JOIN orders 
ON orders.user_id = users.id
GROUP BY users.id
HAVING COUNT(orders.id) > 10


ex 12

SELECT products.*
FROM products
JOIN products_orders
ON products_orders.product_id = products.id
JOIN orders
ON orders.id = products_orders.order_id
JOIN users
ON users.id = orders.user_id
WHERE users.registration_date 