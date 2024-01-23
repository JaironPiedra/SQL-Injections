# SQL-Injections

<h2>Description</h2>
A SQL injection attack involves the insertion or injection of a SQL query through input data from the client to the application. If successfully exploited, this type of attack can compromise the security of a database, allowing unauthorized access to sensitive data, manipulation of database records, and even execution of administrative operations on the database management system (DBMS), such as shutting it down. SQL injection attacks fall under the category of injection attacks, where SQL commands are inserted into input data, aiming to manipulate the execution of predefined SQL commands.

<br />

<h2>Languages and Utilities Used</h2>

<b>SQL INJECTIONS<b>

<h2>Environments Used </h2>

<b>DVWA<b>

<h2>SQL Injection Walkthrough:</h2>

<p align="center">
SQL injection Source 

  You can breakdown this source code to get a visual of why the database vulnerability exists in the "User ID" input box. The help section states that the 'id' variable is vulnerable to SQL injection.
After the user submits their input, a GET request is sent to collect form data. This shows the GET request takes in the 'id' parameter but this parameter is not validated which allows hackers to inject code into the SQL statement. The next line below shows how the SQL query is constructed when user input is sent to the database.

<p align="center">
 <br/>
<img src="https://i.imgur.com/eqHfx9I.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<p align="center">
Now let's interact with the web application, as shown in the screenshot below. The web application then returns First Name: and Surname: for the corresponding ID which tells us the query was sent to the database and executed using the following statement:

<p align="center">
 <br/>
  SELECT first_name, last_name FROM users WHERE user id = ‘1’;

<p align="center">
 <br/>
<img src="https://i.imgur.com/d8Zi8Zu.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<p align="center">
Blind SQL Injection

  When exploiting a normal SQL injection you will find that sometimes the database will display a visual output or even return an error that might tell us our SQL syntax is incorrect. Blind SQL injection is when we cannot visually see a response from the query sent to the database or we get a generic error page. These two types of SQL injections are virtually the same, the distinction between the two is in the database retrieval method. 
 
  Blind SQL injection is a type of SQL injection using boolean logic where the query is sent using True or False questions and the answer will be based on the response from the web application.
Boolean is an algebraic logic system type with only one of two possible values of logic: "True" or "False"
•	1=1 (TRUE)
•	1=0 (FALSE)
The following boolean expression is always (TRUE). When we send the query to the database the database answers back with TRUE and returns all results.

<p align="center">
 <br/>
<img src="https://i.imgur.com/1Gwo2u8.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<p align="center">

The following boolean expression is (FALSE). When we send the query to the database it answers back with FALSE and does not return any results.

<p align="center">
 <br/>
<img src="https://i.imgur.com/oQAUtwR.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<p align="center">

As a reminder, it's crucial for individuals and developers to be vigilant about SQL injection attacks.  To safeguard against SQL injection, always use secure coding practices, employ parameterized queries or prepared statements, and validate user input to prevent the execution of harmful SQL commands. Stay vigilant and prioritize security measures to protect databases from potential vulnerabilities.






