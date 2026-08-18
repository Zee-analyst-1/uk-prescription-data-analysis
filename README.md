# 💊 NHS Prescription Data Analysis

A straightforward data analysis project exploring UK NHS prescribing patterns using **SQL (Supabase)** and **Tableau**.

---

## 🎯 Project Goals
The main objective is to answer four key questions regarding regional healthcare expenditure and prescription volume:
1. **Regional Spending:** Which NHS regions have the highest financial spend and item volume?
2. **Top Drug Categories:** Which British National Formulary (BNF) chapters account for the highest cost?
3. **Most Prescribed Drugs:** Which individual medications are dispensed most frequently?
4. **Unit Cost Analysis:** What is the average unit cost per prescription item?

---

## 🛠️ Tools Used
- **Supabase:** Data cleaning, type conversion, and running SQL queries.
<img width="700" height="300" alt="image" src="https://github.com/user-attachments/assets/9e5e5492-e1b2-48e9-b9b2-ba2d2bd3f80d" />
<img width="700" height="300" alt="image" src="https://github.com/user-attachments/assets/706bb949-d5a1-40d5-8648-03071f4d97a6" />
<img width="700" height="200" alt="image" src="https://github.com/user-attachments/assets/75a57118-445c-4d47-99e5-d93029b8e0df" />




- **Tableau:** Visualizing query results through interactive charts and dashboards.

[Link to my Tableau](https://public.tableau.com/app/profile/zahra.bani/vizzes)
<img width="900" height="400" alt="image" src="https://github.com/user-attachments/assets/e5b518eb-900a-41eb-b6ff-46e7da600e9f" />

---

## 🧹 Data Cleaning (SQL)
Since the cost column was originally imported as text containing special formatting characters, it was converted to a clean `numeric` data type using the following command:

```sql
ALTER TABLE prescription_analysis 
  ALTER COLUMN actual_cost_gbp 
  TYPE numeric 
  USING REGEXP_REPLACE(actual_cost_gbp::text, '[^0-9.]', '', 'g')::numeric;

