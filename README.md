
# 📊 Student Performance Analysis (SQL & PostgreSQL)

## 🚀 Overview

This project explores factors affecting student performance using **PostgreSQL and SQL**.
It focuses on analyzing how variables such as study hours, attendance, sleep, and extracurricular activities influence exam scores.

The project demonstrates practical use of:

* SQL data exploration
* Aggregations and grouping
* Window functions
* Feature engineering techniques

---

## 🛠️ Tech Stack

* PostgreSQL
* SQL (Advanced queries)
* Jupyter Notebook (ipython-sql)

---

## 📂 Dataset

The dataset contains information about students, including:

* `hours_studied`
* `attendance`
* `sleep_hours`
* `tutoring_sessions`
* `extracurricular_activities`
* `exam_score`

---

## 🔍 Key Analyses

### 1. 📈 Study Hours vs Exam Performance

Analyzed how study time impacts exam scores using aggregation:

```sql
SELECT hours_studied, AVG(exam_score)
FROM student_performance
GROUP BY hours_studied;
```

---

### 2. 🧠 Feature Engineering (Binning)

Grouped study hours into categories:

```sql
CASE
  WHEN hours_studied BETWEEN 1 AND 5 THEN '1-5 hours'
  WHEN hours_studied BETWEEN 6 AND 10 THEN '6-10 hours'
  WHEN hours_studied BETWEEN 11 AND 15 THEN '11-15 hours'
  ELSE '16+ hours'
END
```

---

### 3. 🏆 Ranking Students (Window Functions)

Used `DENSE_RANK()` to rank students by exam performance:

```sql
DENSE_RANK() OVER (ORDER BY exam_score DESC)
```

---

## 📊 Insights

* Students studying more hours tend to achieve higher exam scores
* Extracurricular activities combined with study improve performance
* Categorizing study hours provides clearer analytical insights
* Top-performing students can be identified using ranking functions

---

## ▶️ How to Run

1. Start PostgreSQL
2. Connect using Jupyter:

```python
%load_ext sql
%sql postgresql://postgres:YOUR_PASSWORD@localhost/Student_Performance
```

3. Run SQL queries using:

```sql
%%sql
SELECT * FROM student_performance;
```

---

## 📌 Project Structure

```
.
├── data/
│   └── student_performance.csv
├── images/
│   ├── exam_result.jpeg
│   └── examB.png
├── student_performance_analysis.ipynb
└── README.md
```

---

## 🎯 Key Skills Demonstrated

* Data analysis with SQL
* PostgreSQL database usage
* Aggregation & grouping
* Window functions (DENSE_RANK)
* Feature engineering (binning)

---

## 📎 Future Improvements

* Data visualization (Matplotlib / Seaborn)
* Machine learning models
* Dashboard integration (Power BI / Tableau)

---

## 📬 Contact

Feel free to connect or give feedback!
