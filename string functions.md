1. Concatinating and making new email addresses. first letter of first name with lower case of last name and the domain name

> SELECT LOWER(LEFT(first_name, 1)) || LOWER(last_name) || '@gmail.com' FROM customer

2. Concatinating first name and last name

> SELECT first_name || ' ' || last_name FROM customer

3. length of a string

>  SELECT length(first_name) FROM customer
