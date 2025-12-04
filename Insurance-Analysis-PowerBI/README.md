# 📊 Project Title – Data Analytics Case Study (Power BI + SQL + Python)

## 📝 Project Overview  
This project focuses on analyzing **[brief topic: e.g., insurance claims, customer behavior, sales performance]** using a full end-to-end data analytics workflow.  
The goal is to extract meaningful insights, build an interactive dashboard, and apply techniques such as data cleaning, data modeling, visualization, sentiment analysis, and security implementation.

---

## 🔧 Tools & Technologies Used  
- **SQL** – Data import, cleaning, and preprocessing  
- **Power BI Desktop** – Data modeling, DAX measures, dashboard design  
- **Power BI Service** – Publishing, scheduled refresh, Row-Level Security  
- **Python (TextBlob)** – Sentiment analysis for unstructured text  
- **Excel / CSV** – Supporting datasets  

---

## 📁 Project Files  

- [Insurance Data Analysis.pbix](./Insurance%20Data%20Analysis%20(Project%201).pbix) - Interactive Power BI report 
- [InsuranceData.csv](./InsuranceData.csv) - Main dataset  
- [Insurance-Customer-Feedback.xlsx](./Insurance-Customer-Feedback.xlsx) - Secondary dataset
- [Page 1 Dashboard](./Page%201%20(Project%20-%201)%20updated.jpg) - Dashboard images 
- [Page 2 Dashboard](./Page%202%20(Project%20-%201).jpg) - Dashboard images  
- [Page 3 Dashboard](./Page%203%20(Project%20-%201).jpg) - Dashboard images
- [README.md](./README.md) - Documentation

---

## 📂 Data Description  
Brief explanation of datasets used:

- **Dataset 1:**  
  - Number of records: 10,005 rows
  - Key fields: Policy Number, CustomerID, Age, Gender, Policy Type, Start Date, End Date, Premium Amount, Coverage Amount, Claim Number, Claim Date, Claim Amount, Claim Status.
  - Description: ____________ 

- **Dataset 2:**  
  - Number of records: 98 rows
  - Key fields: Customer Name, Feedback  

---

## 🧹 Data Cleaning & Preprocessing  
Key steps performed:

- Checked for missing values, duplicates, and inconsistencies  
- Standardized data types (dates, text, numerics)  
- Removed irrelevant fields  
- Created new calculated columns (e.g., age groups, policy groups)  
- Ensured referential integrity between tables  

---

## 🧮 Data Modeling  
- Established relationships between tables  
- Built a star/galaxy schema  
- Created DAX measures for KPIs such as:  
  - Total Premium  
  - Total Claims  
  - Coverage Amount  
  - Sentiment Score (normalized)  

---

## 📊 Dashboard Overview  
Main visuals included:
## 📸 Main Page

![Dashboard Main](./Page%201%20(Project%20-%201)%20updated.jpg)
- [Page 2](./Page%202%20(Project%20-%201).jpg) - contains Table with conditional formatting

## Page 3 - WordCloud (sentiment
 ![Page 3 - WordCloud (sentiment)](./Page%203%20(Project%20-%201).jpg)


---

## 💡 Key Insights  

1. **58% of all policies are active**, indicating strong customer retention.  
2. **Travel policies generate the highest premium**, while Home policies generate the lowest.  
3. **Travel policies have the highest number of rejected claims**, highlighting potential process inefficiencies.  
4. **Customers aged 60+ report the highest claim amounts (₹6.4M)**, suggesting increased risk in elder demographics.  
5. **31% of customers expressed dissatisfaction**, driven by issues like complex claim procedures, long wait times, and poor customer service.  

---

## 🔐 Row-Level Security (RLS)  
Implemented RLS in Power BI to restrict data visibility:

- **Role 1:** Travel 
- **Role 2:** Health
- Users only see data relevant to their roles  
- RLS applied in both Desktop & Service  

---

## 🧠 Sentiment Analysis  
Using Python (TextBlob):

**Steps:**  
- Tokenized customer feedback  
- Calculated polarity using TextBlob  
- Normalized score using:  

```python
# 'dataset' holds the input data for this script
from textblob import TextBlob

def get_sentiment(text):
    if text:
        # Get the default polarity (-1 to 1)
        score = TextBlob(str(text)).sentiment.polarity
        # Convert to 0 to 1 scale
        normalized_score = (score + 1) / 2
        return normalized_score
    else:
        return 0.5 # Return neutral if text is missing

# Apply the function to your Feedback column
dataset['Sentiment_Score'] = dataset['Feedback'].apply(get_sentiment)
```  

- Categorized as:  
  - Excellent  
  - Good  
  - Needs Improvement  
- Visualized using WordCloud and bar charts  

---

## 🚀 How to Use This Project  
1. Download the `.pbix` file  
2. Update data source paths  
3. Refresh to load fully  
4. Explore dashboard & insights  

---

## 🏁 Conclusion  
This project demonstrates the complete workflow of a data analyst—  
from data extraction → cleaning → modeling → visualization → insight generation → security implementation.

It showcases strong skills in SQL, Power BI, and Python, along with an ability to analyze real-world business scenarios.

---

## 🙌 Connect With Me  
If you found this project useful or want to collaborate, feel free to reach out on LinkedIn!  
👉 https://www.linkedin.com/in/keshav-sureka/
