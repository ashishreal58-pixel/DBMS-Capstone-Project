IT Helpdesk & Incident Management System

DBMS Capstone Project

Project Overview

The IT Helpdesk & Incident Management System is a database-driven web application designed to manage IT support requests, incidents, ticket assignments, service-level agreements (SLAs), and support activities.

The project demonstrates the practical implementation of Database Management System concepts using MySQL, MongoDB, Python, and Flask.

Objectives

- Design and implement a relational database.
- Develop an ER/EER diagram and relational schema.
- Apply functional dependencies and normalization.
- Implement complex SQL queries.
- Use stored procedures, functions, and triggers.
- Demonstrate transaction management and concurrency control.
- Implement role-based access control and database security.
- Integrate MongoDB for NoSQL operations.
- Develop a web-based application using Flask.

Key Features

- User and role management.
- IT incident and ticket management.
- Ticket assignment and tracking.
- SLA monitoring.
- Incident status management.
- Activity and audit logging.
- Advanced SQL operations.
- Database security and access control.
- MongoDB integration.
- Flask-based web interface.

Technologies Used

Technology| Purpose
MySQL| Relational database
MongoDB| NoSQL database
Python| Backend programming
Flask| Web framework
HTML/CSS| Frontend
PyMySQL| MySQL connectivity
PyMongo| MongoDB connectivity
GitHub| Version control

Project Structure

DBMS-Capstone-Project/
│
├── README.md
│
└── IT.helpdesk_capstone/
    ├── README.md
    ├── 00_design_document.md
    ├── 01_schema.sql
    ├── 02_data.sql
    ├── 03_views_indexes.sql
    ├── 04_triggers_procs_functions.sql
    ├── 05_queries.sql
    ├── 06_transactions_concurrency.sql
    ├── 07_rbac_security.sql
    ├── 08_test_cases.sql
    ├── 09_mongodb_extension.js
    ├── 10_app.py
    ├── 11_sqli_demo.py
    └── generate_data.py

DBMS Concepts Implemented

- Database design and normalization.
- Primary keys and foreign keys.
- Constraints and referential integrity.
- Joins, subqueries, and aggregate functions.
- Views and indexes.
- Stored procedures and functions.
- Triggers.
- Query optimization using EXPLAIN.
- ACID properties and transactions.
- Concurrency control and locking.
- Role-based access control.
- SQL injection prevention.
- MongoDB CRUD and aggregation.

Installation and Execution

1. Clone Repository

git clone https://github.com/ashishreal58-pixel/DBMS-Capstone-Project.git

2. Install Dependencies

pip install flask pymysql pymongo

3. Configure MySQL

Start MySQL Server and execute the SQL scripts in the following order:

1. "01_schema.sql"
2. "02_data.sql"
3. "03_views_indexes.sql"
4. "04_triggers_procs_functions.sql"
5. "05_queries.sql"
6. "06_transactions_concurrency.sql"
7. "07_rbac_security.sql"
8. "08_test_cases.sql"

4. Configure MongoDB

Start MongoDB and execute:

mongosh 09_mongodb_extension.js

5. Run Application

python 10_app.py

Open your browser:

http://127.0.0.1:5000

Note: Run commands from the project directory, configure database credentials, and adjust script paths if necessary.

Expected Deliverables

- Requirements and business rules.
- ER/EER diagram and relational schema.
- Functional dependencies and normalization.
- SQL scripts and realistic dataset.
- Complex SQL query set.
- Views, indexes, and query optimization.
- Stored procedures, functions, and triggers.
- Transaction and concurrency demonstrations.
- Database security and RBAC.
- MongoDB integration.
- Web application.
- Testing and documentation.

Conclusion

The IT Helpdesk & Incident Management System demonstrates the practical application of database management concepts in a real-world IT support environment. It combines relational database management, NoSQL integration, advanced SQL programming, security, and web development.

Repository

GitHub: https://github.com/ashishreal58-pixel/DBMS-Capstone-Project

Project Type: DBMS Capstone Project
