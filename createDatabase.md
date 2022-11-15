Creating a databse is quite simple, right click on the database directory, click on create, giv hte name of the database and VIOLA!

1. Create the account table -

> CREATE TABLE account(
>	  user_id SERIAL PRIMARY KEY,
>	  username VARCHAR (50) UNIQUE NOT NULL,
>	  password VARCHAR(50) NOT NULL,
>	  email VARCHAR(250) UNIQUE NOT NULL,
>	  created_on TIMESTAMP NOT NULL,
>	  last_login TIMESTAMP
> );

2. Create the job table - 

> CREATE TABLE job(
>	  job_id SERIAL PRIMARY KEY,
>	  job_name VARCHAR(200) UNIQUE NOT NULL
> );



3. Create a table which references both the job table and the account table. This table will be an intermediary table which connects their job to their account. 

>CREATE TABLE account_job(
>	user_id INTEGER REFERENCES account(user_id),
>	job_id INTEGER REFERENCES job(job_id),
>	hire_date TIMESTAMP 	
>);
