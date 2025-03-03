# DBMS Basics - Enhanced Notes

## 1. Basics of DBMS: Data vs. Information, DBMS vs. File Systems, Applications of DBMS.

### Data vs. Information:

*   **Data:** Think of data as raw, unorganized facts. It's like individual ingredients in a kitchen (flour, sugar, eggs). They don't mean much on their own. The slide mentions "known facts recorded with implicit meaning." For example, the number 22, an image of a cat, or the name "Alice".
*   **Information:** Information is processed, organized, and structured data that gives it meaning and makes it useful. It's like a cake made from those ingredients. The slide says it's "processed data used for decision-making." So, if we know "Alice" is 22 years old, that *is* information. If we have a database of cat images and can search for "Siamese cats", that search result is information.

### DBMS vs. File Systems:

*   **File System:** Imagine a filing cabinet where you store individual documents (files). Each file is independent. This is similar to how early computer systems stored data. Think of a simple text file (.txt) or a spreadsheet (.csv). They're useful for simple tasks but become problematic when you need to manage large amounts of related data.
*   **DBMS (Database Management System):** A DBMS is a sophisticated software system designed to manage databases. It's like a highly organized, computerized library. It provides tools for storing, retrieving, updating, and managing data efficiently and securely. Examples include Oracle, MySQL, PostgreSQL, and Microsoft SQL Server.

### Applications of DBMS:

DBMS are used everywhere! Think about:

*   Banking: Managing accounts, transactions, loans.
*   E-commerce: Storing product information, customer details, orders.
*   Social Media: Managing user profiles, posts, connections.
*   Healthcare: Storing patient records, medical history, appointments.
*   Education: Managing student information, courses, grades.

## 2. Importance of Data: Improves lives, supports decision-making, solves problems.

Data is crucial for informed decision-making. Businesses use data to understand customer behavior, optimize operations, and identify new opportunities. In healthcare, data analysis can lead to better diagnoses and treatment plans. Governments use data to track trends, allocate resources, and develop policies.

## 3. Database Components: Storage, coding, GUI, SQL programming.

*   **Storage:** Where the data is physically stored (e.g., hard drives, SSDs, cloud storage).
*   **Coding:** The underlying code that makes the DBMS work (often written in languages like C++, Java).
*   **GUI (Graphical User Interface):** The visual interface that allows users to interact with the DBMS (e.g., phpMyAdmin for MySQL).
*   **SQL Programming:** SQL (Structured Query Language) is the standard language for interacting with databases. It's used to create, read, update, and delete data.

## 4. DBMS Definition: Software to store, manage, and retrieve databases (e.g., Oracle, MySQL).

This is a restatement of what we discussed earlier. It's the core concept of what a DBMS is.

## 5. File System Drawbacks: Redundancy, inconsistency, isolation, security issues, atomicity problems.

This is why DBMS were created! File systems have major limitations:

*   **Redundancy:** Data can be duplicated across multiple files, wasting storage space. Imagine having the same customer address in 10 different files.
*   **Inconsistency:** If you update the address in one file but not the others, you have inconsistent data.
*   **Isolation:** It's difficult to access related data that's spread across multiple files.
*   **Security Issues:** File systems typically have limited security features, making them vulnerable to unauthorized access.
*   **Atomicity Problems:** If a transaction (e.g., transferring money) involves updating multiple files, and one update fails, the entire transaction can be left in an inconsistent state.

## 6. Advantages of DBMS: Fast access, reduced redundancy, data consistency, security, concurrent access.

DBMS address the limitations of file systems:

*   **Fast Access:** DBMS use indexing and other techniques to quickly retrieve data.
*   **Reduced Redundancy:** Data is stored in a structured way, minimizing duplication.
*   **Data Consistency:** DBMS enforce rules and constraints to ensure data integrity.
*   **Security:** DBMS provide security features like user authentication, authorization, and encryption.
*   **Concurrent Access:** Multiple users can access and modify the database simultaneously without interfering with each other.

## 7. Database Users: End Users, Application Developers, Database Administrators (DBA), Systems Programmers.

*   **End Users:** People who use the applications that interact with the database (e.g., a bank teller, a customer using an e-commerce website).
*   **Application Developers:** Programmers who write the applications that access and manipulate the data in the database.
*   **Database Administrators (DBA):** Responsible for managing the database system, including security, performance, and backup/recovery.
*   **Systems Programmers:** Programmers who design and implement the DBMS software itself.

## 8. Examples: UNIVERSITY Database: Entities (Students, Courses), Relationships (Enrollment, Prerequisites).

This is a classic example.

*   **Entities:** Real-world objects that we want to store information about (e.g., Students, Courses).
*   **Relationships:** How the entities are related to each other (e.g., Enrollment - students enroll in courses; Prerequisites - a course might require another course as a prerequisite).

## 9. ACID Transaction Example: Fund transfer between accounts with atomicity and consistency.

ACID is a set of properties that guarantee reliable transaction processing:

*   **Atomicity:** The entire transaction is treated as a single, indivisible unit of work. Either all changes are applied, or none are.
*   **Consistency:** The transaction must maintain the integrity of the database. It must move the database from one valid state to another.
*   **Isolation:** Transactions are isolated from each other. Concurrent transactions should not interfere with each other's results.
*   **Durability:** Once a transaction is committed, the changes are permanent and will survive even system failures.

### Fund Transfer Example:

If you transfer $100 from account A to account B:

*   Debit $100 from account A.
*   Credit $100 to account B.

*   **Atomicity:** Either both steps happen, or neither happens. If the system crashes after step 1, the DBMS must ensure that the debit from account A is rolled back.
*   **Consistency:** The total amount of money in the system remains the same.
*   **Isolation:** If another transaction is trying to read the balance of account A while the transfer is in progress, it should see either the old balance or the new balance, but not an intermediate state.
*   **Durability:** Once the transfer is complete, the changes are permanent, even if the system crashes.

## Week 1: Exam-Style Question Answers

1.  **Explain the difference between data and information. Provide an example of each.**

    *   **Data:** Raw, unorganized facts or figures. It's like the individual pixels in an image or the letters in a word. Data has no inherent meaning until it is processed.
        *   *Example:* The number `25`, the word `"apple"`, a digital image of a tree.
    *   **Information:** Processed, organized, and structured data that provides context and meaning, enabling decision-making. It's the result of analyzing and interpreting data.
        *   *Example:* `"The temperature is 25 degrees Celsius"`, `"The fruit is an apple"`, a weather forecast generated from weather data.

2.  **What are the key drawbacks of using a file system to manage data compared to a DBMS?**

    *   **Data Redundancy:** The same data can be stored in multiple files, wasting storage space and increasing the risk of inconsistency.
    *   **Data Inconsistency:** If the same data is stored in multiple files and one copy is updated while others are not, the data becomes inconsistent.
    *   **Data Isolation:** It's difficult to access related data that is spread across multiple files.
    *   **Security Issues:** File systems typically have limited security features, making them vulnerable to unauthorized access.
    *   **Atomicity Problems:** Transactions involving updates to multiple files may not be atomic, leading to data corruption if a failure occurs during the transaction.

3.  **List and explain the ACID properties of a transaction. Why are these properties important?**

    *   **Atomicity:** A transaction is treated as a single, indivisible unit of work. Either all changes within the transaction are applied, or none are.
    *   **Consistency:** A transaction must maintain the integrity of the database. It must move the database from one valid state to another.
    *   **Isolation:** Transactions are isolated from each other. Concurrent transactions should not interfere with each other's results.
    *   **Durability:** Once a transaction is committed, the changes are permanent and will survive even system failures.

    *Importance:* ACID properties ensure data reliability and integrity, especially in multi-user environments where concurrent transactions are common.

4.  **Describe the roles of different types of database users (end users, application developers, DBAs).**

    *   **End Users:** People who use the applications that interact with the database (e.g., bank tellers, customers using an e-commerce website). They typically don't interact directly with the DBMS.
    *   **Application Developers:** Programmers who write the applications that access and manipulate the data in the database. They use SQL and other programming languages to build the user interface and business logic.
    *   **Database Administrators (DBA):** Responsible for managing the database system, including security, performance tuning, backup/recovery, and user access control.
    *   **Systems Programmers:** Programmers who design and implement the DBMS software itself.

5.  **Give an example of a real-world application of a DBMS and explain how it is used.**

    *   *Example:* **Banking System**
        *   A DBMS is used to store and manage customer accounts, transactions, loans, and other financial data.
        *   It ensures the security and integrity of financial data.
        *   It provides fast and reliable access to account information for bank tellers and customers.
        *   It supports complex transactions such as fund transfers and loan processing.


## Week 02 - DBMS Architectures and Data Models - Enhanced Notes

### 1. DBMS Architectures:

*   **Centralized:** Imagine a single, powerful computer that handles everything related to the database. All users connect directly to this central system. It's simpler to manage but can become a bottleneck with many users. Think of a small library where all the books and the librarian are in one room.
*   **2-Tier Client-Server:** Here, the workload is divided. The client (e.g., your computer running a database application) sends requests to a specialized server (e.g., a database server like MySQL). The server processes the request and sends back the results. Think of a restaurant where you (the client) place an order with the waiter (the network) who relays it to the chef (the server).
*   **3-Tier Client-Server:** This adds another layer, typically an application server or web server, between the client and the database server. This middle layer handles application logic, data validation, and security. It improves scalability and security. Think of a restaurant with a maitre d' (application server) who takes your order, checks if you have a reservation, and then relays it to the waiter, who then gives it to the chef.

### 2. ANSI/SPARC Three-Level Architecture:

This is a conceptual framework for how a DBMS should be organized:

*   **External Schema (View Level):** This is what individual users see. Each user can have a different view of the database, tailored to their needs. For example, a student might see their grades and courses, while a professor sees course rosters and assignment submissions. Think of different people looking at the same car: one person might focus on the engine, another on the interior, and another on the paint job.
*   **Conceptual Schema (Logical Level):** This is the overall structure of the database, defining all the entities, attributes, and relationships. It's a complete, logical view of the data. Think of the blueprint of the car, showing all its components and how they fit together.
*   **Internal Schema (Physical Level):** This describes how the data is physically stored on the storage devices. It includes details like file structures, indexes, and data types. Think of the actual physical materials used to build the car and how they are arranged.

### 3. Data Independence:

This is the ability to change one level of the architecture without affecting the other levels:

*   **Logical Data Independence:** You can change the conceptual schema (e.g., add a new attribute to a table) without affecting the external schemas (user views). Users don't need to change their applications. Think of redesigning the blueprint of the car without changing the way the driver uses it.
*   **Physical Data Independence:** You can change the internal schema (e.g., change the storage format or add an index) without affecting the conceptual schema or external schemas. Users and applications don't need to know about the physical storage details. Think of changing the materials used to build the car without changing its design or how the driver uses it.

### 4. Data Types:

*   **Structured Data:** Data that has a predefined format and is typically stored in tables with rows and columns (e.g., data in a relational database like MySQL).
*   **Unstructured Data:** Data that doesn't have a predefined format (e.g., text documents, images, videos). NoSQL databases are often used to manage unstructured data.

### 5. ACID Properties:

(We already covered this in the previous slide, but it's important, so let's reiterate):

*   **Atomicity:** All or nothing.
*   **Consistency:** Maintains data integrity.
*   **Isolation:** Transactions don't interfere.
*   **Durability:** Changes are permanent.

### 6. SQL vs. NoSQL:

*   **SQL (Relational Databases):**
    *   **Predefined Schema:** Data must conform to a predefined structure (tables with rows and columns).
    *   **Joins:** Used to combine data from multiple tables based on relationships.
    *   **Vertical Scaling:** Scaling by increasing the resources (CPU, RAM) of a single server.
    *   **Examples:** MySQL, PostgreSQL, Oracle, SQL Server.
*   **NoSQL (Non-Relational Databases):**
    *   **Schema-less:** Data can be stored in various formats (e.g., JSON documents, key-value pairs) without a predefined structure.
    *   **Flexible:** Easier to adapt to changing data requirements.
    *   **Horizontal Scaling:** Scaling by adding more servers to the system.
    *   **Examples:** MongoDB, Cassandra, Redis.

### 7. Data Models:

*   **Object-Based Data Models:** Use concepts like entities, attributes, and relationships to represent data. The Entity-Relationship (ER) model is a common example.
*   **Record-Based Data Models:** Data is organized into records.
    *   **Hierarchical Model:** Data is organized in a tree-like structure.
    *   **Network Model:** Similar to the hierarchical model, but allows more complex relationships.
    *   **Relational Model:** Data is organized into tables with rows and columns.
*   **Physical Data Models:** Describe how data is physically stored on the storage devices. The Unifying Model is an example.

### 8. DBMS Languages:

*   **DDL (Data Definition Language):** Used to define the structure of the database (e.g., creating tables, defining data types).
    *   `CREATE`: Creates database objects (e.g., tables, indexes).
    *   `ALTER`: Modifies database objects.
    *   `DROP`: Deletes database objects.
*   **DML (Data Manipulation Language):** Used to manipulate the data in the database (e.g., inserting, updating, deleting data).
    *   `SELECT`: Retrieves data from the database.
    *   `INSERT`: Adds new data to the database.
    *   `UPDATE`: Modifies existing data in the database.
    *   `DELETE`: Removes data from the database.
*   **DCL (Data Control Language):** Used to control access to the database (e.g., granting or revoking permissions).
    *   `GRANT`: Gives users permission to access database objects.
    *   `REVOKE`: Removes permissions from users.
*   **TCL (Transaction Control Language):** Used to manage transactions (e.g., committing or rolling back changes).
    *   `COMMIT`: Saves the changes made by a transaction.
    *   `ROLLBACK`: Undoes the changes made by a transaction.

### 9. Miscellaneous:

*   **Motivating Scenario:** Large-scale data management for Pakistan Foundation (performance, security, durability). This highlights the need for a robust DBMS to handle large volumes of data, ensure data security, and provide reliable data storage.
*   **Factors for Choosing DBMS:**
    *   **Flexibility:** How easily can the DBMS adapt to changing data requirements?
    *   **Query Efficiency:** How quickly can the DBMS retrieve data?
    *   **Security:** How well does the DBMS protect data from unauthorized access?

## Week 2: Exam-Style Question Answers

1.  **Compare and contrast the centralized, 2-tier client-server, and 3-tier client-server DBMS architectures.**

    *   **Centralized:**
        *   *Description:* All DBMS components (software, hardware, user interfaces) reside on a single system.
        *   *Advantages:* Simpler to manage.
        *   *Disadvantages:* Can become a bottleneck with many users, limited scalability.
    *   **2-Tier Client-Server:**
        *   *Description:* The client (e.g., application) sends requests to a specialized server (e.g., database server).
        *   *Advantages:* Improved scalability compared to centralized.
        *   *Disadvantages:* Limited security, increased network traffic.
    *   **3-Tier Client-Server:**
        *   *Description:* Adds an application server between the client and the database server.
        *   *Advantages:* Improved scalability, security, and data processing.
        *   *Disadvantages:* More complex to manage.

2.  **Explain the three levels of the ANSI/SPARC architecture and their importance for data independence.**

    *   **External Schema (View Level):** User-specific views of the database.
    *   **Conceptual Schema (Logical Level):** Overall structure of the database, defining entities, attributes, and relationships.
    *   **Internal Schema (Physical Level):** Physical storage details (file structures, indexes).

    *Importance for Data Independence:*
        *   Allows changes at one level without affecting other levels.
        *   Logical data independence allows changes to the conceptual schema without affecting external schemas.
        *   Physical data independence allows changes to the internal schema without affecting the conceptual schema or external schemas.

3.  **What is the difference between logical and physical data independence? Why is data independence important?**

    *   **Logical Data Independence:** The ability to modify the conceptual schema (e.g., add a new attribute) without affecting the external schemas (user views).
    *   **Physical Data Independence:** The ability to modify the internal schema (e.g., change the storage format) without affecting the conceptual schema or external schemas.

    *Importance:* Data independence reduces the maintenance effort, improves flexibility, and allows the database to evolve without disrupting existing applications.

4.  **Explain the difference between SQL and NoSQL databases. Give examples of when you would use each type of database.**

    *   **SQL (Relational Databases):**
        *   *Schema:* Predefined schema (tables with rows and columns).
        *   *Scaling:* Vertical scaling (increasing resources of a single server).
        *   *Examples:* MySQL, PostgreSQL, Oracle, SQL Server.
    *   **NoSQL (Non-Relational Databases):**
        *   *Schema:* Schema-less (data can be stored in various formats).
        *   *Scaling:* Horizontal scaling (adding more servers to the system).
        *   *Examples:* MongoDB, Cassandra, Redis.

    *Use Cases:*
        *   *SQL:* Suitable for applications with structured data, complex relationships, and ACID requirements (e.g., banking, e-commerce).
        *   *NoSQL:* Suitable for applications with unstructured data, high scalability requirements, and flexible data models (e.g., social media, content management).

5.  **Describe the different types of data models (object-based, record-based, physical).**

    *   **Object-Based Data Models:** Use concepts like entities, attributes, and relationships (e.g., ER Model).
    *   **Record-Based Data Models:** Data is organized into records.
        *   Hierarchical Model: Data is organized in a tree-like structure.
        *   Network Model: Similar to the hierarchical model, but allows more complex relationships.
        *   Relational Model: Data is organized into tables with rows and columns.
    *   **Physical Data Models:** Describe how data is physically stored (e.g., Unifying Model).

6.  **What are the main categories of DBMS languages (DDL, DML, DCL, TCL)? Give examples of commands in each category.**

    *   **DDL (Data Definition Language):** Used to define the database structure.
        *   *Examples:* `CREATE TABLE`, `ALTER TABLE`, `DROP TABLE`
    *   **DML (Data Manipulation Language):** Used to manipulate the data.
        *   *Examples:* `SELECT`, `INSERT`, `UPDATE`, `DELETE`
    *   **DCL (Data Control Language):** Used to control access to data.
        *   *Examples:* `GRANT`, `REVOKE`
    *   **TCL (Transaction Control Language):** Used to manage transactions.
        *   *Examples:* `COMMIT`, `ROLLBACK`

7.  **What factors should you consider when choosing a DBMS for a specific application?**

    *   Flexibility: How easily can the DBMS adapt to changing data requirements?
    *   Query Efficiency: How quickly can the DBMS retrieve data?
    *   Security: How well does the DBMS protect data from unauthorized access?
    *   Scalability: How well can the DBMS handle increasing data volumes and user traffic?
    *   Cost: The cost of the DBMS software, hardware, and administration.
    *   Features: Does the DBMS have the features required by the application (e.g., support for specific data types, transaction management, etc.)?


## Week 03 - Database Schema, Development, DFDs, and ERDs - Enhanced Notes

### 1. Database Schema vs. State:

*   **Schema (Intension):** Think of the schema as the *blueprint* or *design* of your database. It defines the structure, including:
    *   Tables: The containers for your data.
    *   Columns: The attributes or properties of each table.
    *   Data Types: The type of data that can be stored in each column (e.g., integer, text, date).
    *   Constraints: Rules that enforce data integrity (e.g., primary keys, foreign keys).
    *   Functions, Triggers, Stored Procedures: Reusable code blocks that perform specific tasks.

    The schema is relatively *static* and changes infrequently. It's like the architectural plans for a building.
*   **State/Instance (Extension):** The state (or instance) is the actual *data* stored in the database *at a particular moment in time*. It's the *content* of the database. Think of it as the occupancy of the building at a specific time: who is in which room, what furniture is there, etc. The state changes frequently as data is inserted, updated, and deleted.

    *Analogy:* Think of a class roster. The schema is the *structure* of the roster: student name, ID, major, etc. The state is the *list of students* enrolled in the class at a specific point in the semester.

### 2. Database Development Process:

*   **Stages:**
    *   Preliminary Study: Understand the problem and determine if a database is the right solution.
    *   Requirements Analysis: Gather detailed information about the data to be stored and the operations to be performed on the data. What are the user needs?
    *   Database Design: Create the schema (logical design) of the database. This includes defining tables, columns, relationships, and constraints.
    *   Physical Design: Determine how the database will be physically stored (e.g., file structures, indexes).
    *   Implementation: Build the database and load the data.
    *   Maintenance: Monitor and maintain the database, including performance tuning, security updates, and backup/recovery.
*   **Strategies:**
    *   Top-Down: Start with a high-level understanding of the system and then break it down into smaller details. Start with general goals and refine into specific requirements. It's like planning a road trip by first deciding on the destination and then figuring out the route.
    *   Bottom-Up: Start with specific requirements and then build up to a more general understanding of the system. Start with specific goals and then integrate them into a general structure. It's like building a house by starting with individual bricks and then assembling them into walls and rooms.

### 3. Data Flow Diagrams (DFD):

DFDs are used to model the flow of data through a system. They show how data moves between processes, data stores, and external entities.

*   **Levels:**
    *   Context Diagram (Level 0): Shows the entire system as a single process and its interactions with external entities. It provides a high-level overview.
    *   Level 1 DFD: Decomposes the context diagram into more detailed processes and data flows.
    *   Level 2+ DFD: Further decomposes the Level 1 DFD into even more detailed processes.

    *Analogy:* Think of a factory. The Context Diagram shows the factory as a whole and its interactions with suppliers and customers. The Level 1 DFD shows the main departments within the factory (e.g., production, shipping, receiving). Level 2+ DFDs show the individual processes within each department.

### 4. Entity Relationship Diagram (ERD):

*   **Purpose:** ERDs are used to graphically represent the entities, attributes, and relationships in a database. They are a key tool for database design.

    *Translates into relational tables:* An ERD is a blueprint for creating the tables in a relational database. Each entity becomes a table, attributes become columns, and relationships are implemented using foreign keys.

*   **Components:**
    *   Entities: Real-world objects that we want to store information about (e.g., Student, Course, Employee, Product). Represented as rectangles.
    *   Attributes: Properties of entities (e.g., student's name, course's title, employee's salary, product's price). Represented as ovals.
    *   Relationships: Associations between entities (e.g., "student enrolls in course," "employee works on project," "customer places order"). Represented as diamonds.
*   **Types of Entities:**
    *   Strong Entity: An entity that has a primary key (a unique identifier). For example, a Student entity with `roll_no` as the primary key.
    *   Weak Entity: An entity that depends on another entity for its existence and doesn't have a primary key of its own. It uses a *partial key* combined with the primary key of the related entity to uniquely identify its instances. For example, a Dependent entity (e.g., a child of an employee) might depend on the Employee entity. The Dependent entity might have a partial key like `dependent_name`, which is unique *within* the context of a particular employee.
*   **Attributes:**
    *   Simple (Atomic): An attribute that cannot be further divided (e.g., `age`, `name`).
    *   Composite: An attribute that is composed of multiple sub-attributes (e.g., `Address` consisting of `street`, `city`, `state`, `zip`).
    *   Multi-Valued: An attribute that can have multiple values for a single entity instance (e.g., `phone_numbers` for a person). In a relational database, multi-valued attributes are typically handled by creating a separate table.
    *   Derived: An attribute whose value can be calculated from other attributes (e.g., `age` can be derived from `date_of_birth`).
    *   Key Attribute: An attribute that uniquely identifies each instance of an entity (e.g., `roll_no` for a student). This becomes the primary key of the corresponding table.
*   **Case Study (University Registrar):**
    *   Entities: Courses, Course Offerings, Students, Instructors.
    *   Relationships: Enrollment (students enroll in course offerings), Grades (students receive grades in course offerings), Prerequisites (courses have prerequisites), Teaching Assignments (instructors are assigned to teach course offerings).

## Week 3: Exam-Style Question Answers

1.  **Explain the difference between a database schema and a database state. Give an example of each.**

    *   **Database Schema:** The *design* or *blueprint* of the database. It defines the tables, columns, data types, constraints, and relationships. It's relatively static.
        *   *Example:* A table named "Students" with columns "StudentID" (integer, primary key), "Name" (text), "Major" (text).
    *   **Database State:** The *data* stored in the database at a specific point in time. It's the actual content of the tables. It changes frequently as data is inserted, updated, and deleted.
        *   *Example:* The "Students" table contains the following rows: (1, "Alice", "CS"), (2, "Bob", "EE"), (3, "Charlie", "ME").

2.  **Describe the different stages of the database development process.**

    *   Preliminary Study: Understand the problem and determine if a database is the right solution.
    *   Requirements Analysis: Gather detailed information about the data to be stored and the operations to be performed.
    *   Database Design: Create the schema (logical design) of the database.
    *   Physical Design: Determine how the database will be physically stored.
    *   Implementation: Build the database and load the data.
    *   Maintenance: Monitor and maintain the database.

3.  **Compare and contrast the top-down and bottom-up strategies for database development.**

    *   **Top-Down:** Start with a high-level understanding of the system and then break it down into smaller details.
        *   *Advantages:* Ensures that the database meets the overall goals of the organization.
        *   *Disadvantages:* Can be difficult to identify all the specific requirements upfront.
    *   **Bottom-Up:** Start with specific requirements and then build up to a more general understanding of the system.
        *   *Advantages:* Ensures that the database meets the specific needs of individual users and applications.
        *   *Disadvantages:* Can be difficult to integrate the different requirements into a coherent whole.

4.  **What is a Data Flow Diagram (DFD)? Explain the different levels of a DFD.**

    *   *Data Flow Diagram (DFD):* A graphical representation of the flow of data through a system. It shows how data moves between processes, data stores, and external entities.
    *   *Levels:*
        *   Context Diagram (Level 0): Shows the entire system as a single process.
        *   Level 1 DFD: Decomposes the context diagram into more detailed processes and data flows.
        *   Level 2+ DFD: Further decomposes the Level 1 DFD into even more detailed processes.

5.  **What is an Entity Relationship Diagram (ERD)? Explain the purpose of an ERD and its main components (entities, attributes, relationships).**

    *   *Entity Relationship Diagram (ERD):* A graphical representation of the entities, attributes, and relationships in a database.
    *   *Purpose:* To model the structure of the database and to communicate the design to stakeholders.
    *   *Components:*
        *   Entities: Real-world objects (e.g., Student, Course).
        *   Attributes: Properties of entities (e.g., student's name, course's title).
        *   Relationships: Associations between entities (e.g., "student enrolls in course").

6.  **Explain the difference between a strong entity and a weak entity. Give an example of each.**

    *   *Strong Entity:* Has a primary key.
        *   *Example:* A "Student" entity with "StudentID" as the primary key.
    *   *Weak Entity:* Depends on another entity for its existence and doesn't have a primary key of its own.
        *   *Example:* A "Dependent" entity (e.g., a child of an employee) that depends on the "Employee" entity. The "Dependent" entity might have a partial key like "dependent_name", which is unique *within* the context of a particular employee.

7.  **Describe the different types of attributes (simple, composite, multi-valued, derived, key). Give an example of each.**

    *   Simple (Atomic): Cannot be further divided (e.g., age, name).
    *   Composite: Composed of multiple sub-attributes (e.g., Address consisting of street, city, state, zip).
    *   Multi-Valued: Can have multiple values for a single entity (e.g., phone_numbers).
    *   Derived: Calculated from other attributes (e.g., age can be derived from date_of_birth).
    *   Key Attribute: Uniquely identifies each instance of an entity (e.g., roll_no for a student).

8.  **Design a simple ERD for a library database, including entities like Books, Authors, and Patrons, and relationships like "borrows" and "writes".**

    *   Entities:
        *   Book (BookID, Title, ISBN, PublicationYear)
        *   Author (AuthorID, Name, Bio)
        *   Patron (PatronID, Name, Address, PhoneNumber)
    *   Relationships:
        *   Writes (Author writes Book): M:N relationship (one author can write multiple books, and one book can have multiple authors). This would require a bridge table "BookAuthor" (BookID, AuthorID).
        *   Borrows (Patron borrows Book): M:N relationship (one patron can borrow multiple books, and one book can be borrowed by multiple patrons). This would require a bridge table "Loan" (LoanID, PatronID, BookID, LoanDate, DueDate).


## Week 04 - Relationships, Cardinalities, and Participation in ERDs - Enhanced Notes

### 1. Relationships in ERD:

*   **Degree of Relationships:** The degree of a relationship refers to the number of entities involved in the relationship.
    *   **Unary (Recursive):** A relationship between instances of the *same* entity. Think of it as a relationship *within* a single table.
        *   *Example:* `Employee supervises Employee`. This means one employee can supervise other employees. In a database, you'd have an `Employee` table with a `supervisor_id` column that references another employee's ID in the same table.
    *   **Binary:** A relationship between *two different* entities. This is the most common type of relationship.
        *   *Example:* `Student enrolls in Course`. This relates the `Student` entity to the `Course` entity.
    *   **Ternary:** A relationship among *three different* entities.
        *   *Example:* `Doctor prescribes Medicine to Patient`. This relates the `Doctor`, `Medicine`, and `Patient` entities.

### 2. Mapping Cardinalities:

Mapping cardinalities specify how many instances of one entity can be related to how many instances of another entity.

*   **1:1 (One-to-One):** One instance of entity A is related to *one* instance of entity B, and vice versa.
    *   *Example:* `One passport ↔ one person`. Each person has only one passport, and each passport belongs to only one person.
*   **1:M (One-to-Many):** One instance of entity A can be related to *multiple* instances of entity B, but each instance of entity B is related to *only one* instance of entity A.
    *   *Example:* `One customer ↔ multiple orders`. A customer can place many orders, but each order belongs to only one customer.
*   **M:N (Many-to-Many):** One instance of entity A can be related to *multiple* instances of entity B, and vice versa.
    *   *Example:* `Students enroll in multiple courses; courses have multiple students`. A student can enroll in many courses, and each course can have many students.
        *   *Requires a bridge entity (e.g., Enrollment table):* Many-to-many relationships are typically implemented in relational databases using a *bridge table* (also called an *associative entity* or *junction table*). This table contains foreign keys referencing both entities involved in the relationship. In the `Students enroll in multiple courses` example, you would create an `Enrollment` table with foreign keys to the `Student` table and the `Course` table. The `Enrollment` table would store records of which students are enrolled in which courses.

### 3. Participation Constraints:

Participation constraints specify whether an entity *must* participate in a relationship.

*   **Total Participation (Mandatory):** *All* instances of an entity *must* participate in the relationship. This is also known as *existence dependency*. In ER diagrams, total participation is often represented by a *double line*.
    *   *Example:* `Every license must belong to an employee`. This means that there cannot be a license that is not associated with an employee.
*   **Partial Participation (Optional):** *Not all* instances of an entity are required to participate in the relationship. In ER diagrams, partial participation is often represented by a *single line*.
    *   *Example:* `Not all employees have a license`. This means that some employees may not have a license.

### 4. Structural Constraints (min, max):

These constraints define the *minimum* and *maximum* number of instances of one entity that can be related to an instance of another entity. This provides a more precise definition of the relationship.

*   *Example:* `A professor teaches 1–4 classes, and each class is taught by exactly 1 professor`. This combines cardinality and participation constraints.

### 5. Examples of Relationships:

*   1:1: `Person ↔ Passport`
*   1:M: `Department ↔ Employees` (One department can have many employees, but each employee belongs to only one department).
*   M:N: `Books ↔ Authors` (One book can have multiple authors, and one author can write multiple books).

### 6. Key Notations:

*   **Chen Model:** Uses `1` and `M` symbols to represent cardinality.
*   **Crow’s Foot:** A graphical notation that uses "crow's feet" to represent the "many" side of a relationship. It's a visual way to represent cardinality.

## Week 4: Exam-Style Question Answers

1.  **Explain the different degrees of relationships (unary, binary, ternary) in ER diagrams. Give an example of each.**

    *   *Unary (Recursive):* A relationship between instances of the same entity.
        *   *Example:* `Employee supervises Employee`.
    *   *Binary:* A relationship between two different entities.
        *   *Example:* `Student enrolls in Course`.
    *   *Ternary:* A relationship among three different entities.
        *   *Example:* `Doctor prescribes Medicine to Patient`.

2.  **Describe the different types of mapping cardinalities (1:1, 1:M, M:N). Give an example of each.**

    *   *1:1 (One-to-One):* One instance of entity A is related to one instance of entity B, and vice versa.
        *   *Example:* `One passport ↔ one person`.
    *   *1:M (One-to-Many):* One instance of entity A can be related to multiple instances of entity B, but each instance of entity B is related to only one instance of entity A.
        *   *Example:* `One customer ↔ multiple orders`.
    *   *M:N (Many-to-Many):* One instance of entity A can be related to multiple instances of entity B, and vice versa.
        *   *Example:* `Students enroll in multiple courses; courses have multiple students`.

3.  **What is a bridge entity (associative entity)? Why is it needed for many-to-many relationships?**

    *   *Bridge Entity (Associative Entity):* A table used to implement many-to-many relationships in a relational database. It contains foreign keys referencing the primary keys of the two entities involved in the relationship.
    *   *Why Needed:* Relational databases cannot directly represent many-to-many relationships. A bridge entity decomposes the M:N relationship into two 1:M relationships.

4.  **Explain the difference between total participation and partial participation constraints. Give an example of each. How are they represented in ER diagrams?**

    *   *Total Participation (Mandatory):* All instances of an entity *must* participate in the relationship. Represented by a *double line* in ER diagrams.
        *   *Example:* `Every license must belong to an employee`.
    *   *Partial Participation (Optional):* Not all instances of an entity are required to participate in the relationship. Represented by a *single line* in ER diagrams.
        *   *Example:* `Not all employees have a license`.

5.  **How do structural constraints (min, max) provide a more precise definition of relationships?**

    Structural constraints (min, max) specify the *minimum* and *maximum* number of instances of one entity that can be related to an instance of another entity, providing a more precise definition than just cardinality alone.

6.  **Draw an ER diagram for a library database, including entities like Books, Authors, and Patrons, and relationships like "borrows" and "writes." Specify the cardinality and participation constraints for each relationship. Use Crow's Foot notation.**

    (Due to the limitations of text-based responses, I cannot draw an ER diagram. However, I can describe it):

    *   Entities:
        *   Book (BookID, Title, ISBN, PublicationYear)
        *   Author (AuthorID, Name, Bio)
        *   Patron (PatronID, Name, Address, PhoneNumber)
    *   Relationships:
        *   Writes (Author writes Book): M:N relationship. A bridge table "BookAuthor" (BookID, AuthorID) is needed. Cardinality using Crow's Foot: Author --<  BookAuthor >-- Book (Crow's foot on both sides). Participation constraints: Total participation of BookAuthor with both Author and Book.
        *   Borrows (Patron borrows Book): M:N relationship. A bridge table "Loan" (LoanID, PatronID, BookID, LoanDate, DueDate) is needed. Cardinality using Crow's Foot: Patron --< Loan >-- Book (Crow's foot on both sides). Participation constraints: Total participation of Loan with both Patron and Book.

7.  **Consider a database for a social media platform. Identify the entities and relationships, including cardinalities and participation constraints.**

    *   Entities:
        *   User (UserID, Username, Email, Password, ProfilePicture)
        *   Post (PostID, UserID, Timestamp, Content)
        *   Comment (CommentID, PostID, UserID, Timestamp, Content)
    *   Relationships:
        *   User creates Post: 1:M relationship (one user can create multiple posts). Total participation of Post (every post must be created by a user).
        *   Post has Comments: 1:M relationship (one post can have multiple comments). Total participation of Comment (every comment must belong to a post).
        *   User likes Post: M:N relationship (one user can like multiple posts, and one post can be liked by multiple users). A bridge table "Likes" (UserID, PostID) would be needed.


## Week 05 - Mandatory/Optional Cardinality, ERD Example, and Keys - Enhanced Notes

### 1. Mandatory vs. Optional Cardinality:

This is a restatement of participation constraints, but the terms are slightly different.

*   **Mandatory:** An entity *must* participate in the relationship. This is the same as *total participation*.
    *   *Example:* `Employee must have a CNIC (Computerized National Identity Card)`. This implies a total participation constraint on the `Employee` entity in the relationship with the `CNIC`.
*   **Optional:** An entity *may or may not* participate in the relationship. This is the same as *partial participation*.
    *   *Example:* `Employee may own a Car`. This implies a partial participation constraint on the `Employee` entity in the relationship with the `Car` entity.

*   **Crow's Foot Notation:** As mentioned before, this notation uses symbols to represent cardinality and participation constraints.
    *   `Single line`: Represents optional participation (zero or one).
    *   `Double line`: Represents mandatory participation (one or more, specifically at least one).
    *   Other symbols are used to specify the "many" side of the relationship (the "crow's foot" itself).

### 2. ERD Example (Company Database):

*   **Entities:** `DEPARTMENT`, `PROJECT`, `EMPLOYEE`, `DEPENDENT`.
*   **Relationships:**
    *   `Departments control projects`. (Implies a 1:M relationship: One department can control multiple projects, but each project is controlled by only one department).
    *   `Employees work on projects (tracking hours)`. (Implies an M:N relationship, requiring a bridge entity like `WorksOn` to track the hours each employee works on each project).
    *   `Employees have dependents`. (Implies a 1:M relationship: One employee can have multiple dependents, but each dependent belongs to only one employee).
    *   `Employees report to supervisors`. (Unary/Recursive relationship on the `Employee` entity, as one employee can be a supervisor for other employees).

### 3. Steps to Create an ER Diagram:

This is a good summary of the process:

1.  Entity Identification: Identify the main objects or concepts that need to be represented in the database.
2.  Relationship Identification: Determine how the entities are related to each other.
3.  Cardinality Identification: Determine the cardinality constraints for each relationship (1:1, 1:M, M:N).
4.  Attribute Identification: Determine the attributes (properties) of each entity.
5.  Draw ERD: Create the graphical representation of the entities, relationships, and attributes using the appropriate notation (e.g., Chen model or Crow's Foot).

### 4. Types of Keys:

Keys are crucial for uniquely identifying records in a database table.

*   **Super Key:** Any combination of attributes that *uniquely* identifies a record in a table. It can contain redundant attributes.
    *   *Example:* `Student_ID + Student_Name`. If `Student_ID` is already unique, adding `Student_Name` makes it a super key but not a candidate key.
*   **Candidate Key:** A *minimal* super key. It's a super key with *no redundant attributes*. A table can have multiple candidate keys.
    *   *Example:* `Student_ID` or `Student_SSN` (if both are unique and minimal).
*   **Primary Key:** The candidate key that is *chosen* to be the main identifier for the table. Each table has only *one* primary key.
    *   *Example:* `Student_ID` (chosen as the primary key).
*   **Alternate Key:** The candidate keys that are *not* chosen as the primary key.
    *   *Example:* `Student_SSN` (if `Student_ID` is the primary key).
*   **Surrogate Key:** An *artificial* key that is added to a table when there is no natural key (no existing attribute or combination of attributes that can uniquely identify a record). Surrogate keys are often auto-incrementing integers.
    *   *Example:* An auto-incremented `ID` column in a table where no other attribute is guaranteed to be unique.

### 5. Examples:

*   **Company Database ERD:**
    *   `DEPARTMENT` attributes: `Name`, `DNumber`, `Locations`, `ManagerID`, `ManagerStartDate`.
    *   `EMPLOYEE` attributes: `CNIC (key)`, `Name`, `Address`, `Salary`, `WorksOn (multivalued)`. *Note:* `WorksOn` is a multi-valued attribute, which would typically be handled by creating a separate table (the bridge table for the M:N relationship between `EMPLOYEE` and `PROJECT`).
    *   `Weak entity DEPENDENT linked to EMPLOYEE via EmpID`. This indicates that the `DEPENDENT` entity is existence-dependent on the `EMPLOYEE` entity, and it uses the `EmpID` (likely the primary key of `EMPLOYEE`) as a foreign key.

## Week 5: Exam-Style Question Answers

1.  **Explain the difference between mandatory and optional cardinality (participation constraints). Give examples of each.**

    *   *Mandatory Cardinality (Total Participation):* An entity *must* participate in the relationship.
        *   *Example:* `Every order must have a customer`.
    *   *Optional Cardinality (Partial Participation):* An entity *may or may not* participate in the relationship.
        *   *Example:* `Not all employees have dependents`.

2.  **Describe the steps involved in creating an ER diagram.**

    1.  Entity Identification: Identify the main objects or concepts.
    2.  Relationship Identification: Determine how the entities are related.
    3.  Cardinality Identification: Determine the cardinality constraints (1:1, 1:M, M:N).
    4.  Attribute Identification: Determine the attributes of each entity.
    5.  Draw ERD: Create the graphical representation.

3.  **Explain the different types of keys (super key, candidate key, primary key, alternate key, surrogate key). Give an example of each.**

    *   *Super Key:* Any combination of attributes that uniquely identifies a record.
        *   *Example:* `StudentID + Name`
    *   *Candidate Key:* A minimal super key (no redundant attributes).
        *   *Example:* `StudentID`
    *   *Primary Key:* The chosen candidate key.
        *   *Example:* `StudentID`
    *   *Alternate Key:* Candidate keys not chosen as the primary key.
        *   *Example:* `SSN` (if `StudentID` is the primary key)
    *   *Surrogate Key:* An artificial key added when there is no natural key.
        *   *Example:* An auto-incrementing `ID` column.

4.  **Consider the Company Database ERD example. Draw the ER diagram, including entities, attributes, relationships, cardinalities, and participation constraints (using Crow's Foot notation).**

    (Again, I cannot draw the diagram, but I can describe it):

    *   Entities:
        *   DEPARTMENT (DNumber, Name, Locations, ManagerID, ManagerStartDate)
        *   EMPLOYEE (SSN, Name, Address, Salary, DNO)
        *   PROJECT (PNumber, Name, Location, DNO)
        *   DEPENDENT (ESSN, DependentName, Relationship)
    *   Relationships:
        *   DEPARTMENT controls PROJECT: 1:M (One department controls multiple projects). Total participation of PROJECT (every project must be controlled by a department).
        *   EMPLOYEE works on PROJECT: M:N (Employees work on projects). A bridge table WORKS_ON (ESSN, PNO, Hours) is needed. Total participation of WORKS_ON with both EMPLOYEE and PROJECT.
        *   EMPLOYEE has DEPENDENT: 1:M (One employee has multiple dependents). Total participation of DEPENDENT (every dependent must belong to an employee).
        *   EMPLOYEE supervises EMPLOYEE: 1:M (One employee supervises other employees). Partial participation on both sides.

5.  **Why is it necessary to create a bridge table for many-to-many relationships? How does the bridge table work?**

    *   *Necessity:* Relational databases cannot directly represent M:N relationships.
    *   *How it works:* The bridge table contains the primary keys of both entities involved in the relationship as foreign keys. Each row in the bridge table represents a specific instance of the relationship between the two entities.

6.  **When would you use a surrogate key? Why?**

    *   *When:* When there is no natural key (no existing attribute or combination of attributes that can uniquely identify a record).
    *   *Why:* To ensure that every table has a primary key, which is essential for data integrity and relationship management.

7.  **In the Company Database example, the `WorksOn` attribute of the `EMPLOYEE` entity is multivalued. How would you handle this in a relational database design?**

    The `WorksOn` attribute is multivalued, indicating that an employee can work on multiple projects. In a relational database, you would handle this by creating a separate table called `WORKS_ON` (ESSN, PNO, Hours). This table would contain the primary key of the `EMPLOYEE` table (ESSN) and the primary key of the `PROJECT` table (PNO) as foreign keys, along with any additional attributes specific to the relationship (e.g., Hours). This creates a bridge table for the M:N relationship between EMPLOYEE and PROJECT.

## Week 06 - Enhanced ERD (EER Model) - Enhanced Notes

### 1. Enhanced ERD (EER Model): Concepts

The EER model extends the basic ER model with more advanced concepts to represent complex data relationships.

*   **Superclass/Subclass:** A hierarchical relationship where a *superclass* (also called a *parent class*) represents a general entity type, and *subclasses* (also called *child classes*) represent more specialized entity types.
    *   *Example:* `Student (superclass) → Undergraduate, Graduate (subclasses)`. All students share common attributes, but undergraduate and graduate students have additional, specific attributes.
*   **Inheritance:** Subclasses *inherit* all attributes and relationships from their superclasses. This promotes code reuse and data consistency.
    *   *Example:* `GraduateStudent inherits StudentID, Name, DOB from Student`. A `GraduateStudent` automatically has all the attributes of a `Student`.
*   **Specialization/Generalization:** These are two ways to view the superclass/subclass relationship:
    *   **Specialization (Top-down):** Starting with a *general* entity type (superclass) and defining more *specific* entity types (subclasses).
        *   *Example:* `Student → Undergraduate, Graduate`. You start with the general concept of a `Student` and then specialize it into `Undergraduate` and `Graduate` students.
    *   **Generalization (Bottom-up):** Starting with *specific* entity types and generalizing them into a more *general* entity type (superclass).
        *   *Example:* `Professor + Lecturer → FacultyMember`. You start with the specific concepts of `Professor` and `Lecturer` and then generalize them into the more general concept of a `FacultyMember`.
*   **Union Types (Categories):** A union type (or category) represents a single superclass/subclass relationship with *more than one superclass*. It groups *unrelated* entities into a single entity.
    *   *Example:* `Person can be a Student or Employee`. A `Person` can be *either* a `Student` *or* an `Employee`, but *not necessarily both*. This is different from a regular superclass/subclass relationship where a subclass *is a kind of* superclass.

### 2. Constraints

*   **Total vs. Partial Participation:** (As before)
    *   **Total:** Every entity in the subclass *must* be related to an entity in the superclass.
        *   *Example:* `Every GraduateStudent must have an Advisor`. Total participation of `GraduateStudent` in the "has advisor" relationship.
    *   **Partial:** An entity in the subclass *may or may not* be related to an entity in the superclass.
        *   *Example:* `Not all FacultyMembers are Professors`. Partial participation of `FacultyMember` in the "is a professor" relationship.
*   **Disjoint vs. Overlapping:** These constraints apply to subclasses of a superclass.
    *   **Disjoint:** An entity can belong to *only one* subclass.
        *   *Example:* `Vehicle is either Car or Truck`. A vehicle cannot be both a car and a truck at the same time.
    *   **Overlapping:** An entity can belong to *multiple* subclasses.
        *   *Example:* `Employee can be Manager and Mentor`. An employee can be both a manager and a mentor.

### 3. Case Study (University Database)

*   **Entities:**
    *   `Student (Superclass)`: `StudentID`, `Name`, `DOB`.
    *   `Subclasses`:
        *   `Undergraduate`: `Major`, `Minor`.
        *   `Graduate`: `ThesisTitle`, `Advisor`.
    *   `FacultyMember (Superclass)`: `FacultyID`, `Name`, `Department`.
    *   `Subclasses`:
        *   `Professor`: `ResearchSpecialization`.
        *   `Lecturer`: `CoursesTaught`.

### 4. Mapping ERD/EER to Relational Tables

This section describes how to translate an ERD or EER diagram into a relational database schema (tables and columns).

*   **Regular Entities:** Create a table for each regular entity. The attributes of the entity become the columns of the table. Choose a primary key.
    *   *Example:* `EMPLOYEE(SSN, Name, ...)`
*   **Weak Entities:** Create a table for the weak entity. Include the primary key of the owner entity as a foreign key in the weak entity's table.
    *   *Example:* `DEPENDENT(EmpID, DependentName, ...)` where `EmpID` is a foreign key referencing the `EMPLOYEE` table.
*   **1:1 Relationships:** Add the primary key of one entity as a foreign key in the table representing the entity with total participation. If participation is partial on both sides, you can choose either table.
*   **1:N Relationships:** Add the primary key of the entity on the "one" side as a foreign key in the table representing the entity on the "many" side.
    *   *Example:* `EMPLOYEE(DNO, ...)` where `DNO` is a foreign key referencing the `DEPARTMENT` table.
*   **M:N Relationships:** Create a junction table (also called a bridge table or associative entity). The junction table contains the primary keys of both entities as foreign keys.
    *   *Example:* `WORKS_ON(ESSN, PNO, Hours)` where `ESSN` is a foreign key referencing `EMPLOYEE` and `PNO` is a foreign key referencing `PROJECT`.
*   **Multivalued Attributes:** Create a separate table for the multivalued attribute. The table contains the primary key of the original entity and a column for the multivalued attribute.
    *   *Example:* `DEPT_LOCATIONS(DNUMBER, DLOCATION)` where `DNUMBER` is a foreign key referencing the `DEPARTMENT` table.

### 5. Example: Ternary Relationship (SUPPLY)

*   `SUPPLY(SNAME, PARTNO, PROJNAME)`. This table represents a ternary relationship between Supplier (SNAME), Part (PARTNO), and Project (PROJNAME). Each column would be a foreign key referencing the respective table.

### 6. Summary of ER-to-Relational Mapping

| ER Model             | Relational Model              |
| -------------------- | ----------------------------- |
| Entity Type          | Table                         |
| 1:1/1:N Relationship | Foreign Key                   |
| M:N Relationship     | Junction Table + Foreign Keys |
| Multivalued Attribute | Separate Table                |

## Week 6: Exam-Style Question Answers

1.  **Explain the concepts of superclass and subclass in the EER model. Give an example.**

    *   *Superclass:* A general entity type (also called a parent class).
    *   *Subclass:* A more specialized entity type (also called a child class) that inherits attributes and relationships from the superclass.
    *   *Example:* `Vehicle (superclass) → Car, Truck (subclasses)`

2.  **What is inheritance in the context of EER modeling?**

    Inheritance is the mechanism by which subclasses inherit all attributes and relationships from their superclasses. This promotes code reuse and data consistency.

3.  **Explain the difference between specialization and generalization.**

    *   *Specialization:* A top-down approach where you start with a general entity type (superclass) and define more specific entity types (subclasses).
    *   *Generalization:* A bottom-up approach where you start with specific entity types and generalize them into a more general entity type (superclass).

4.  **What is a union type (category)? How does it differ from a regular superclass/subclass relationship?**

    *   *Union Type (Category):* Represents a single superclass/subclass relationship with *more than one superclass*. It groups *unrelated* entities into a single entity.
    *   *Difference:* In a regular superclass/subclass relationship, a subclass *is a kind of* superclass. In a union type, an entity can be *either* one superclass *or* another, but not necessarily both.

5.  **Explain the difference between disjoint and overlapping constraints on subclasses. Give examples.**

    *   *Disjoint:* An entity can belong to *only one* subclass.
        *   *Example:* `Vehicle is either Car or Truck`.
    *   *Overlapping:* An entity can belong to *multiple* subclasses.
        *   *Example:* `Employee can be Manager and Mentor`.

6.  **Consider the University Database case study. Draw the EER diagram, including entities, attributes, relationships, cardinalities, participation constraints, and disjoint/overlapping constraints.**

    (Again, I cannot draw the diagram, but I can describe it):

    *   Entities:
        *   Student (Superclass): StudentID, Name, DOB
        *   Undergraduate (Subclass): Major, Minor
        *   Graduate (Subclass): ThesisTitle, Advisor
        *   FacultyMember (Superclass): FacultyID, Name, Department
        *   Professor (Subclass): ResearchSpecialization
        *   Lecturer (Subclass): CoursesTaught
    *   Relationships:
        *   Inheritance: Undergraduate and Graduate inherit from Student. Professor and Lecturer inherit from FacultyMember.
    *   Constraints:
        *   Total participation of Undergraduate and Graduate in the Student superclass.
        *   Total participation of Professor and Lecturer in the FacultyMember superclass.
        *   Disjoint constraint between Undergraduate and Graduate (a student is either an undergraduate or a graduate).
        *   Overlapping constraint between Professor and Lecturer is possible (a faculty member can be both a professor and a lecturer, although it might be unusual).

7.  **Describe the steps involved in mapping an ERD/EER diagram to a relational database schema.**

    1.  Regular Entities: Create a table for each regular entity.
    2.  Weak Entities: Create a table for the weak entity and include the primary key of the owner entity as a foreign key.
    3.  1:1 Relationships: Add the primary key of one entity as a foreign key in the table representing the entity with total participation.
    4.  1:N Relationships: Add the primary key of the entity on the "one" side as a foreign key in the table representing the entity on the "many" side.
    5.  M:N Relationships: Create a junction table.
    6.  Multivalued Attributes: Create a separate table.

8.  **How do you map 1:1, 1:N, and M:N relationships to relational tables?**

    *   1:1: Add the primary key of one entity as a foreign key in the table representing the entity with total participation.
    *   1:N: Add the primary key of the entity on the "one" side as a foreign key in the table representing the entity on the "many" side.
    *   M:N: Create a junction table (also called a bridge table or associative entity). The junction table contains the primary keys of both entities as foreign keys.

9.  **How do you handle multivalued attributes when mapping an ERD/EER diagram to a relational database schema?**

    Create a separate table for the multivalued attribute. The table contains the primary key of the original entity and a column for the multivalued attribute.

10. **Design a relational database schema for the University Database case study, based on your EER diagram. Specify the tables, columns, data types, primary keys, and foreign keys.**

    *   Students (StudentID INTEGER PRIMARY KEY, Name VARCHAR, DOB DATE)
    *   Undergraduates (StudentID INTEGER PRIMARY KEY, Major VARCHAR, Minor VARCHAR, FOREIGN KEY (StudentID) REFERENCES Students(StudentID))
    *   Graduates (StudentID INTEGER PRIMARY KEY, ThesisTitle VARCHAR, AdvisorID INTEGER, FOREIGN KEY (StudentID) REFERENCES Students(StudentID), FOREIGN KEY (AdvisorID) REFERENCES FacultyMembers(FacultyID))
    *   FacultyMembers (FacultyID INTEGER PRIMARY KEY, Name VARCHAR, Department VARCHAR)
    *   Professors (FacultyID INTEGER PRIMARY KEY, ResearchSpecialization VARCHAR, FOREIGN KEY (FacultyID) REFERENCES FacultyMembers(FacultyID))
    *   Lecturers (FacultyID INTEGER PRIMARY KEY, CoursesTaught VARCHAR, FOREIGN KEY (FacultyID) REFERENCES FacultyMembers(FacultyID))