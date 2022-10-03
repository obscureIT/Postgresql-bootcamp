1. Find out all the customers email address who lives in california.

> SELECT email, district
> 
> FROM customer INNER JOIN address
> 
> ON customer.address_id = address.address_id
> 
> WHERE address.district = 'California'

2. Find out all the movies where "Nick Wahlberg" has acted in

>SELECT actor.first_name, actor.last_name, title FROM film
>
>INNER JOIN film_actor ON
>
>film.film_id = film_actor.film_id
>INNER JOIN actor ON
>
>film_actor.actor_id = actor.actor_id
>
>WHERE first_name = 'Nick' AND Last_name = 'Wahlberg'

3. 

