# 📊 Cohort Analysis Using SQL and Python

## 📌 Overview
This project demonstrates how to perform a **cohort analysis** on a fictional e-commerce dataset using a combination of **SQL** and **Python**. The goal was to explore customer sign-up behavior, track retention over time, and analyze purchasing patterns across different cohorts.  
The project combines **SQL for data extraction** from a SQLite database and **Python (Pandas, Seaborn, Matplotlib)** for data cleaning, transformation, and visualization.

---

## 🎯 Business Objective
The objective of this analysis is to:
- Identify customer retention trends across cohorts.
- Understand when user drop-off occurs and which cohorts are most engaged.
- Provide actionable insights to improve customer lifetime value through targeted strategies.

---

## 🧠 What is Cohort Analysis?
Cohort analysis groups customers by shared characteristics (e.g., month of signup) and tracks their behavior over time. This method is commonly used in:
- **E-commerce**: Measure customer retention and lifetime value.
- **SaaS**: Monitor subscriber engagement and churn.
- **Healthcare**: Track treatment adherence over time.
- **Finance**: Follow client activity post-onboarding.

---

## 🛠 Tools and Technologies
- **Database:** SQLite (`cohort_analysis.db`)
- **Language:** Python 3
- **Libraries:**
  - `SQLAlchemy` – database connection
  - `Pandas` – data manipulation
  - `Matplotlib` / `Seaborn` – data visualization
- **Environment:** Google Colab

---

## 📂 Dataset
Two tables are stored in a SQLite database:
1. **`customers`**
   - `customer_id`
   - `sign_up_date`
   - `location`
2. **`purchases`**
   - `purchase_id`
   - `customer_id`
   - `purchase_date`
   - `total_amount`

---

## 📋 Steps Performed

1. **Connect to Database & Explore Data**
   - Used SQLAlchemy to connect to the SQLite database and inspect available tables.
   - Previewed `customers` and `purchases` tables.

2. **Retrieve Data with SQL**
   ```sql
   SELECT 
     c.customer_id,
     c.sign_up_date,
     c.location,
     p.purchase_date,
     p.total_amount
   FROM customers c
   JOIN purchases p ON c.customer_id = p.customer_id;
   ```

3. **Preprocess Data in Python**
   - Converted date fields to datetime format.
   - Created `cohort_month` and `purchase_month`.
   - Calculated `cohort_index` (months since signup).

4. **Build Retention Matrix**
   - Removed duplicate customer-month records.
   - Counted active customers per cohort per month.
   - Normalized counts to calculate retention rates.

5. **Visualize Cohort Retention**
   - Created a heatmap showing retention over time.

---

## 📊 Key Insights
- Retention is highest in the **first and second months** after signup.
- Some cohorts (e.g., February 2024, March 2024) retained strong engagement into the third month.
- Drop-off occurs between months 2–4 for most cohorts.
- The April 2024 cohort had perfect first-month retention but insufficient long-term data.

---

## 💡 Business Recommendations
- **Enhance onboarding** to keep customers engaged beyond the first month.
- **Target retention campaigns** (email, promotions) around months 2–3.
- **Replicate success** from high-retention cohorts to other acquisition months.

---

---

## 📎 Files in This Project
- `Cohort_Analysis.ipynb` – Jupyter/Colab notebook with SQL, Python code, and analysis.
- `Cohort_Analysis.pdf` – Clean PDF export of the notebook.
- `README.md` – Project description and instructions.

---

## 🚀 How to Run This Project
1. Clone the repository:
   ```bash
   git clone https://github.com/bilp9/Cohort-Analysis.git
   ```
2. Open the notebook in Jupyter or Google Colab.
3. Upload the `cohort_analysis.db` file to your environment.
4. Run all cells to reproduce the analysis.

---

## 📬 Contact
**Author:** Billy Pierre  
**GitHub:** [https://github.com/bilp9](https://github.com/bilp9)  
**LinkedIn:** [https://www.linkedin.com/feed/](https://www.linkedin.com/feed](https://www.linkedin.com/in/pierrebilly/)  
