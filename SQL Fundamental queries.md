> #### SELECT is the most common statement used, and it allows us to retrieve information from a table.
> #### The "*" (asterik mark means "all") is used to retrieve all the columns from the table after the FROM keyword

### SELECT * FROM film;
or
### SELECT * FROM actor;

> #### We want to reward our first 10 paying customers
> #### What are the customer ids of the first 10 customers who created a payment?

### SELECT customer_id FROM payment
### ORDER BY payment_date ASC
### LIMIT 10;

> #### A customer wants to quickly rent a video to watch over their short luch break.
> #### What are the titles for the 5 shortest (in length of runtime) movies?

### SELECT title, length FROM film 
### ORDER BY length ASC
### LIMIT 5;

> #### If a customer has option to watch any movies which is 50 minutes or less how many optiuons does he/she have?

### SELECT COUNT(*) FROM film
### WHERE length <= 50;

> Show all from payment table where payment_date starts from 2007-02-01 0:00 mark to 2007-02-15 0:00 mark

### SELECT * FROM payment
### WHERE payment_date BETWEEN '2007-02-01' AND '2007-02-15';

> IN statement usage
> Show all rows from customers where John, Jake and Julie does not belong to the first_name column 

### SELECT * FROM customer
### WHERE first_name NOT IN('John','Jake','Julie')
