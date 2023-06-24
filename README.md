<p align="center">
<img src="https://i.imgur.com/MAEapT6.png" alt="SQL logo"/>
</p>

<h1>Applying filters to SQL queries</h1>

I am responsible for ensuring the security of our organization's system. This involves investigating potential security issues and updating employee computers as needed. I utilize SQL with filters to perform security-related tasks efficiently.



<h2>Retrieve after-hours failed login attempts</h2>

I selected all tables and used ‘FROM’ to specify which table,’ WHERE’ to set my conditions to
see how many login attempts have happened after 18:00
SELECT *
FROM log_in_attempts
WHERE login_time > '18:00' AND success = FALSE;
As you can see there have been 19 failed login attempts.

<p>
<img src="https://i.imgur.com/b6layXH.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

<h2>Retrieve login attempts on specific dates</h2>

Suspicious events occurred on 2022-05-09. and the day before 2022-05-08.
I used the OR operator and specified the dates
SELECT *
FROM log_in_attempts
WHERE login_date = '2022-05-09' OR login_date = '2022-05-08';
There are 75 login attempts in these 2 days.

<p>
<img src="https://i.imgur.com/FZrVFu2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

<p>
<img src="https://i.imgur.com/AX8ScJZ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

<h2>Retrieve login attempts outside of Mexico</h2>

Now I want to retrieve attempts outside of Mexico
I used NOT and LIKE operators
SELECT *
FROM log_in_attempts
WHERE NOT country LIKE 'MEX%';
There are 144 login attempts made outside of Mexico.

<p>
<img src="https://i.imgur.com/t7llq0k.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

<p>
<img src="https://i.imgur.com/LP8QzXO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

<h2>Retrieve employees in Marketing</h2>

The team is updating employee machines and needs to obtain information about employees in
the Marketing department who are located in all offices in the East building.
use the AND and LIKE operators
SELECT *
FROM employees
WHERE department = 'Marketing' AND office LIKE 'East%';
Now the team can see the devices that need an update

<p>
<img src="https://i.imgur.com/MYgrVr2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

<h2>Retrieve employees in Finance or Sales</h2>

Also, the team needs to perform a different update to the computers of all employees in the
Finance or the Sales department.
I used the OR operator
SELECT *
FROM employees
WHERE department = 'Finance' OR department = 'Sales';
Now the team can see the devices that need an update

<p>
<img src="https://i.imgur.com/6EjWrSr.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

<h2>Retrieve all employees not in IT</h2>

team needs to make one more update. This update was already made to employee computers
in the IT department. The team needs information about employees who are not in IT
department.
For this i used the NOT operator
SELECT *
FROM employees
WHERE NOT department = 'Information Technology';
Now the team can see all the information they need for this update

<p>
<img src="https://i.imgur.com/m2UGy7g.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

<h2>Summary</h2>

Ensuring secure data retrieval from databases is crucial, and one must employ proper SQL
query execution techniques while utilizing operators like AND, OR, and NOT to apply precise
filtering, thereby enhancing overall security measures.





