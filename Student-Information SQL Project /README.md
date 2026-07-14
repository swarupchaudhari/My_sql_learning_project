# 🎓 Student Information Management — SQL Analytics Project

A relational database project built in **MySQL** that models an ed-tech platform:
students, courses, enrollments, and payments. It includes **50+ SQL queries**
ranging from basic filtering to intermediate joins/aggregations and advanced
window functions — designed to demonstrate real-world data analysis skills.

---

## 📌 Project Overview

This project simulates the backend database of an online learning platform
(similar to Coursera/Udemy). It answers practical business questions such as:

- Which courses generate the most revenue?
- Which students are the highest spenders?
- What's the completion vs. drop-off rate per course?
- How does enrollment trend month over month?

---

## 🗃️ Database Schema

**Database:** `student_information`

| Table | Description | Key Columns |
|---|---|---|
| `students` | Student master data | `student_id` (PK), `full_name`, `city`, `age`, `registration_date` |
| `courses` | Course catalog | `course_id` (PK), `course_name`, `category`, `price` |
| `enrollments` | Links students to courses | `enrollment_id` (PK), `student_id` (FK), `course_id` (FK), `status` |
| `payments` | Payment transactions per enrollment | `payment_id` (PK), `enrollment_id` (FK), `amount`, `payment_mode` |

### Entity Relationship

```
students (1) ───< enrollments >─── (1) courses
                       │
                       │ (1)
                       ▼
                    payments
```

- One student can have **many** enrollments (one-to-many).
- One course can have **many** enrollments (one-to-many).
- Each enrollment has **one** corresponding payment (one-to-one).

**Sample size:** 30 students · 10 courses · 30 enrollments · 30 payments.

---

## 🛠️ Tech Stack

- **Database:** MySQL 8.0+
- **Concepts used:** DDL (`CREATE TABLE`), DML (`INSERT`), joins (`INNER`/`LEFT`),
  aggregate functions (`SUM`, `AVG`, `COUNT`, `MIN`, `MAX`), `GROUP BY` / `HAVING`,
  date filtering, and **window functions** (`RANK() OVER`).

---

## 📊 Query Breakdown (50 Queries)

### 🟢 Basic (Q1–15)
Filtering, sorting, `DISTINCT`, `COUNT`, date range filters, and simple
aggregates — e.g. students from a specific city, courses above a price
threshold, min/max/avg course price.

### 🟡 Intermediate (Q16–35)
Multi-table `JOIN`s, `GROUP BY` with `HAVING`, revenue-per-course,
monthly revenue trends, students with zero enrollments (`LEFT JOIN`),
and average student age per city.

### 🔴 Advanced (Q36–50)
Window functions for ranking courses/students by revenue,
`RANK() OVER (ORDER BY ...)`, students who completed 100% of their
courses, courses with zero drop-offs, and high-value customer segmentation
(spent > ₹10,000).

---

## 🚀 How to Run

1. Install MySQL (or use MySQL Workbench / phpMyAdmin / DBeaver).
2. Open a SQL client and run the script top to bottom:
   ```bash
   mysql -u root -p < student_information.sql
   ```
3. All 4 tables will be created and pre-populated with sample data.
4. Run any of the 50 queries individually to explore the analysis.

---

## 💡 Key Insights You Can Derive

- Revenue leaders among the 10 courses.
- Student segments by engagement (completed / in progress / dropped).
- Best-performing cities by student count and average age.
- Payment mode preferences (UPI vs. Card vs. Net Banking).

---

## 📈 Possible Extensions

- Connect to **Power BI / Tableau** for a live dashboard.
- Add a `instructors` table and course ratings.
- Convert queries into **stored procedures** or a **Python (SQLAlchemy)** API layer.
- Add indexing and query performance analysis (`EXPLAIN`).

---

## 👤 Author

Built as a hands-on SQL practice project covering the full spectrum of
querying — from beginner fundamentals to advanced analytics used in
real data-analyst interviews.

---

## 📄 License

This project is open for learning purposes — feel free to fork, adapt, and extend it.
