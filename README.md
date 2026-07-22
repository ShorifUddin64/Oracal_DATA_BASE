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

### 🗄️ Database Environment Overview

```yaml
Database Engine  : Oracle Database (19c / Enterprise Edition)
Query Languages  : SQL, PL/SQL (Procedures, Functions, Triggers)
Tools & Client   : Oracle SQL Developer, SQL*Plus, Command Line Interface
Security Mindset : Input Sanitization, Role-Based Access Control (RBAC), Prepared Statements
-- =========================================================
-- STEP 1: DROP OLD TABLE (RESET ENVIRONMENT)
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


-- =========================================================
-- SELECT & FILTERING PRACTICE COMMANDS
-- =========================================================

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


