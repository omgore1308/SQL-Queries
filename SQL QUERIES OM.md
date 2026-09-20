1.BASIC QUERIES.



show databases;



create database company;



use company;



create table employee (empID INT ,name varchar(50) ,gender varchar(30) ,email varchar(40) ,mobNo bigint );



DESC employee;



insert into employee(empID,name,gender,email,mobNo)values(121,"om","male","omgore@gmail.com",6467989785);



select \* from employee;



Delete from employee WHERE empID = 121;



update employee set name = "rohan" WHERE empID = 121;



select email from employee;



select name,email,gender from employee;





2.PRIMARY KEY



&#x20;create table employee (empID  INT PRIMARY KEY ,name varchar(50) ,gender varchar(30) ,email varchar(40) ,mobNo bigint );





3.LOGICAL OPERATOR





select \* from employee wHERE email is NOT NULL;



select \* from employee wHERE gender is NULL;



select \* from employee WHERE name = rohan and gender = male;



select \* from employee WHERE name = ram OR gender = male;



SELECT \* FROM employee WHERE NOT gender = "male";





4.NULL QUERIES



select \* from employee wHERE email is NOT NULL;



select \* from employee wHERE gender is NULL;





5.ALTER QUERIES





ALTER table employee ADD column city varchar(40);



ALTER table employee MODIFY column mobNO int;



ALTER TABLE employee DROP column email;



ALTER TABLE employee RENAME COLUMN city to state;



ALTER table employee rename TABLE employeeData;



DROP TABLE employeeData;



DROP DATABASE company;





6.ORDER BY





select \* from employee ORDER BY name ASC;



select \* from employee ORDER BY name DESC;







7.UNIQUE KEY



create table employee (empID INT PRIMARY KEY ,name varchar(50) NOT NULL ,gender varchar(30) ,email varchar(40) UNIQUE ,mobNo bigint UNIQUE NOT NULL);







8.LIMIT \& OFFSET



SELECT \* from employee LIMIT 5  OFFSET 3;





9.LIAS



SELECT name AS Official\_name FROM employee;





10.DATATYPES



create table



&#x20;create table employee(empID INT, MobNO BIGINT, height FLOAT, salary DOUBLE, tax DECIMAL(5,2), gender CHAR, name VARCHAR(50), feedback TEXT, joining\_date DATE, work\_time TIME, punchIn TIMESTAMP, is\_active BOOLEAN, extra JSON);





insert values



&#x20;insert into employee values(101,6789665638,6.5,6500.000,150.00,'M','Om','i like your communication','2026-05-18', '07:30:00','2026-08-13  06:20:00', TRUE, '{"name":"om","city":"Nashik"}');





11.operator comparison



select \* from employee WHERE age > 18;



select \* from employee WHERE age >= 18;



select \* from employee WHERE age < 18;



select \* from employee WHERE age <= 18;



select \* from employee WHERE age <> 18;  ---------> NOT EQUALS TO





12.DEFAULT



create table employee (empID int, name varchar(50), city varchar(40) DEFAULT 'PUNE', mobNo bigint );





13.CHECK



create table employee (empID int, name varchar(50), city varchar(40) DEFAULT 'PUNE', mobNo bigint , age int check(age >= 18);



14.IN OPERATOR



select \* from employee WHERE city IN('Pune','Mumbai','Nashik');



15.BETWEEN OPERATOR



select \* from employee WHERE age BETWEEN 18 AND 25;



16.AGGREGATE FUNCTION



\--> select count(empID) from employee;



\--> select SUM(salary) from employee;



\--> select MAX(age) from employee;



\--> select MIN(AGE) from employee;



\--> select AVG(salary) from employee;



17.DISTINCT



select DISTINCT city from employee;



18.LIKE OPERATOR



\---> select \* from employee WHERE name LIKE 'A%';



\---> select \* from employee WHERE name LIKE '%A';



\---> select \* from employee WHERE name LIKE '\_A%';



\---> select \* from employee WHERE name LIKE 'A%\_';



19.TRUNCATE



TRUNCATE table employee;



20.AUTO\_INCREMENT



create table employee(empID int PRIMARY KEY AUTO\_INCREMENT, empName varchar(50), city varchar(40));



21.GROUP BY 



select city, SUM(salary) from employee GROUP BY city;



22\. HAVING clause



select city, SUM(salary) from employee GROUP BY CITY HAVING salary >= 30000;



23.NESTED QUERIES(Sub queries)



select \* from employee WHERE AGE = (select \* from employee where age )



select \* from employee WHERE salary = (select MAX(salary) from employee WHERE profile = 'test');



select name,experience from employee WHERE salary = (select min(salary) FROM employee);



23.FOREIGN KEY



TABLE 1 - create table DEPARTMENT(deptID int PRIMARY KEY AUTO\_INCREMENT, deptName varchar(40), deptsize int);



TABLE 2 - create table EMPLOYEE(empId int PRIMARY KEY, empName varchar(50), city varchar (40), deptId int, FOREIGN KEY deptID REFERENCES DEPARTMENT deptID);



24.JOINS 



\--> SELECT \* from DEPARTMENT JOIN EMPLOYEE USING(deptID);



\--> SELECT \* from  DEPARTMENT JOIN EMPLOYEE ON DEPARTMENT.deptID = EMPLOYEE.deptID;



\--> INNER JOIN --> SELECT employee.empID, employee.empName, employee.city, employee.deptID, department.deptName,department.deptsize FROM EMPLOYEE INNER JOIN DEPARTMENT ON employee.deptID = department.deptID; --> ONLY FETCH MATCHING ROWS BETWEEN BOTH COLUMNS



\--> LEFT JOIN --> SELECT employee.empID, employee.empName, employee.city, employee.deptID, department.deptName,department.deptsize FROM EMPLOYEE LEFT JOIN DEPARTMENT ON employee.deptID = department.deptID; --> IT Fetch all rows from the 

left table and also fetch common column from right table



\--> Right JOIN -->  SELECT employee.empID, employee.empName, employee.city, employee.deptID, department.deptName,department.deptsize FROM EMPLOYEE RIGHT JOIN DEPARTMENT ON employee.deptID = department.deptID; --> IT Fetch all rows from the RIGHT table and also fetch common column from left table

&#x20;

\--> FULL OUTER join -->  SELECT employee.empID, employee.empName, employee.city, employee.deptID, department.deptName,department.deptsize FROM EMPLOYEE FULL OUTER JOIN DEPARTMENT ON employee.deptID = department.deptID; --> IT Fetch all  from the left table and right table, also fetch unmatch rows.



\--> CROSS JOIN -->  SELECT employees.name, departments.dept\_name

&#x20;    FROM employees

&#x20;    CROSS JOIN departments;

\-->The CROSS JOIN keyword returns all records from both tables (table1 and table2).



\--> self JOIN --> Shows employees and their managers (from the same table)./ it is a regular join, but the table is joined with itself.



\--> Query : SELECT e1.name AS Employee, e2.name AS Manager

FROM employees e1

INNER JOIN employees e2

ON e1.manager\_id = e2.emp\_id;











&#x20;















&#x20;







&#x20;

