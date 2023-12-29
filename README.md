# Filter-a-SQL-Query

<h2>Activity overview</h2>

As a security analyst, knowing how to make better queries to retrieve specific pieces of data can help I find the security-related information I need more efficiently.

In this lab activity, I’ll apply basic filters to SQL queries to retrieve information from a MariaDB database.

MariaDB is a popular open-source relational database that is compatible with MySQL.

This activity provides me with a great opportunity to apply what I’ve learned and add filters to SQL queries.

Note: The terms row and record are used interchangeably in this lab activity.

<h2>Scenario</h2>

In this scenario, I need to get specific information about employees, their machines, and the departments they’re in. My team needs this data to perform various tasks, such as running updates, posting privacy notices in certain departments, and sending an alert to an employee with an issue on a machine.

I am responsible for finding the required information by querying a database. I’ll add filters to my queries to locate the information more quickly.

Here’s how I’ll do this task: First, I’ll list all organization machines and their operating systems. Second, I’ll list all machines with the operating system OS 2. Third, I’ll list all the employees in the Finance and Sales departments. Fourth, I’ll obtain information about machines.

<h2>Task 1. List all organization machines</h2>

In this task, I need to get a list of all organization machines and their operating systems. The data is contained in the ```machines``` table. I’ll need to use the ```SELECT``` keyword to return specific columns.

- Run a SQL query to retrieve only the ```device_id``` and ```operating_system``` columns from the ```machines``` table.

```SELECT device_id, operating_system, FROM machines;```

Here I can find that 200 rows were returned at the bottom of the output:

![image](https://github.com/n8som/Filter-a-SQL-Query/assets/110139109/51032f5b-f9fe-44c1-8ae7-4101373297be)

<h2>Task 2. Retrieve a list of the machines with OS 2</h2>

In this task, I need to obtain a list of all machines with the 'OS 2' operating system because these machines need an update. To get this information, I’ll run my first SQL query with a filter.

- Select all the records from the ```machines``` table with a value of 'OS 2' in the ```operating_system``` column. Replace the value X with the correct string:

```SELECT device_id, operating_system```

```FROM machines```
 
```WHERE operating_system = 'X';```

Note: The WHERE clause allows you to filter the results returned by a query by returning only the records that satisfy the condition.

Here I see 80 machines in the database use the OS 2 operating system:

![image](https://github.com/n8som/Filter-a-SQL-Query/assets/110139109/cf18b579-aa9f-4ca2-a215-36c636a70ad8)

<h2>Task 3. List employees in specific departments</h2>

In this task, I need to retrieve a list of all the employees in the Finance and Sales departments to obtain their office numbers. A notice about handling confidential financial information will be posted to these offices.

1. Filter the rows returned from the ```department``` column in the ```employees``` table to include only employees from the 'Finance' department. Replace X with the appropriate column name and Y with the appropriate value to complete the filter:

```SELECT *```

```FROM employees``` 

```WHERE X = 'Y';```

Here I see the employee_id, 1003, is in the first row:

![image](https://github.com/n8som/Filter-a-SQL-Query/assets/110139109/ec855b3e-b0e2-4268-abb2-62a6b01cbfb4)

2. Modify the previous query so that it returns employees who are in the 'Sales' department.

Here I see 33 employees work in the Sales department:

![image](https://github.com/n8som/Filter-a-SQL-Query/assets/110139109/c5dfb4b9-d2e8-4278-9797-62ba0e2375a9)

<h2>Task 4. Identify employee machines</h2>

My team recently discovered that there are issues with machines in the South building. In this task, I need to obtain certain employee and computer information.

A machine in 'South-109' has an issue. I need to determine which employee uses that computer so I can send them an alert.

1. Write a query to identify which employee uses the office in 'South-109'. (The data must be returned from the ```office``` column in the ```employees``` table.)

Here I see the employee, jlansky, uses the computer with the issue:

![image](https://github.com/n8som/Filter-a-SQL-Query/assets/110139109/a12e5396-dfe2-4b34-a927-66bfee2610db)

Next, my team has determined that there is an issue with all the machines in the South building. Offices in the organization are named with the building name, a hyphen, and the office number in that building (for example, 'South-109').

2. Modify the query I used in the previous step so that it returns information on all the employees in the 'South' building. Use the ```LIKE``` operator with ```%``` in this query.

Note: The ```LIKE``` keyword in SQL performs simple string matches. The matching pattern may include the wildcard ```%``` to represent a string of any length. This wildcard may be placed both before and after the targeted substring.

Here I see the department that the first employee listed in the South building belongs to Finance:

![image](https://github.com/n8som/Filter-a-SQL-Query/assets/110139109/be1a0974-e289-40b2-8ea2-3c6e4b9d8279)

<h2>Conclusion</h2>

I now have practical experience in using SQL to

- apply the ```WHERE``` clause to filter what a SQL query returns and
- use the ```LIKE``` operator to filter for patterns.

I'm well on my way to running SQL queries to get specific data from a database.

