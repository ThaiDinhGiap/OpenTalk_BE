# Manage Opentalk Website

## Introduction
Manage Opentalk Web is a system for managing Opentalk sessions within the company, enabling administrators and employees to easily register, manage, and track Opentalk events.

## Main Features
### 1. Employee Management
- CRUD employees.
- Sync employee data from an external HRM system via REST API using WebClient.

### 2. Authentication
- Login/Logout (Spring Security with JWT - Generate, Validate, Refresh Token).
  
### 3. Opentalk Management
- Register for Opentalk.
- Manage Opentalk schedule.
- Upload slides for Opentalk sessions.
- Opentalk lottery: If the schedule is empty, the system can randomly select employees who have not hosted within the year.
- Dynamic Cronjob Configuration for Opentalk Lottery Scheduling
  
## Roles and Permissions
### 1. Admin
- Add/Edit/Delete employee information (sync data from HRM).
- Add/Edit/Delete company branches.
- Retrieve employee list with filters:
  - Status (Enabled/Disabled).
  - Company branch.
  - Employee name.
- Add/Edit/Delete Opentalk topics.
- Manage Opentalk lists:
  - Past Opentalk sessions (Pagination, filters by employee status, company branch, employee name, date range).
  - Upcoming Opentalk sessions (Pagination, filters by date range, company branch, employee name).
  - Opentalk sessions for a specific employee ID (Pagination, filters by date range).
  - Employees who have not registered for Opentalk (Pagination, filters by employee status, date range, company branch, employee name).

### 2. Employee
- View registered Opentalk sessions (Pagination, sorted by registration date descending).
- View past Opentalk sessions (Pagination, filters by employee status, company branch, employee name, date range).
- Register for Opentalk.

## 3. Technologies Used
- **Backend**: Java Spring Boot
- **Database**: MySQL, Redis

## 4. Key Concepts Applied
### 4.1 Spring Core
- Spring Profile & Configuration: Using multiple configuration files (dev, alpha, beta, stg, prod), fetching values dynamically.
- Bean Scopes & Life Cycle: Managing different bean scopes and understanding the Spring bean lifecycle.
### 4.2 Database & ORM
- Defining relationships, Cascade types, and Fetch Types
- Using Mapstruct and Mapper for efficient mapping between DTO and Entity
### 4.3 Email & Internationalization
- Email Service: Sending emails with Thymeleaf templates.
- Spring Events & @Async: Asynchronous event handling and background processing.
- Multilanguage Support: Configuring internationalization in the application.
### 4.4 Repository & Query Optimization
- Automatic Custom Queries.
- Manual Custom Queries (JPQL, Native Query).
- Customizing results using Class Constructors and Spring Data Projection.
- Sorting & Pagination with JPQL and native queries, comparison with Slice.
- Implementing query caching.
### 4.5 Testing
- Implementing Unit & Integration Testing.
