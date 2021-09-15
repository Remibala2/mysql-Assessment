# mysql-Assessment
Apply SQL techniques for querying, aggregating and joining data. Solve the given challenges using SQL.

select * from users;
select * from progress;

2. 1>> Top 25 Schools
	
	select * from users where email_domain like "%.edu"
	group by 1
	limit 25;
	
	2>> Count of learners located in New York
	
	select count(user_id) from users where email_domain like "%.edu" and city = "New York";
	
	3>> Count of mobile users
	
	select count(user_id) from users where mobile_app = "mobile-user";
		

3. 1>> Sign up count for each hour
	select strftime('%H', sign_up_at), count(*)
from users
group by 1;

4. 1>> Do different schools (.edu domains) prefer different courses?

select users.email_domain, progress.learn_cpp, progress.learn_sql, progress.learn_html, progress.learn_javascript, progress.learn_java 
from users join progress 
where users.user_id = progress.user_id
group by users.email_domain;

	2>> What courses are the New Yorkers students taking?

select users.city, users.email_domain, progress.learn_cpp, progress.learn_sql, progress.learn_html, progress.learn_javascript, progress.learn_java 
from users join progress 
where users.user_id = progress.user_id and users.city = "New York"
group by users.email_domain;

	3>> What courses are the Chicago students taking?
	select users.city, users.email_domain, progress.learn_cpp, progress.learn_sql, progress.learn_html, progress.learn_javascript, progress.learn_java 
from users join progress 
where users.user_id = progress.user_id and users.city = "Chicago"
group by users.email_domain;


What did you like about this project? - Hands on mysql
What did you struggle with in this project? - Joins concept
What would make your experience with this assessment better? - Self study more and practice more queries
