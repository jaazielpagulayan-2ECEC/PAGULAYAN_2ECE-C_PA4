# Jaaziel Raighne M. Pagulayan
## 2ECE-C
## 09/17/2026

### I. Intended Learning Outcomes 

At the end of this laboratory activity, the student should be able to:
1. filter tabular data using several categorical and numerical conditions;
2. construct focused DataFrames by selecting relevant features;
3. summarize the relationship between categorical features and a numerical variable; and
4. communicate a data comparison using clear and correctly labeled plots.

`Explanation`
* import pandas as pd loads the pandas Library into Python and gives it the shortcut name pd, so it's easier to type. Pandas is used to handle tabular data (like spreadsheets).
* import matplotlib.pyplot as plt loads the matplotlib into the python and gives it the shortcut name plt

### A. VISAYAS COMMUNICATION DATAFRAME

`Explanation`:

* 'df = pd.read_excel('board2.xlsx')' reads the dataset file named 'board2.xlsx' using pandas and saves the table into a variable df.

* 'df['Average'] = df[['Math', 'Electronics', 'GEAS', 'Communication']].mean(axis=1)' creates a new data frame that computes the average   

* 'VisComm = df.loc[(df['Hometown'] == 'Visayas') & (df['Track'] == 'Communication'), ['Name', 'Gender', 'Math', 'Electronics', 'Average']]' uses .loc and 

* 

* 

* 

```python

```

### B. VISAYAS FEMALE DATAFRAME

`Explanation:`

* 

* 

```python

```

### C. CATEGORY-AVERAGE VISUALIZATION

 `Explanation:` 
 
 * 

 * 

   
```python


```
