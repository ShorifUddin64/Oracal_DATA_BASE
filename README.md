<div align="center">

  <!-- Oracle Database Animated Header -->
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=700&size=26&pause=1000&color=F80000&center=true&vCenter=true&width=650&height=70&lines=ORACLE+DATABASE+%26+SQL+LAB;PL%2FSQL+PROCEDURES+%26+QUERIES;SECURE+DATA+MANAGEMENT" alt="Oracle DB Banner" />

  <p align="center">
    <code><b>DATABASE: ORACLE 19c/21c</b> • <b>LANGUAGE: SQL / PL-SQL</b> • <b>SECURITY: SQL INJECTION DEFENSE</b></code>
  </p>

  <p align="center">
    <img src="https://img.shields.io/badge/Database-Oracle_DB-F80000?style=for-the-badge&logo=oracle&logoColor=white" alt="Oracle" />
    <img src="https://img.shields.io/badge/Language-SQL_%26_PL%2FSQL-000000?style=for-the-badge&logo=databricks&logoColor=red" alt="SQL" />
    <img src="https://img.shields.io/badge/Focus-Query_Optimization-00F2FE?style=for-the-badge&logo=speedtest&logoColor=black" alt="Optimization" />
  </p>

</div>

<br/>

> ```text
>   ___  ____   _     ____  _     _____ 
>  / _ \|  _ \ / \   / ___|| |   | ____|
> | | | | |_) / _ \ | |    | |   |  _|  
> | |_| |  __/ ___ \| |___ | |___| |___ 
>  \___/|_| /_/   \_\____||_____|_____|
> ```

---
ER_Diagram Creat: https://edotor.net/ (CORD)

ER_Diagram: https://app.diagrams.net/ (Shape)
### 🗄️ Database Environment Overview

```yaml
Database Engine  : Oracle Database (19c / Enterprise Edition)
Query Languages  : SQL, PL/SQL (Procedures, Functions, Triggers)
Tools & Client   : Oracle SQL Developer, SQL*Plus, Command Line Interface
Security Mindset : Input Sanitization, Role-Based Access Control (RBAC), Prepared Statements
```

### Key Word : 
Foreign key, References, constraint,,values,unique,Varcher</font>
```yaml
=========================================================
************************************************************
```
```diff
-SELECT & FILTERING PRACTICE COMMANDS
```
```yaml
************************************************************
=========================================================

SELECT * FROM DEMO;
SELECT NAME, TO_CHAR(JOIN_DATE, 'YYYY-MM-DD HH24:MI:SS') AS FULL_DATE_TIME FROM DEMO WHERE NAME = 'Sajid Khan';
SELECT NAME, TO_CHAR(JOIN_DATE, 'YYYY-MM-DD HH24:MI:SS') AS FULL_DATE_TIME FROM DEMO WHERE NAME = 'Anika Rahman';

SELECT * FROM DEMO ORDER BY ID;
SELECT * FROM DEMO WHERE SALARY > 40000 AND STATUS = 'Active';               -- Both conditions true
SELECT * FROM DEMO WHERE STATUS = 'Inactive' OR BONUS = 0;                  -- Either condition true
SELECT * FROM DEMO WHERE SALARY BETWEEN 40000 AND 70000;                     -- Salary in range
SELECT * FROM DEMO WHERE ID IN (5, 8, 10);                                  -- Match specific IDs
SELECT ID, UPPER(NAME) FROM DEMO;                                           -- Convert name to capital
SELECT ID, LOWER(NAME) FROM DEMO;                                           -- Convert name to small
SELECT ID, NAME, (SALARY + BONUS) AS TOTAL_INCOME FROM DEMO;                -- Calculate total income
SELECT NAME, LENGTH(NAME) AS LETTER_COUNT FROM DEMO;                        -- Count letters in name
SELECT ID, SUBSTR(NAME, 1, 3) AS SHORT_NAME FROM DEMO;                      -- Cut first 3 letters
SELECT * FROM DEMO ORDER BY STATUS ASC, ID DESC;                            -- Double sort structure
SELECT * FROM DEMO WHERE NAME IN (SELECT NAME FROM DEMO GROUP BY NAME HAVING COUNT(NAME) > 1) ORDER BY NAME;
SELECT * FROM DEMO ORDER BY ID ASC;                                         -- Sort small to big
SELECT * FROM DEMO ORDER BY ID DESC;                                        -- Sort big to small
SELECT ID, NAME, BONUS + 100 AS NEW_BONUS FROM DEMO;                        -- Add 100 to bonus
SELECT ID, NAME || ' is ' || STATUS AS EMP_DETAILS FROM DEMO;               -- Combine 2 columns
SELECT ID, NAME AS EMPLOYEE_NAME FROM DEMO;                                 -- Change column display name
SELECT * FROM DEMO WHERE VAT IS NULL;                                       -- Find empty VAT rows
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
                                                      RENDOME DATA MANAGMENT SYSTEM
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

select * from emp;
select avg(sal)*110 as Avgsalary from emp;
select avg(SELLING_PRICE_$)*110 as "AvgsSELLING_PRICE_BDT" from VEHICLE;
select * from vehicle where regdate between '01-may-21' and '20-may-2021';
select * from emp where hiredate between '01-may-2081' and '20-may-2081';
select * from emp where hiredate between '01-may-81' and '2020-may-2081';
select * from emp where hiredate between '01-may-81' and '20-may-2081';
select * from emp where hiredate between '01-may-81' and '20-may-81';
SELECT * FROM emp WHERE hiredate BETWEEN '01-MAY-2081' AND '20-MAY-2081';
SELECT * FROM emp 
WHERE hiredate BETWEEN TO_DATE('01-05-2081', 'DD-MM-YYYY') 
                   AND TO_DATE('20-05-2081', 'DD-MM-YYYY');

select * from emp where hiredate between '01-may-1981' and '20-may-1981';

SELECT TYPE, SUM(SELLING_PRICE_$) AS TOTAL_SELLING_PRICE
FROM VEHICLE
WHERE REGDATE IS NOT NULL
GROUP BY TYPE
HAVING SUM(SELLING_PRICE_$) > 987999;
SELECT VEHICLE_NO, 
       TYPE,
       SELLING_PRICE_$ * DECODE(TYPE, 
                                'MICROBUS', 0.80, 
                                'TRUCK', 0.90, 
                                'PRIVATE CAR', 0.85, 
                                1) AS DISCOUNTED_PRICE
FROM VEHICLE;

SELECT *
FROM VEHICLE
WHERE UPPER(TYPE) LIKE '%BUS';
SELECT VEHICLE_NO,
       NVL(TO_CHAR(REGDATE, 'YYYY-MM-DD'), 'NULL') AS REGDATE,
       TYPE
FROM VEHICLE
WHERE VEHICLE_NO = 112;
SELECT CONCAT(ename, job),
       INSTR(ename, 'p'),
       SUBSTR(job, 2, 3),
       TRIM('p' FROM job),
       LENGTH(job),
       LOWER(hiredate),
       UPPER(ename),
       INITCAP(ename),
```
```diff
-//////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
-//////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
-//////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
```
-- =========================================================
************************************************************
-- STEP 1: DROP OLD TABLE (RESET ENVIRONMENT)
************************************************************
-- =========================================================
DROP TABLE DEMO;


-- =========================================================
-- STEP 2: CREATE THE MAIN TABLE STRUCTURE
-- =========================================================
CREATE TABLE DEMO (
    ID NUMBER NOT NULL,               -- 1. Unique Employee ID, cannot be empty (NOT NULL)
    NAME VARCHAR2(50) NOT NULL,       -- 2. Employee Name, mandatory column (NOT NULL)
    SALARY NUMBER(10) DEFAULT 0,    -- 3. Base Salary, automatically sets to 0 if left blank
    BONUS NUMBER(10,2) DEFAULT 0,     -- 4. Bonus, automatically sets to 0 if left blank
    VAT NUMBER(10,2),                 -- 5. VAT column, defaults to null for tax calculations
    JOIN_DATE DATE,                   -- 6. Stores both registration date and time together
    ABOUT_EMP CLOB,                   -- 7. Large character object for long descriptions/bios
    STATUS VARCHAR2(10),              -- 8. Current employment status (Active/Inactive)
    PRIMARY KEY (ID)                  -- 9. Declares ID as the main unique key
);
-- =========================================================
-- STEP 3: FIGHER CHACK
-- =========================================================
DESC <TABLE NAME>;
DESC  DEPARTMENT;

-- =========================================================
-- STEP 3: VIEWING COLUMN CONSTRAINT NEW NAME
-- =========================================================
SELECT constraint_name, column_name 
FROM user_cons_columns 
WHERE table_name = '<table_name>';

-- =========================================================
-- STEP 3: VIEWING CHECK CONDITION
-- =========================================================
SELECT constraint_name, search_condition 
FROM user_constraints 
WHERE table_name = '<table_name>';

-- =========================================================
-- STEP 3: DIRECT VALUES INSERTION & SPECIFIC RECORDS
-- =========================================================

-- RECORD 1: SAJID KHAN
INSERT INTO DEMO (ID, NAME, SALARY, BONUS, VAT, JOIN_DATE, ABOUT_EMP, STATUS) 
VALUES (
    1, 
    'Sajid Khan', 
    55000, 
    2500.00, 
    750.50, 
    TO_DATE('2025-01-15 14:20:00', 'YYYY-MM-DD HH24:MI:SS'), 
    'Senior Developer specializing in Java GUI Swing frameworks and corporate database management systems.', 
    'Active'
);

-- RECORD 2: ANIKA RAHMAN
INSERT INTO DEMO (STATUS, VAT, BONUS, SALARY, NAME, ID, ABOUT_EMP, JOIN_DATE) 
VALUES (
    'Active',
    0, 
    2000, 
    45000.90, 
    'Anika Rahman', 
    2, 
    'Data Analyst managing company-wide database migrations and tuning operations.', 
    TO_DATE('2025-03-20', 'YYYY-MM-DD')
);

-- RECORD 3: ROHIT SHARMA (SCRAMBLED RE-CREATED)
INSERT INTO DEMO (ABOUT_EMP, VAT, ID, STATUS, SALARY, NAME, JOIN_DATE) 
VALUES (
    NULL, 
    500, 
    3, 
    NULL, 
    DEFAULT, 
    'Rohit Sharma', 
    SYSDATE
);

DELETE FROM DEMO WHERE ID = 3;

-- RE-CREATING RECORD 3
INSERT INTO DEMO VALUES (
    3, 
    'Rohit Sharma', 
    0, 
    0, 
    500, 
    SYSDATE, 
    NULL, 
    'Unctive'
);

INSERT INTO DEMO (ID, NAME, STATUS) VALUES (4, 'Rohit Sharma', 'Inactive');

-- BULK RECORDS (5 TO 10)
INSERT INTO DEMO VALUES (5, 'Emma', 62001, 3500, 150, SYSDATE, 'QA Engineer specialized in automation.', 'Active');
INSERT INTO DEMO VALUES (6, 'Virat', 85000, 0, 200, SYSDATE, 'Project Manager handling Agile development.', 'Active');
INSERT INTO DEMO VALUES (7, 'Zayn', 40000, 1200, 0, TO_DATE('2024-11-05', 'YYYY-MM-DD'), NULL, 'Inactive');
INSERT INTO DEMO VALUES (8, 'Anna', 55000, 2000, 100, SYSDATE, 'UI/UX Designer with creative concepts.', 'Active');
INSERT INTO DEMO VALUES (9, 'Luke', 32000, 1000, 50, SYSDATE, 'Support Lead managing customer queries.', 'Active');
INSERT INTO DEMO VALUES (10, 'Sara', 72000, 4000, 300, TO_DATE('2025-05-20', 'YYYY-MM-DD'), 'Marketing executive.', 'Active');
--
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
                                                      RENDOME DATA BASE ENVIORENTMENT CREAT
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
Primary Key:
create table deptk(deptid number(3) primary key,dname varchar2(12));

Foreign Key:
create table student(id number(11) constraint pkk primary key,name varchar2(32),cgpa float,deptid number(3),constraint fkk foreign key(deptid) references deptk(deptid));

insert into student(id,name,cgpa) values(15,'ABC',2.8);
insert into deptk values(3,'BBA');

select * from deptk;
select * from student;
drop table student;

Not NULL:
create table student(id number(3) constraint nkk not null,dname varchar(12))

UNIQUE:
create table student(id number(3) constraint ukk unique,dname varchar(12))

Default:
create table student(id number(3) default(0),dname varchar(12))

Check:
coulmn level:
create table student(id number(11) constraint pkk primary key,name varchar2(32),cgpa float constraint ckk check(cgpa between 0 and 4),deptid number(3),constraint fkk foreign key(deptid) references deptk(deptid));
table level:
create table teacher(id number(3) constraint tkk primary key,tname varchar2(32),sal number(20),deptno number(3),constraint fkkk foreign key(deptno) references deptf(deptno),constraint ckkk check(id in(1,2,3) and tname like 'A%'))
Table level:
create table student(id number(11) constraint pkk primary key,name varchar2(32),cgpa float,deptid number(3),constraint fkk foreign key(deptid) references deptk(deptid), constraint ckk check(cgpa between 0 and 4 and name like 'A%'));
Alter Constraints:
Alter table student add constraint pkk primary key(id);
Alter table student add constraint fkk foreign key(deptid) references dept(deptno);
Alter table student add constraint ukk unique(id);
Alter table student modify id default(0);
Alter table student modify id not null;
Alter table student add constraint ckk check(id in(1,2,3));
drop table deptk;
CREATE TABLE DEPTK ( DEPTID NUMBER(3) PRIMARY KEY, DNAME VARCHAR2(12));
INSERT INTO DEPTK (DEPTID,DNAME) VALUES (1,'P');
SELECT * FROM DEPTK;
DROP TABLE STUDENT;
CREATE TABLE STUDENT ( ID NUMBER(11) CONSTRAINT PK PRIMARY KEY, NAME VARCHAR2(32),CGPA FLOAT, DEPTID NUMBER(3), CONSTRAINT FK FOREIGN KEY(DEPTID) REFERENCES DEPTK(DEPTID));
INSERT INTO STUDENT( ID,NAME,CGPA) VALUES(2,'S',2.5);
INSERT INTO STUDENT( ID,NAME,CGPA,DEPTID) VALUES(2,'S',2.5,1);
SELECT * FROM STUDENT;
  DROP TABLE DEPARTMENT;

CREATE TABLE DEPARTMENT(
DEPTID NUMBER(3) CONSTRAINT PK PRIMARY KEY,
S NUMBER(9) CHECK(S BETWEEN 20 AND 50),
DEPT_NAME VARCHAR(6) CHECK(DEPT_NAME IN('CSE','EEE','BBA','ENG','ACH')),
BUDGET NUMBER(6) DEFAULT(0));

DESC  DEPARTMENT;

SELECT constraint_name, search_condition 
FROM user_constraints 
WHERE table_name = 'DEPARTMENT';

SELECT constraint_name, column_name 
FROM user_cons_columns 
WHERE table_name = 'DEPARTMENT';

DROP TABLE COURSE;

CREATE TABLE COURSE (
CRS_ID NUMBER(4) CONSTRAINT FKC PRIMARY KEY,
CRS_NAME VARCHAR2(20) NOT NULL,
DEPT_ID NUMBER(3) DEFAULT(0),
FOREIGN KEY(DEPT_ID) REFERENCES DEPARTMENT(DEPTID));

DESC COURSE;

SELECT constraint_name, search_condition 
FROM user_constraints 
WHERE table_name = 'COURSE';

SELECT constraint_name, column_name 
FROM user_cons_columns 
WHERE table_name = 'COURSE';


       REPLACE(job, 't', 'p')
FROM emp;
