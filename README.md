```
# Celestial Bodies Database (PostgreSQL)

## Project Overview

This project implements a relational PostgreSQL database named **`universe`** that models celestial bodies and their hierarchical relationships. It satisfies all freeCodeCamp **Celestial Bodies Database** project requirements using normalized tables, strict constraints, and valid relational integrity.

The database is built entirely through the PostgreSQL terminal (`psql`) and demonstrates competency in database design, SQL DDL, constraints, and data modeling.

---

## Database Structure

### Tables

The database contains **five tables**:

1. **galaxy**
2. **star**
3. **planet**
4. **moon**
5. **asteroid**

Each table:

* Uses an auto-incrementing primary key (`SERIAL`)
* Has a `name` column of type `VARCHAR`
* Enforces `NOT NULL` and `UNIQUE` constraints
* Contains at least five columns (for required tables)
* Includes multiple data types (`INT`, `NUMERIC`, `TEXT`, `BOOLEAN`)

---

## Table Relationships

* **galaxy → star**

  * `star.galaxy_id` references `galaxy.galaxy_id`
* **star → planet**

  * `planet.star_id` references `star.star_id`
* **planet → moon**

  * `moon.planet_id` references `planet.planet_id`

All foreign keys follow the required naming convention and enforce referential integrity.

---

## Data Types Used

| Data Type | Usage                                   |
| --------- | --------------------------------------- |
| `INT`     | Ages, radii, sizes, temperatures        |
| `NUMERIC` | Masses and orbital distances            |
| `TEXT`    | Descriptions                            |
| `BOOLEAN` | Life presence, spherical shape, hazards |
| `VARCHAR` | Names and classifications               |

---

## Row Counts (Requirement Compliance)

| Table    | Rows |
| -------- | ---- |
| galaxy   | 6    |
| star     | 6    |
| planet   | 12   |
| moon     | 20   |
| asteroid | 3    |

All minimum row requirements are met or exceeded.

---

## Constraints Implemented

* Primary keys on all tables
* Auto-incrementing IDs
* `NOT NULL` constraints (minimum two per table)
* `UNIQUE` constraints on `name` columns
* Foreign key constraints enforcing hierarchy
* Required column naming conventions followed

---

## Setup Instructions

### 1. Log into PostgreSQL

```bash
psql --username=freecodecamp --dbname=postgres
``

### 2. Create and Connect to the Database

```sql
CREATE DATABASE universe;
\c universe
``

### 3. Run SQL Script

Execute the provided SQL file to create tables and insert data.

---

## Backup and Restore

### Create a Dump

```bash
pg_dump -cC --inserts -U freecodecamp universe > universe.sql
``

### Restore from Dump

```bash
psql -U postgres < universe.sql
``

---

## Project Purpose

This project demonstrates:

* Relational database design
* SQL constraint enforcement
* One-to-many relationships
* PostgreSQL command-line proficiency
* Compliance with structured technical specifications

---

## Status

All freeCodeCamp tests pass.
Database is fully functional and normalized.
