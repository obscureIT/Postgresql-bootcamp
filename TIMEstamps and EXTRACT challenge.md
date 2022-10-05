# INTRO

1. EXTRACT keyword to extract parts of the Timestamp - Year, months , quarters etc
> SELECT EXTRACT(YEAR FROM payment_date) FROM payment;

2. Extracting the max value of a year
> SELECT MAX(EXTRACT(YEAR FROM payment_date)) FROM payment;

3. Extracting and naming the column with something for relevant
> SELECT (EXTRACT(MONTH FROM payment_date)) AS pay_month FROM payment;

4. Returning the time value that has passed since the data entry in the table and today in year month date hour and seconds
> SELECT AGE(payment_date) FROM payment;

5. Some examples of the TO_CHAR function
> SELECT TO_CHAR(payment_date,'MONTH-YYYY') FROM payment;

> SELECT TO_CHAR(payment_date,'MON-YYYY') FROM payment;

> SELECT TO_CHAR(payment_date,'mon YYYY') FROM payment;

> SELECT TO_CHAR(payment_date,'dd-MM-YYYY') FROM payment;

> SELECT TO_CHAR(payment_date,'MM-dd-YYYY') FROM payment;

### FOR MORE INFORMATION ON DATE TIME FORMATTING - https://www.postgresql.org/docs/current/functions-formatting.html

# TIMESTAMPS AND EXTRACT CHALLENGE

1. Show all the full name of the months when payment occured 

> SELECT DISTINCT(TO_CHAR(payment_date,'MONTH')) AS pay_month FROM payment;

2. How many payments occurred on a monday in the payment table?

> SELECT COUNT(*) FROM payment WHERE EXTRACT(dow FROM payment_date) = 1
