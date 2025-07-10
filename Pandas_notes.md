# 🐼 Pandas Complete Notes – For Revision & Projects

> ✨ Real project + notebook-based Pandas notes. Ideal for beginner → intermediate.

---

## 📌 Table of Contents
1. [What is Pandas?](#what-is-pandas)  
2. [Core Data Structures](#core-data-structures)  
3. [Reading Data](#reading-data)  
4. [Basic DataFrame Operations](#basic-dataframe-operations)  
5. [Data Selection & Filtering](#data-selection--filtering)  
6. [Handling Missing Data](#handling-missing-data)  
7. [Data Cleaning & Type Conversion](#data-cleaning--type-conversion)  
8. [Useful Functions](#useful-functions)  
9. [GroupBy and Aggregation](#groupby-and-aggregation)  
10. [Merging & Joining DataFrames](#merging--joining-dataframes)  
11. [Exporting Data](#exporting-data)  
12. [Feature Engineering](#feature-engineering)  
13. [Categorical Encoding](#categorical-encoding)  
14. [Working with Dates](#working-with-dates)  
15. [Project-Based Learnings](#project-based-learnings)  
16. [Optional Advanced Pandas](#optional-advanced-pandas)  

---

## 🧠 What is Pandas?

> Pandas is a powerful library used for structured data analysis, manipulation, and cleaning.

```python
import pandas as pd  # Pandas as shortcut 'pd'
import numpy as np   # For handling missing values or numeric ops
📦 Core Data Structures
✅ Series (1D labelled data)
python
Copy
Edit
# Create a Series from a list
s = pd.Series([10, 20, 30])
✅ DataFrame (2D tabular data)
python
Copy
Edit
# Create DataFrame using dictionary
data = {'Name': ['Alice', 'Bob'], 'Age': [25, 30]}
df = pd.DataFrame(data)
📥 Reading Data
python
Copy
Edit
# Load data from different file types
pd.read_csv("file.csv")
pd.read_excel("file.xlsx")
pd.read_json("file.json")
🛠️ Basic DataFrame Operations
python
Copy
Edit
df.head()       # First 5 rows
df.tail()       # Last 5 rows
df.shape        # Get (rows, columns)
df.info()       # Column types and nulls
df.describe()   # Summary stats of numeric columns
🎯 Data Selection & Filtering
python
Copy
Edit
df['Age']                  # Select one column
df[['Name', 'Age']]        # Select multiple columns
df.loc[2]                  # Row by index label
df.iloc[2]                 # Row by position
df[df['Age'] > 25]         # Filter rows by condition
🚫 Handling Missing Data
python
Copy
Edit
df.isnull().sum()                         # Count missing values
df.dropna()                               # Drop rows with any nulls
df.fillna(0)                              # Fill nulls with 0
df['col'].replace('Unknown', np.nan)     # Replace specific value with NaN
🧽 Data Cleaning & Type Conversion
python
Copy
Edit
df['Age'] = df['Age'].astype(int)         # Change data type
df['Name'] = df['Name'].str.strip()       # Remove extra spaces
df['Name'] = df['Name'].str.lower()       # Convert text to lowercase
🧰 Useful Functions
python
Copy
Edit
df['col'].value_counts()    # Frequency of each value
df['col'].unique()          # List of unique values
df['col'].nunique()         # Number of unique values
df.sample(5)                # Random 5 rows
df.duplicated().sum()       # Count of duplicate rows
🧠 GroupBy and Aggregation
python
Copy
Edit
df.groupby('department').mean()            # Mean salary by department
df.groupby('gender')['salary'].sum()       # Sum of salary by gender
🔗 Merging & Joining DataFrames
python
Copy
Edit
# Merge datasets using a common key
pd.merge(df1, df2, on='id', how='inner')  # Types: inner, left, right, outer

# Concatenate dataframes vertically or horizontally
pd.concat([df1, df2])
📤 Exporting Data
python
Copy
Edit
# Save cleaned/processed data to file
df.to_csv("output.csv", index=False)
df.to_excel("output.xlsx")
🧠 Feature Engineering
python
Copy
Edit
# Create new column from existing ones
df['BonusSalary'] = df['salary'] + df['bonus']

# Extract first character from name
df['Initial'] = df['Name'].apply(lambda x: x[0])
🧾 Categorical Encoding
python
Copy
Edit
# Convert categories to numeric binary columns
pd.get_dummies(df, columns=['Gender'])
📆 Working with Dates
python
Copy
Edit
df['Date'] = pd.to_datetime(df['Date'])   # Convert string to datetime
df['Year'] = df['Date'].dt.year           # Extract year
df['Month'] = df['Date'].dt.month         # Extract month
🔍 Project-Based Learnings
python
Copy
Edit
df.loc[2]['Title']   # Access specific row and column

df[df['episodes'] == 'Unknown']   # Filter specific string condition

df['episodes'].replace('Unknown', np.nan, inplace=True)  # Clean dirty data
🧪 Optional Advanced Pandas
python
Copy
Edit
df.query("Age > 30 and Gender == 'Male'")    # SQL-style row filtering
df.eval("Total = salary + bonus", inplace=True)  # Column calc with expressions
df.explode('skills')                         # Split list-like values into rows
pd.cut(df['Age'], bins=[0,18,35,60], labels=['Teen','Adult','Senior'])  # Bin ranges
df.corr()                                    # Correlation matrix for numeric columns
