# Gl-Covid-19_India_-data-analysis
Data analysis and visualization of COVID-19 cases across Indian states using Python
## 🦠 COVID-19 India Data Analysis (Python)

### 📘 **Project Overview**

This project performs a complete data analysis of **COVID-19 cases across India**.
The goal is to identify **trends, top affected states**, and **visualize key statistics** such as confirmed, cured, and death cases using Python.

---

## 🧩 **Step-by-Step Project Explanation**

### **1️⃣ Importing Required Libraries**

```python
import pandas as pd 
from matplotlib import pyplot as plt
import seaborn as sns
import datetime as dt
import numpy as np
```

* **Pandas**: For loading and analyzing tabular data
* **Matplotlib & Seaborn**: For creating visualizations
* **Datetime**: For handling date conversions
* **NumPy**: For numerical operations

---

### **2️⃣ Importing the Dataset**

```python
df = pd.read_csv("covid_19_india.csv", parse_dates=['Date'], dayfirst=False)
```

* The dataset `covid_19_india.csv` is read using pandas.
* The `Date` column is parsed as a datetime object for easier date-based analysis.

---

### **3️⃣ Viewing the Dataset**

```python
df.head()
```

Displays the **first 5 rows** to understand the structure and content of the dataset.

---

### **4️⃣ Selecting and Renaming Columns**

```python
df = df[['Date','State/UnionTerritory','Cured','Deaths','Confirmed']]
df.columns = ['date','state','cured','deaths','confirmed']
```

* Keeps only necessary columns for analysis.
* Renames columns for consistency and simplicity.

---

### **5️⃣ Checking Early and Latest Records**

```python
df.head()
df.tail()
```

* `head()` → Shows earliest records
* `tail()` → Shows most recent records
  This helps understand how the data evolves over time.

---

### **6️⃣ Filtering Data for a Specific Date**

```python
today = df[df.date == '2020-07-17']
```

* Filters the dataset for **17th July 2020** to analyze the latest available COVID-19 situation.

---

### **7️⃣ Sorting Data by Confirmed Cases**

```python
max_confirmed_cases = today.sort_values(by="confirmed", ascending=False)
```

* Sorts all Indian states by the total number of confirmed cases in descending order.
* This helps identify the **most affected states**.

---

### **8️⃣ Selecting Top 5 Affected States**

```python
top_states_confirmed = max_confirmed_cases[0:5]
```

* Extracts the **top 5 states** with the highest confirmed COVID-19 cases.
* These states will be visualized next.

---

### **9️⃣ Visualizing Top 5 States (Bar Plot)**

```python
sns.set(rc={'figure.figsize':(15,11)})
sns.barplot(x='state', y='confirmed', data=top_states_confirmed, hue='state')
plt.show()
```

* Creates a **bar chart** showing the top states by confirmed cases.
* Uses Seaborn for a clean, colorful visualization.
* Highlights how COVID-19 was distributed across states.

---

### **10️⃣ Handling Date Conversion**

```python
Maha["date"] = Maha["date"].map(dt.datetime.toordinal)
```

* Converts date to **ordinal numbers** (numeric representation of days).
* Helps in modeling or plotting time-series data numerically.
* (Handled with `.copy()` to avoid `SettingWithCopyWarning`.)

---

## 📊 **Key Insights**

* Maharashtra, Tamil Nadu, and Delhi showed the highest number of confirmed cases.
* Data visualization clearly shows how infection rates vary by region.
* Using Python libraries makes the analysis efficient and reproducible.

---

## 🧰 **Tech Stack**

* **Language:** Python
* **Libraries:** Pandas, NumPy, Matplotlib, Seaborn, Datetime
* **Tool:** Jupyter Notebook

---
## 📸 **Sample Output**


```markdown
![Top States COVID Cases](<img width="876" height="817" alt="image" src="https://github.com/user-attachments/assets/6c4aee30-ea25-491b-8f4f-a671d6d8ddcf" />
)
```

---

## 🏷️ **Tags**

#Python #DataAnalysis #COVID19 #Seaborn #DataVisualization #Pandas #Matplotlib #DataScience



