# Movie Rental System Database Administration

## Project Overview

This project is focused on establishing and maintaining a robust and highly available database system for a Movie Rental System Company. As a Database Administrator (DBA), the primary goal is to ensure 24-hour availability, daily backups, complete database recovery, and optimal performance.

## Business Requirements

### High Availability
To achieve continuous availability, a standby database will be created on the same machine.

### Database Structure
The database will be designed based on the Entity-Relationship (ER) model, incorporating necessary tables, indexes, views, and materialized views.

## The ERD model

![ERD-Movie-Rental-4.png](https://github.com/YehiaKhaledAbouzeiid/Movie-Rental-Database-System/blob/main/ERD-Movie-Rental-4.png)

### User Management
Three groups of users with distinct privileges and roles will be established. Each group will have specific password policies, failed login attempts, concurrent session limits, and assigned quotas.

- **Group 1:**
  - Password expires in 80 days
  - 3 allowed failed login attempts
  - Maximum 4 concurrent sessions
  - Suitable quotas assigned

- **Group 2:**
  - Password expires in 100 days
  - 2 allowed failed login attempts
  - Maximum 2 concurrent sessions
  - Suitable quotas assigned

- **Group 3:**
  - Password expires in 60 days
  - 3 allowed failed login attempts
  - Maximum 2 concurrent sessions
  - Suitable quotas assigned

### Storage Management
Tablespaces will be created, and the staff table will be saved in Automatic Storage Management (ASM). Expecting record sizes ranging from 300K to 900K.

### Database Configuration
- Archiving enabled
- Mirrored and distributed log files and control files
- Flash Recovery Area created
- Flashback Database enabled
- ASM with 2 Disk groups
- Automatic Memory Management
- Unicode character set

### Monitoring and Metrics
- Define the table space full metric threshold for warning (50%) and critical (60%)
- Mandatory audit specified

### Backup and Recovery
- Compressed backup set
- Maximum backup piece set to 150MB
- Auto backup enabled
- Exclude example tablespace
- Retention policy set to 15 days
- Recovery catalog created

### Backup Strategy
- Backup database plus archivelog as a copy
- Export table "customer" to a dump file

### Performance Optimization
- Database work in the best performance
- Backup scripts and strategies to ensure data integrity and recovery readiness

## Database Creation Scripts

For your convenience, the project includes scripts to:
- Generate database creation scripts
- Generate database template
- Create a failure group in ASM

## Reports

Twelve suggested reports to monitor and analyze the database's health and performance have been provided. These reports cover aspects like user activity, resource utilization, and overall system performance.

1. Query for the Most 3 Rented Films
2. Query for the Top 3 Actors in Films
3. The films that have not returned yet
4. Top 1 employee
5. Monthly report of the payment amount
6. The most rental in a store
7. The most Active customer
8. Top-Rented Films by Category
9. Staff Performance Report
10. Customer Activity Over Time
11. Store Comparison Report
12. Film Rating Analysis


