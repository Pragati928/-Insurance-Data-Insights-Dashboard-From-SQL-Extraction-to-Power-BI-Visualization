# 📊 Insurance-Data-Insights-Dashboard-From-SQL-Extraction-to-Power-BI-Visualization

An end-to-end Insurance Data Analysis project using SQL for data extraction &amp; Power BI for interactive insights and visualization.

![KPI Cards](https://github.com/user-attachments/assets/a2daae2e-8478-45ee-ba90-dd337dda00c8)

![KPI Cards](https://github.com/user-attachments/assets/09e7e711-e844-4455-bcd6-ebc6c1fccf57)



### 🔗 Dashboard Link: *(https://app.powerbi.com/view?r=eyJrIjoiNjA4MjU0NzAtY2U5NC00OGMzLWI5YWItZjA0MmU2ZjBkMjIxIiwidCI6IjEzOWQ5NmE0LWUxMzktNDZkMy05MDkwLTU0ZDMxNTBlM2NhMiJ9)*  

---

## 📝 Problem Statement  

This dashboard provides a **comprehensive analysis** of insurance policies, claims, customer demographics, and feedback sentiment.  
It enables insurance companies to:  

- 📌 Monitor **total premiums, coverage, and claim amounts**.  
- 📌 Analyze **claim statuses** (Settled, Pending, Rejected).  
- 📌 Track **performance by policy type and age group**.  
- 📌 Understand **active vs inactive policy distribution**.  
- 📌 Perform **sentiment analysis** on customer feedback for service improvement.  

---

## ⚙️ Steps Followed  

### **Step 1 – Data Extraction (SQL)** 🗄  
- Connected to the **Insurance Claims Database** using SQL Server.  
- Extracted relevant datasets (`Policies`, `Claims`, `Customers`).  
- Used SQL to:  
  - **Join** related tables for a unified dataset.  
  - **Filter** for relevant time periods and active policies.  
  - **Aggregate** premiums, coverage, and claim amounts by policy type and age group.  
  - **Clean** data by removing duplicates, handling nulls, and standardizing values.  

💡 *Example SQL Query:*  
```sql
SELECT 
    c.CustomerID,
    c.Name,
    c.Age,
    c.Gender,
    p.PolicyNumber,
    p.PolicyType,
    p.PremiumAmount,
    p.CoverageAmount,
    cl.ClaimNumber,
    cl.ClaimAmount,
    cl.ClaimStatus
FROM Customers c
JOIN Policies p ON c.CustomerID = p.CustomerID
LEFT JOIN Claims cl ON p.PolicyNumber = cl.PolicyNumber
WHERE p.PolicyStatus = 'Active';

```

---


### **Step 2 – Data Loading in Power BI** 📥  
- Imported the **cleaned SQL dataset** into **Power BI Desktop** using **DirectQuery** for live connection to the database.  
- Ensured column data types (date, currency, text) were properly recognized during load.  
- Verified **row counts** between SQL output and Power BI to confirm data completeness.  

---

### **Step 3 – Data Quality Check** ✅  
- Used **Power Query** to:  
  - Check column distribution, quality, and profile.  
  - Remove null values and duplicates.  
  - Correct mismatched data types for numerical, date, and text fields.  
- Standardized currency formatting and date formats.  

---

### **Step 4 – Data Transformation** 🔄  
- Created **calculated columns** for:  
  - **Age Groups** (0–25, 25–50, 50–75, 75–100).  
  - **Policy Status** (Active/Inactive).  
- Created measures for KPIs using **DAX**:  
  - 🛡 **Total Premium Amount** = ₹5.98M  
  - 💰 **Total Coverage Amount** = ₹600.55M  
  - 📈 **Total Claim Amount** = ₹16.91M  
  - 👩 **Number of Female Policyholders** = 5,001  
  - 👨 **Number of Male Policyholders** = 5,003  

---

### **Step 5 – Visuals Created** 📊  

1. **KPI Cards** – Total Premium, Coverage, Claim Amount  
   ![KPI Cards](https://github.com/user-attachments/assets/a2c36765-ac1c-4e2f-9d6f-565217b3371f)  

2. **Bar Chart** – Number of claims by status (Rejected, Settled, Pending)  
   ![Ribbon Chart](https://github.com/user-attachments/assets/1cd8beeb-955a-4e0b-bb99-8c52ec0d501c)

4. **Area Chart** – Premium amount by policy type (Travel, Health, Auto, Life, Home)  
   ![Bar Chart ](https://github.com/user-attachments/assets/8bdc267c-3390-4cd3-81b5-d881f597a020) 

6. **Ribbon Chart** – Claim amount by age group (Adult, Elder, Young Adult)  
    ![Area Chart](https://github.com/user-attachments/assets/4de790bd-b9e6-41ae-b7cc-08c5e8e6517d) 

7. **Donut Chart** – Active vs Inactive policies  
   ![Donut Chart](https://github.com/user-attachments/assets/9d1fae49-d95e-4f8b-b8c1-bf65bb88d208)  

8. **Table** – Claim amount breakdown by policy type and status  
   ![Table](https://github.com/user-attachments/assets/103bb45d-26a5-40ab-850e-33b5595d10f6)  

9. **Word Cloud** – Sentiment keywords from customer feedback  
   ![Word Cloud](https://github.com/user-attachments/assets/1cb4ecde-cddc-4666-90e5-529ba9b39ef9)

10. **Table** – Detailed customer feedback with sentiment scores  
   ![Feedback Table](https://github.com/user-attachments/assets/5b9fa663-e8b7-4944-b63a-67f578c14134)  

11. **Published Dashboard** – Power BI Service View  

   ![Published Dashboard](https://github.com/user-attachments/assets/10a0db53-52ae-4ba1-a551-9ee4d76e6f30)  


---



## 📌 Insights  

**1️⃣ Policy Overview**  
- Total Premium Amount: **₹5.98M**  
- Total Coverage Amount: **₹600.55M**  
- Total Claim Amount: **₹16.91M**  

**2️⃣ Claim Status Distribution**  
- Rejected: **4.4K claims**  
- Settled: **3.4K claims**  
- Pending: **2.3K claims**  

**3️⃣ Policy Type Performance**  
- Highest premium from **Travel Insurance** (₹2.5M).  
- Health and Auto policies follow with strong coverage amounts.  

**4️⃣ Age Group Claims**  
- Adults have the highest claim amounts (₹8.6M).  
- Young Adults are second with ₹6.4M claims.  

**5️⃣ Customer Feedback Sentiment**  
- Majority positive feedback with keywords like *"Excellent"*, *"Quick"*, *"Helpful"*.  
- Negative feedback includes *"Website down"*, *"Policy terms unclear"*, *"Long response time"*.  

---

## 💡 Business Recommendations  

1. **Improve Claim Processing Time** – Reduce pending claims to improve customer trust.  
2. **Enhance Digital Experience** – Fix website accessibility issues and simplify navigation.  
3. **Target High-Value Segments** – Focus marketing on Adult age group and Travel policy buyers.  
4. **Reduce Rejection Rates** – Review reasons for high rejected claims and improve approval processes.  

---

## 🛠 Tools & Technologies Used  

- **SQL Server** – Data extraction and preprocessing  
- **Power BI Desktop & Service** – Dashboard creation & publishing  
- **DAX** – KPI and calculated measures  
- **Power Query** – Data cleaning & transformation  
- **Word Cloud Visual** – Sentiment analysis from feedback  

---

## 🙋‍♀️ Author  

**Pragati Kumari**  
_Data Analyst | Power BI | Excel | SQL | Python_  
🔗 [LinkedIn](#) *(https://www.linkedin.com/in/pragati-kumari-b60352305)*  

---

## 🚀 How to View the Dashboard  

1. Download the `.pbix` file.  
2. Open it in **Power BI Desktop**.  
3. Interact with slicers and visuals for deeper insights.  

---

## 📄 License  

Open for learning and portfolio demonstration. Not for commercial use.  
