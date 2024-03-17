#1A. Overall perofrmance DQLab Store dari tahun 2009 - 2012 untuk jumlah order dan total sales order finished
SELECT 
YEAR(order_date) AS years, 
SUM(sales) AS sales, 
COUNT(order_quantity) AS number_of_order 
FROM dqlab_sales_store
WHERE order_status = 'Order Finished'
GROUP BY YEAR(order_date)
order by year(order_date);

#1B. Overall performance DQLab by subcategory product yang akan dibandingkan antara tahun 2011 dan tahun 2012
SELECT
YEAR(order_date) AS years,
product_sub_category,
SUM(sales) AS sales
FROM dqlab_sales_store
WHERE order_status = 'Order Finished'
AND YEAR(order_date) BETWEEN 2011 AND 2012
GROUP BY years, product_sub_category
ORDER BY years, sales DESC;

#2A. Efektifitas dan efisiensi promosi yang dilakukan selama ini, dengan menghitung burn rate dari promosi yang dilakukan overall berdasarkan tahun
SELECT
YEAR(order_date) AS years,
SUM(sales) AS sales,
SUM(discount_value) AS promotion_value,
ROUND((SUM(discount_value)/SUM(sales))*100,2) AS burn_rate_percentage
FROM dqlab_sales_store
WHERE order_status = 'Order Finished'
GROUP BY years
ORDER BY years;

#2B. Efektifitas dan efisiensi promosi yang dilakukan selama ini, dengan menghitung burn rate dari promosi yang dilakukan overall berdasarkan sub-category
SELECT
YEAR(order_date) AS years,
product_sub_category,
product_category,
SUM(sales) AS sales,
SUM(discount_value) AS promotion_value,
ROUND((SUM(discount_value)/SUM(sales))*100,2) AS burn_rate_percentage
FROM dqlab_sales_store
WHERE order_status = 'Order Finished'
AND YEAR(order_date) = 2012
GROUP BY 
years,
product_sub_category,
product_category
ORDER BY sales DESC;

#3A. Analisa terhadap customer setiap tahunnya
SELECT
YEAR(order_date) AS years,
COUNT(DISTINCT customer) AS number_of_customer
FROM dqlab_sales_store
WHERE order_status = 'Order Finished ' AND YEAR(order_date) BETWEEN 2009 AND 2012
GROUP BY years
ORDER BY years ASC;
