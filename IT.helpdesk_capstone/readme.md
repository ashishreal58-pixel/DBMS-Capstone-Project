IT Helpdesk & Incident Management System

Internal Technical Documentation

This directory contains the implementation files for the IT Helpdesk & Incident Management System DBMS Capstone Project.

1. Project Description

The application manages IT support incidents, ticket creation, assignment, resolution tracking, SLA monitoring, and user activities.

The database uses MySQL for structured relational information and MongoDB for additional NoSQL operations and activity logging.

2. File Documentation

File| Description
"00_design_document.md"| Requirements, business rules, and database design
"01_schema.sql"| Database and table creation
"02_data.sql"| Sample dataset insertion
"03_views_indexes.sql"| Views and indexes
"04_triggers_procs_functions.sql"| Triggers, stored procedures, and functions
"05_queries.sql"| Complex SQL queries
"06_transactions_concurrency.sql"| Transaction and concurrency demonstrations
"07_rbac_security.sql"| Roles, privileges, and security
"08_test_cases.sql"| Database testing
"09_mongodb_extension.js"| MongoDB implementation
"10_app.py"| Flask web application
"11_sqli_demo.py"| SQL injection demonstration
"generate_data.py"| Sample data generation



Screenshot checklist (name files as shown, paste in report in this order)
#	Screenshot	From
1	EER diagram (Database → Reverse Engineer)	after 01
2	SHOW TABLES (22 tables) + row-count query	01/02
3–20	One per query Q1…Q18 (query + result grid)	05
21	4 views output	03
22	EXPLAIN before indexes (type=ALL)	03 (A)
23	EXPLAIN after indexes (type=ref/range) + SHOW INDEX	03 (C)
24	Trigger creation + SHOW TRIGGERS	04
25	sp_create_incident → history + SLA rows + audit_log	04 smoke test
26	fn_sla_status output	04
27	Transaction Scenario 1 COMMIT	06 A1
28	Scenario 2 error + ROLLBACK + unchanged row	06 A2
29	Scenario 3 SAVEPOINT (before / after rollback to savepoint)	06 A3
30	Scenario 4 auto-escalation	06 A4
31	Scenario 5 failed escalation but assignment kept	06 A5
32	Cursor SLA monitor result	06 A7
33	Session A + Session B side by side: B blocked on FOR UPDATE	06 B2
34	Session B after A commits → "already assigned" error	06 B2
35	Lost update (without lock) vs conditional update (1 vs 0 rows)	06 B1/B3
36	Deadlock ERROR 1213 + SHOW ENGINE INNODB STATUS	06 B6
37	SHOW GRANTS for 4 roles	07
38	End user: SELECT * FROM incident → ERROR 1142, v_my_incidents OK	07 tests
39	Agent: DELETE/DROP denied	07 tests
40	SQL injection succeeds (vulnerable) vs 0 rows (prepared)	07 §6 or 11_sqli_demo.py
41	Test-case outputs (constraint errors)	08
42	MongoDB: insert / find / update / delete	09
43	MongoDB: aggregation pipelines + $lookup	09
44	Flask app: open tickets, create ticket, assign, SLA page, Mongo activity	10
45	(Optional) MongoDB Atlas / cloud MySQL connection	—


3. Database Configuration

Database Name: "helpdesk_db"

Database Management System: MySQL

NoSQL Database: MongoDB

Before executing the application, configure the MySQL and MongoDB connection details.

Example MySQL configuration:

DB_CONFIG = {
    "host": "localhost",
    "user": "root",
    "password": "your_password",
    "database": "helpdesk_db"
}

Do not commit real database passwords or secret credentials to GitHub.

4. SQL Execution Order

Execute the SQL scripts in the following sequence:

1. Create the database and relational tables.
2. Insert the sample dataset.
3. Create views and indexes.
4. Create triggers, stored procedures, and functions.
5. Execute complex SQL queries.
6. Test transactions and concurrency.
7. Configure database roles and permissions.
8. Execute database test cases.

5. Database Concepts

Relational Database Design

- Entity Relationship modelling.
- Primary and foreign keys.
- Referential integrity.
- Functional dependencies.
- 1NF, 2NF, and 3NF normalization.

SQL Implementation

- DDL, DML, and DQL.
- Joins and nested queries.
- Aggregate functions.
- Views and indexes.
- Stored procedures.
- User-defined functions.
- Triggers.

Transaction Processing

- ACID properties.
- COMMIT and ROLLBACK.
- SAVEPOINT.
- Locking mechanisms.
- Concurrency control.

Database Security

- User roles and privileges.
- Access control.
- SQL injection prevention.
- Prepared statements.

MongoDB

- CRUD operations.
- Document-based storage.
- Aggregation pipelines.
- Data retrieval and updates.

6. Application Execution

Install dependencies:

pip install flask pymysql pymongo

Start the MySQL and MongoDB services.

Configure the database connections in the Python application.

Run:

python 10_app.py

Access the local application:

http://127.0.0.1:5000

7. Testing and Validation

The project includes testing for:

- Table creation and constraints.
- Data insertion and retrieval.
- Primary and foreign key validation.
- Complex SQL queries.
- Trigger execution.
- Stored procedure execution.
- Transaction rollback.
- Concurrent database operations.
- User privileges and access control.
- MongoDB operations.
- SQL injection prevention.

8. Expected Results

The completed system should provide:

- Structured IT incident management.
- Reliable ticket assignment and tracking.
- Database integrity and consistency.
- Advanced SQL functionality.
- Secure database access.
- NoSQL integration.
- Web-based interaction with the database.

9. Notes

- Execute SQL scripts in the recommended order.
- Ensure database services are running.
- Verify connection credentials before launching Flask.
- Use realistic sample data for testing.
- Store screenshots and test evidence separately.
- Never upload sensitive credentials.

