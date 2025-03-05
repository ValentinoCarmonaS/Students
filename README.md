# STUDENT DATABASE PROJECT

This project involves creating and querying a PostgreSQL database to manage student information, academic majors, and courses. Part 1 focuses on database design and data insertion, while Part 2 adds advanced querying and reporting capabilities.

---

## PART 1: DATABASE CREATION & DATA INSERTION

1. **Database Setup**:
   - Created a students database with four normalized tables:
     - students: Student IDs, names, GPA, and major links.
     - majors: Unique academic majors.
     - courses: Available courses.
     - majors_courses: Maps many-to-many relationships between majors and courses.
   - Implemented constraints: `PRIMARY KEY`, `FOREIGN KEY`, `NOT NULL`, and composite keys.

2. **Automated Data Insertion**:
   - Developed a Bash script (`insert_data.sh`) to parse and insert data from `students.csv` and `courses.csv`.
   - Handled CSV headers, avoided duplicates, and resolved dependencies (e.g., inserting majors/courses before linking them).
   - Used `TRUNCATE` to reset tables during testing while managing foreign key constraints.

3. **Data Integrity**:
   - Ensured dynamic linking of majors and courses via foreign keys.
   - Handled `NULL` values for students without declared majors.

---

## PART 2: ADVANCED QUERYING & REPORTING

1. **Script for Student Insights**:
   - Created `student_info.sh` to generate reports on student performance and course details.
   - Key features:
     - Filter students by GPA ranges, name patterns, or major enrollment status.
     - List courses alphabetically, filter by naming patterns, or enrollment counts.
     - Calculate aggregate statistics (e.g., average GPA, student counts per major).

2. **Advanced SQL Techniques**:
   - **Joins**: Used `FULL JOIN`, `LEFT JOIN`, and `INNER JOIN` to link tables for complex queries.
   - **Pattern Matching**: Leveraged `LIKE`, `ILIKE`, and wildcards (`%`, `_`) for text searches.
   - **Aggregate Functions**: `COUNT`, `AVG`, `MIN`, `MAX`, and `ROUND` for statistical analysis.
   - **Grouping & Filtering**: Combined `GROUP BY` with `HAVING` to refine results.

3. **Key Queries**:
   - Students with GPAs ≥ 4.0 or specific name patterns.
   - Courses starting/ending with letters or containing case-insensitive substrings.
   - Majors with no enrolled students or those linked to specific student criteria.
   - Ordered results using `ORDER BY` and limited outputs with `LIMIT`.

---

## TECHNICAL CHALLENGES
- **Part 1**:
  - Avoiding data duplication during CSV insertion.
  - Managing foreign key dependencies across tables.
- **Part 2**:
  - Optimizing query performance for large datasets.
  - Combining multiple conditions (e.g., `AND`/`OR` with `LIKE`, `IS NULL`).

## SKILLS DEMONSTRATED
- **Database Design**: Normalized schema, constraints, and relationships.
- **Bash Scripting**: Automated data insertion and report generation.
- **Advanced SQL**: Joins, pattern matching, aggregate functions, and query optimization.
- **Data Analysis**: Extracting insights via structured queries.

---

## HOW TO USE
1. **Rebuild Database**:
   ```bash
   psql -U postgres < students.sql
   ```

2. **Insert Data (Part 1)**:
   ```bash
   chmod +x insert_data.sh
   ./insert_data.sh
   ```

3. **Generate Reports (Part 2)**:
   ```bash
   chmod +x student_info.sh
   ./student_info.sh
   ```

## TOOLS & TECHNOLOGIES
- **PostgreSQL**: Database management and querying.
- **Bash**: Scripting for automation.
- **CSV Files**: Raw data storage.

A project completed as part of the freeCodeCamp.org Relational Database Certification.
