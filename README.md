# SqlPortfolio
USE `STORE`;

/* LIST ALL CUSTOMERS */
SELECT *
FROM customers;
    
/* LIST OF CUSTOMERS ORDERED BY FIRST NAME */    
SELECT *
FROM CUSTOMERS
ORDER BY FIRST_NAME;


SELECT 
    LAST_NAME, FIRST_NAME, POINTS, POINTS + 10
FROM
    CUSTOMERS;

SELECT 
    LAST_NAME, FIRST_NAME, POINTS, (POINTS + 10) * 100
FROM
    CUSTOMERS;

SELECT 
    last_name, first_name, points, (points * 10) + 100
FROM
    CUSTOMERS;

SELECT 
    last_name,
    first_Name,
    points,
    (points + 10) * 100 AS 'DISCOUNT_FACTOR'
FROM
    CUSTOMERS;


SELECT name,unit_price,(unit_price *1.1) AS new_price
FROM products;


SELECT *
FROM customers
WHERE birth_date > '1990-01-01';
    
/*LIST OF ALL ORDER ITEM */
SELECT *
FROM order_items;
    
/* TOTAL PRICE FOR ORDER ITEM */    
SELECT 
    order_id,
    product_id,
    quantity,
    unit_price,
    quantity * unit_price AS 'TOTAL PRICE'
FROM
    order_items;

SELECT *
FROM order_statuses;
    
    
/* TO IDENTIFY ORDER STATUS AS DELIVERED  */
SELECT order_status_id, name AS 'Status'
FROM order_statuses
WHERE name = 'Delivered';
    
 /* ALL ORDERES PLACED BY CUSTOMER ID 6 */   
SELECT *
FROM ORDERS
WHERE customer_id = 6;
    
/*LIST OF PRODUCTS LESS THAN OR EQUAL TO 10  */
SELECT *
FROM PRODUCTS
WHERE quantity_in_stock <= 10;
    
/*TOP 3 CUSTOMERS WITH HIGHEST POINTS  */
SELECT *
FROM customers
ORDER BY POINTS DESC
LIMIT 3;

/* LIST OF TOTAL ORDER AMOUNT BY ORDER  */
SELECT order_id, SUM(QUANTITY * unit_price) AS TOTAL_AMOUNT
FROM order_items
GROUP BY order_id;

/*LIST OF CUSTOMERS FROM CHICAGO   */
SELECT *
FROM CUSTOMERS
WHERE CITY = 'Chicago';
    
/*COUNT OF ORDERS WITH STATUS  */
SELECT status, COUNT(order_id) AS NO_OF_ORDERS
FROM orders
GROUP BY status;

/*LIST OF CUSTOMERS FROM IL STATE  */
SELECT *
FROM CUSTOMERS
WHERE STATE = 'IL';

