# 🐼 Pandas Complete Notes – Hinglish Version (Easy Revision)

> 👨‍💻 Ye notes banaye gaye hain real projects + practice notebooks se. Simple language me likhe gaye hain taaki revision easy ho.

---

## 📌 Table of Contents
1. What is Pandas?  
2. Series & DataFrame  
3. Data Load karna  
4. Basic Operations  
5. Data Select & Filter  
6. Missing Data  
7. Data Clean & Type Change  
8. Useful Functions  
9. GroupBy & Aggregation  
10. Merge & Join  
11. Export to File  
12. Feature Engineering  
13. Categorical Encoding  
14. DateTime Columns  
15. Project Learnings  
16. Advance Pandas (Optional)

---

## 🧠 What is Pandas?

```python
import pandas as pd  # pandas ko pd naam se import karte hain
import numpy as np   # NaN ya numbers ke liye numpy use hota hai
📦 Series & DataFrame
python
Copy
Edit
# Series: 1D data hota hai
s = pd.Series([10, 20, 30])

# DataFrame: 2D table jaisa hota hai
data = {'Name': ['Alice', 'Bob'], 'Age': [25, 30]}
df = pd.DataFrame(data)
📥 Data Load karna (CSV, Excel)
python
Copy
Edit
pd.read_csv("file.csv")       # CSV file load
pd.read_excel("file.xlsx")    # Excel file load
pd.read_json("file.json")     # JSON file load
🛠️ Basic Operations
python
Copy
Edit
df.head()       # First 5 rows dekhne ke liye
df.tail()       # Last 5 rows dekhne ke liye
df.shape        # Kitne rows aur columns hain
df.info()       # Column ka datatype aur null info
df.describe()   # Numeric columns ka stats
🎯 Data Select & Filter
python
Copy
Edit
df['Age']                  # Ek column select karna
df[['Name', 'Age']]        # Multiple columns lena
df.loc[2]                  # Index ke basis pe row
df.iloc[2]                 # Position ke basis pe row
df[df['Age'] > 25]         # Filter rows where age > 25
🚫 Missing Data Handle karna
python
Copy
Edit
df.isnull().sum()                       # Null values count karo
df.dropna()                             # Jahan null ho wo row hatao
df.fillna(0)                            # Null value ko 0 se bhar do
df['col'].replace('Unknown', np.nan)   # Unknown ko NaN me badlo
🧽 Data Clean & Type Change
python
Copy
Edit
df['Age'] = df['Age'].astype(int)       # Age ko integer me convert karo
df['Name'] = df['Name'].str.strip()     # Name se extra space hatao
df['Name'] = df['Name'].str.lower()     # Name ko lowercase me karo
🧰 Useful Functions
python
Copy
Edit
df['col'].value_counts()    # Har value kitni baar aayi
df['col'].unique()          # Unique values kya hain
df['col'].nunique()         # Kitni unique values hain
df.sample(5)                # Random 5 rows dekhne ke liye
df.duplicated().sum()       # Duplicate rows kitni hain
🧠 GroupBy & Aggregation
python
Copy
Edit
df.groupby('department').mean()         # Har department ka avg nikaalo
df.groupby('gender')['salary'].sum()    # Gender wise salary ka sum
🔗 Merge & Join
python
Copy
Edit
pd.merge(df1, df2, on='id', how='inner')  # Dono data ko id ke basis pe jodo
pd.concat([df1, df2])                     # 2 dataframes ko upar neeche jodo
📤 Export to File
python
Copy
Edit
df.to_csv("output.csv", index=False)     # CSV file me save karo
df.to_excel("output.xlsx")               # Excel file me save karo
🧠 Feature Engineering
python
Copy
Edit
df['BonusSalary'] = df['salary'] + df['bonus']       # Naya column bana diya
df['Initial'] = df['Name'].apply(lambda x: x[0])      # First letter nikaala
🧾 Categorical Encoding
python
Copy
Edit
pd.get_dummies(df, columns=['Gender'])   # Gender column ko 0/1 me badla
📆 DateTime Columns
python
Copy
Edit
df['Date'] = pd.to_datetime(df['Date'])   # Date string ko datetime me badlo
df['Year'] = df['Date'].dt.year           # Year nikaalo
df['Month'] = df['Date'].dt.month         # Month nikaalo
🔍 Project Learnings
python
Copy
Edit
df.loc[2]['Title']   # Specific row aur column access

df[df['episodes'] == 'Unknown']    # Filter rows jisme episodes unknown hain

df['episodes'].replace('Unknown', np.nan, inplace=True)  # Clean kar diya
🧪 Advance Pandas (Optional)
python
Copy
Edit
df.query("Age > 30 and Gender == 'Male'")    # SQL-style filtering
df.eval("Total = salary + bonus", inplace=True)  # Expression based column
df.explode('skills')                         # List ko alag alag rows me karo
pd.cut(df['Age'], bins=[0,18,35,60], labels=['Teen','Adult','Senior'])  # Age range me divide
df.corr()                                    # Correlation matrix (numeric)
