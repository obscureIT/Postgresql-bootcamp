Creating a databse is quite simple, right click on the database directory, click on create, giv hte name of the database and VIOLA!

3. Create a table which references both the job table and the account table. This table will be an intermediary table which connects their job to their account. 

>CREATE TABLE account_job(
	user_id INTEGER REFERENCES account(user_id),
	job_id INTEGER REFERENCES job(job_id),
	hire_date TIMESTAMP 	
);
