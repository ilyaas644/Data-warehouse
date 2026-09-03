# Project 3: The Data Warehouse

## Overview
This project demonstrates provisioning a managed cloud database using AWS RDS for an e-commerce startup that needed to move from Excel sheets to a scalable database solution.

## AWS Services Used
- Amazon RDS (MySQL)
- Amazon EC2 (Bastion Host)
- Security Groups
- SSH Tunneling


ARCHITECT Diagram

## Database Details
- **Database Name:** interns_db
- **Table Name:** Interns
- **Engine:** MySQL 8.0

## Table Schema
Interns
├── InternID INT (PRIMARY KEY)
├── FirstName VARCHAR(50) (NOT NULL)
├── LastName VARCHAR(50) (NOT NULL)
└── Email VARCHAR(100) (UNIQUE, NOT NULL)

## Sample Data
| InternID | FirstName | LastName | Email |
|----------|-----------|----------|-------|
| 1 | John | Doe | jdoe@decodelabs.com |
| 2 | Jane | Smith | jsmith@decodelabs.com |
| 3 | Conan | O'Leary | coleary@decodelabs.com |
| 4 | Maria | Garcia | mgarcia@decodelabs.com |
| 5 | Alex | Chen | achen@decodelabs.com |

## SQL Commands Used
```sql
-- Create database
CREATE DATABASE interns_db;

-- Switch to database
USE interns_db;

-- Create table
CREATE TABLE Interns (
    InternID INT PRIMARY KEY,
    FirstName VARCHAR(50) NOT NULL,
    LastName VARCHAR(50) NOT NULL,
    Email VARCHAR(100) UNIQUE NOT NULL
);

-- Insert data
INSERT INTO Interns (InternID, FirstName, LastName, Email)
VALUES 
    (1, 'John', 'Doe', 'jdoe@decodelabs.com'),
    (2, 'Jane', 'Smith', 'jsmith@decodelabs.com'),
    (3, 'Conan', "O'Leary", 'coleary@decodelabs.com'),
    (4, 'Maria', 'Garcia', 'mgarcia@decodelabs.com'),
    (5, 'Alex', 'Chen', 'achen@decodelabs.com');

-- Query data
SELECT * FROM Interns;
+----------+-----------+----------+------------------------+
| InternID | FirstName | LastName | Email                  |
+----------+-----------+----------+------------------------+
|        1 | John      | Doe      | jdoe@decodelabs.com    |
|        2 | Jane      | Smith    | jsmith@decodelabs.com  |
|        3 | Conan     | O'Leary  | coleary@decodelabs.com |
|        4 | Maria     | Garcia   | mgarcia@decodelabs.com |
|        5 | Alex      | Chen     | achen@decodelabs.com   |
+----------+-----------+----------+------------------------+
5 rows in set (0.00 sec)

