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


## INSERTING INTO TABLE

1. Inserting into job table

> INSERT INTO job(job_name)
> VALUES
> ('Astronaut');

> INSERT INTO job(job_name)
> VALUES
> ('President');

2. Inserting into account table

> INSERT INTO account(username,password, email, created_on)
VALUES
('Jose', 'password', 'Jose@gmail.com', CURRENT_TIMESTAMP);

3. inserting into the account_job (intermediary table or the table containing foreign keys of account and job tables)

> INSERT INTO account_job(user_id, job_id, hire_date)
> VALUES
> (10,10, CURRENT_TIMESTAMP)

## UPDATING TABLE

1.

> UPDATE account
> SET last_login = CURRENT_TIMESTAMP
> RETURNING created_on, last_login

2.

> UPDATE account
> SET last_login = created_on
> RETURNING *

3. UPDATE JOIN 

> SELECT * FROM account_job
> SET hire_date = account.created_on
> FROM account
> WHERE account_job.user_id = account.user_id

## DELETE rows

1. first adding a value to the job table and then removing it 

>INSERT INTO job(job_name)
VALUES
('Cowboy')

>DELETE FROM job
WHERE job_name = 'Cowboy'
RETURNING *

### Alter clause
##### Usued for adding, dropping, renaming columns, changing columns data type, set default values for a column, Add CHECK constraints, Rename Table.

1. Renaming a table (changing the name of information table to new_info)

> ALTER TABLE information
RENAME TO new_info

2. Rename column name of a table

> ALTER TABLE new_info
RENAME COLUMN person TO people

3. Dropping a constraint on some column

> ALTER TABLE new_info
ALTER COLUMN people DROP NOT NULL

4. Dropping columns

> ALTER TABLE new_info
DROP COLUMN people

or

> ALTER TABLE new_info
DROP COLUMN IF EXISTS people
