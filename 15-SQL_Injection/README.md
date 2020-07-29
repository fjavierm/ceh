# SQL Injection

A SQL injection attack consists of insertion or "injection" of a SQL query via the input data from the client to the application. A successful SQL injection exploit can read sensitive data from the database, modify database data (Insert/Update/Delete), execute administration operations on the database (such as shutdown the DBMS), recover the content of a given file present on the DBMS file system and in some cases issue commands to the operating system. SQL injection attacks are a type of injection attack, in which SQL commands are injected into data-plane input in order to effect the execution of predefined SQL commands.

SQL injection is a very popular, powerful and dangerous attack. The seriousness of the attack can rank from very simple to very high, allowing attackers with good knowledge of the SQL language and DBMS capabilities to perform serious damage to organisations.

## Some Concepts

SQL injection can be a big threat to web applications. SQL injection impact can be measured by observing the following parameters that attackers are intended to overcome:

* Bypassing the authentication
* Revealing sensitive information
* Compromised data integrity
* Erasing the database
* Remote code execution

### SQL - How it works

Structured Query Language (SQL) is used to communicate with a database. It is the standard language for relational database management systems. SQL statements are used to perform tasks such as update, insert, delete or retrieve data from a database.

Some examples can be:

* **Select**: _select * from User where name = 'John';_ It will select all users from the table _User_ with the _name_ equal to _John_.

* **Insert**: _insert into User (id, name, surname, age) values (1, 'John', 'Doe', 25);_ It will add a new user to the table _User_ with the given values.

* **Update**: _update User set age = 30 where id = 1_ It will update the age of the user with _id_ equal to _1_ on the table _User_.

* **Delete**: _delete from User where name = 'John';_ It will delete from the table _User_ all the users called _John_.

### SQL Injection tools

* **SQLMap**: Automatic SQL Injection And Database Takeover Tool

* **BSQL Hacker**: BSQL Hacker is an automated SQL Injection Tool designed to exploit SQL injection vulnerabilities in virtually any database.

* **Marathon Tool**: Marathon Tool is a POC for using heavy queries to perform a Time-Based Blind SQL Injection attack.

* **SQL Power Injector**: SQL Power Injector is an application created in .Net 1.1 that helps the penetration tester to inject SQL commands on a web page.

* **Havij**: Havij is an automated SQL Injection tool that helps penetration testers to find and exploit SQL Injection vulnerabilities on a web page.

### Types of SQL Injection

SQL injection can be classified into three major categories:

* In-band SQLi
* Inferential SQLi
* Out-of-band SQLi

#### In-Band SQL Injection

This category include injection techniques using the same communication channel to launch the attack and gather information from the response. Include

* Error-based SQL injection
* Union-based SQL injection

##### Error-Based SQL Injection

It relies on error messages from the database server to reveal information about the structure of the database. It is a very effective way to enumerate an entire database. Despite error messages are very useful during development time, they should be disabled when the application goes live. Error-based SQL injection can be performed by the following techniques:

* System stored procedure
* End of line comment
* Illegal / Logically incorrect query
* Tautology

##### Union-based SQL injection

Imply the use of the command _UNION_ in SQL to combine the result of two or more different tables.

#### Inferential SQL Injection (Blind Injection)

In this type of injection, no data is transferred from a web application; i.e. the attacker is unable to see the result of an attack hence referred as Blind injection. the attacker can just observe the behaviour of the server. The two main types are:

* **Boolean-based SQLi**: Boolean-based SQL Injection is an inferential SQL Injection technique that relies on sending an SQL query to the database which forces the application to return a different result depending on whether the query returns a TRUE or FALSE result.

* **Time-based SQLi**:  Time-based SQL Injection is an inferential SQL Injection technique that relies on sending an SQL query to the database which forces the database to wait for a specified amount of time (in seconds) before responding.

#### Out-of-band SQL Injection

It requires different channels to launch the attack and receive the response. For example, some features as DSN or HTTP request on database server hence it is not very common.

### SQL Injection Methodology

#### Information Gathering and vulnerability detection

An important step is to examine the target web application. Information can be gathered from input fields, hidden fields, get and post requests, cookies, string values, errors messages and more. All this information will provide some initial points of injection and, even, database structure or some existing vulnerabilities.

#### Launching the Attack

Once all the information has been collected, making use of it, attackers will proceed to execute one or more than one of the attack types seen it above trying to gather more information, extracting some data or bypass the authentication.

#### Advanced SQL Injection

Here, attackers will try to enumerate the database obtaining users, privilege levels assigned to them, account information about the administrator and as much information as possible about the structure. It also includes passwords and hashes grabbing and, transferring the database to a remote machine.

### Evasion Techniques

One tool that can be used by security professional to try to prevent SQL injection is the installation of an IDS. By installing and IDS attacker not only need to attack the database, they need to by pass the IDS too. IDSs use a signature-based detection mechanism to match input strings against the existing signatures to detect intrusions.

Despite of the extra security offered by adding an IDS, there are som evasion techniques that can be used to evade signature-based detection:

* Inserting inline comment in between keywords
* Character encoding
* String concatenation
* Obfuscated codes
* White spaces manipulation
* Hex encoding
* Sophisticated matches

### Countermeasures

In order to prevent SQL injection, developers can utilise parameterized database queries with bound, typed parameters and careful use of parameterized stored procedures in the database.

Additionally, developers, system administrators, and database administrators can take further steps to minimize attacks or the impact of successful attacks:

* Keep all web application software components including libraries, plug-ins, frameworks, web server software, and database server software up to date with the latest security patches available from vendors.

* Utilise the principle of least privilege when provisioning accounts used to connect to the SQL database.  For example, if a web site only needs to retrieve web content from a database using SELECT statements, do not give the web site's database connection credentials other privileges such as INSERT, UPDATE, or DELETE privileges. In many cases, these privileges can be managed using appropriate database roles for accounts.  Never allow your web application to connect to the database with Administrator privileges.

* Do not use shared database accounts between different web sites or applications.

* Validate user-supplied input for expected data types, including input fields like drop-down menus or radio buttons, not just fields that allow users to type in the input.

* Configure proper error reporting and handling on the web server and in the code so that database error messages are never sent to the client web browser. Attackers can leverage technical details in verbose error messages to adjust their queries for successful exploitation.
