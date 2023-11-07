# EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands

## DATE : 11/08/23

## AIM :

To create a student database and execute DDL queries using SQL.
To create a manager database and execute DML queries using SQL.

## DML(Data Manipulation Language) :

<div align="justify">
The SQL commands that deal with the manipulation of data present in the database belong to DML or Data Manipulation Language and this includes most of the SQL statements. It is the component of the SQL statement that controls access to data and to the database. Basically, DCL statements are grouped with DML statements.
</div>

## List of DML commands :

<div align="justify">
INSERT: It is used to insert data into a table.<br>
UPDATE: It is used to update existing data within a table.<br>
DELETE: It is used to delete records from a database table.<br>
</div>

## Create the table as given below :
```sql
create table manager(enumber number(6),ename char(15),salary number(5),
commission number(4),annualsalary number(7),Hiredate date,designation char(10)
,deptno number(2),reporting char(10));
```
## insert the following values into the table
```sql
insert into manager values(7369,'Dharsan',2500,500,30000,'30-June-81','clerk',10,'John');
insert into manager values(7839,'Subu',3000,400,36000,'1-Jul-82','manager',null,'James');
insert into manager values(7934,'Aadhi',3500,300,42000,'1-May-82','manager',30,NULL);
insert into manager values(7788,'Vikash',4000,0,48000,'12-Aug-82','clerk',50,'Bond');
```
### Q1) Update all the records of manager table by increasing 10% of their salary as bonus.
### QUERY :
```
UPDATE manager
SET salary = salary + (salary * 0.10),
annualsalary = annualsalary + (annualsalary * 0.10);
```
### OUTPUT :

![image](https://github.com/Abrinnisha6/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118889454/093e49fe-14fd-494e-9d66-ce119e3f05fa)

### Q2) Delete the records from manager table where the salary less than 2750.
### QUERY :
```
DELETE FROM manager WHERE salary < 2750;
```
### OUTPUT :

![image](https://github.com/Abrinnisha6/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118889454/30f98df0-d3a0-423f-af3d-0cf6ba8c82db)

### Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)
### QUERY :
```
SELECT ename AS "Name", salary * 12 AS "Annual Salary"
FROM manager;
```
### OUTPUT :
![image](https://github.com/Abrinnisha6/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118889454/148fcdbf-3956-4ab5-95f5-bc33effb7ac4)

### Q5) List the names of Clerks from emp table.
### QUERY :
```
SELECT ename from manager where designation='clerk';
```
### OUTPUT :
![image](https://github.com/Abrinnisha6/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118889454/c26bd95a-f247-46b0-ba87-21410acfc861)

### Q6) List the names of employee who are not Managers.
### QUERY :
```
SELECT ename from manager where designation!='manager';
```
### OUTPUT :
![image](https://github.com/Abrinnisha6/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118889454/18f59582-4d4d-438f-a5af-69e7773c1aaa)

### Q7) List the names of employees not eligible for commission.
### QUERY :
```
SELECT ename from manager where commission=0;
```
### OUTPUT :
![image](https://github.com/Abrinnisha6/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118889454/d50396bc-cb6b-4c99-bb41-03b8b330ea7b)

### Q8) List employees whose name either start or end with ‘s’.
### QUERY :
```
SELECT ename
FROM manager
WHERE ename LIKE 'S%' OR ename LIKE '%s';
```
### OUTPUT :
![image](https://github.com/Abrinnisha6/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118889454/4e4b6f6d-57f3-4bc5-bd24-a4b0283252eb)

### Q9) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.
### QUERY :
```
select ename,designation,deptno,Hiredate from manager
order by Hiredate asc;
```
### OUTPUT :
![image](https://github.com/Abrinnisha6/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118889454/c29a9d32-55d4-4b2c-ac11-628ec30bdd59)

### Q10) List the Details of Employees who have joined before 30 Sept 81.
### QUERY :
```
SELECT *
FROM manager
WHERE Hiredate < TO_DATE('1981-09-30', 'YYYY-MM-DD');
```
### OUTPUT :
![image](https://github.com/Abrinnisha6/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118889454/802677ae-6940-44f9-8f09-d794230cfca3)

### Q11) List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.
### QUERY :
```
select ename,deptno,salary from manager order by deptno asc;
select ename,deptno,salary from manager order by salary desc;
```
### OUTPUT :

![image](https://github.com/Abrinnisha6/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118889454/1b3cce1b-5886-4459-8782-885d2a2d9b33)

![image](https://github.com/Abrinnisha6/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118889454/4b7a668a-3fa8-4ebc-9c70-dd446783c1d1)

### Q12) List the names of employees not belonging to dept no 30,40 & 10
### QUERY :
```
select ename from manager where deptno not in (10,30,40);
```
### OUTPUT :
![image](https://github.com/Abrinnisha6/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118889454/9f20ecbb-f12c-4767-ae5f-f1bf2ee18d90)

## Q13) Find number of rows in the table EMP
## QUERY :
```
select count(*) from manager;
```
## OUTPUT :
![image](https://github.com/Abrinnisha6/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118889454/764a9b58-aa1e-4a1d-acd5-2f18dc629fd1)

### Q14) Find maximum, minimum and average salary in EMP table.
### QUERY :
```
select ename ,salary,annualsalary from manager
where salary = (select max(salary) from manager);

select ename ,salary,annualsalary from manager
where salary = (select min(salary) from manager);

select avg(salary) from manager;
```
### OUTPUT :

![image](https://github.com/Abrinnisha6/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118889454/06bff0bb-fa36-42e5-86e2-fea412afabb9)

![image](https://github.com/Abrinnisha6/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118889454/9110a1b9-87d7-4f07-8473-492ba3a0a493)

![image](https://github.com/Abrinnisha6/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118889454/3487b3f5-ca85-4475-b1ba-d87236fcba64)

### Q15) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.
### QUERY :
```
SELECT designation, COUNT(*) AS "Number of Employees"
FROM manager
GROUP BY designation
ORDER BY COUNT(*) DESC;
```
### OUTPUT :

![image](https://github.com/Abrinnisha6/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118889454/4a0d6bc8-27ec-4984-8d07-7e40d40a87b1)

## RESULT :

Thus, Manager database is created and DML queries such as insertion, updation, deletion are executed using SQL.
