# Jaaziel Raighne M. Pagulayan
## 2ECE-C
## 09/17/2026

### I. Intended Learning Outcomes 

At the end of this laboratory activity, the student should be able to:
1. filter tabular data using several categorical and numerical conditions;
2. Construct focused DataFrames by selecting relevant features;
3. summarize the relationship between categorical features and a numerical variable; and
4. Communicate a data comparison using clear and correctly labeled plots.

`Explanation`
* 'import pandas as pd' loads the pandas Library into Python and gives it the shortcut name pd, so it's easier to type. Pandas is used to handle tabular data (like spreadsheets).
* 'import matplotlib.pyplot as plt' loads the Matplotlib plotting module and assigns it the shortcut name plt for generating charts and visual data summaries.

```python

import pandas as pd
import matplotlib.pyplot as plt

```

### A. VISAYAS COMMUNICATION DATAFRAME

`Explanation`:

* 'df = pd.read_excel('board2.xlsx')' reads the dataset file named 'board2.xlsx' using pandas and saves the table into a variable df.

* 'df['Average'] = df[['Math', 'Electronics', 'GEAS', 'Communication']].mean(axis=1)' calculates the horizontal mean (axis=1) across the four subject scores for each row and assigns the result to a new column named 'Average'

* 'VisComm = df.loc[(df['Hometown'] == 'Visayas') & (df['Track'] == 'Communication'), ['Name', 'Gender', 'Math', 'Electronics', 'Average']]' filters the data for students whose 'Hometown' is 'Visayas' AND whose 'Track' is 'Communication'. It selects only the specified columns (Name, Gender, Math, Electronics, and Average) and stores the filtered table in a new DataFrame named VisComm.

* 'VisComm.shape[0]' returns the total number of rows in the DataFrame.

```python
df = pd.read_excel('board2.xlsx')
df['Average'] = df[['Math', 'Electronics', 'GEAS', 'Communication']].mean(axis=1)

VisComm = df.loc[(df['Hometown'] == 'Visayas') & (df['Track'] == 'Communication'), ['Name', 'Gender', 'Math', 'Electronics', 'Average']]
VisComm

VisComm.shape[0]
```

### B. VISAYAS FEMALE DATAFRAME

`Explanation:`

*  'VisFemale = df.loc[(df['Hometown'] == 'Visayas') & (df['Gender'] == 'Female'), ['Name', 'Gender', 'GEAS', 'Electronics', 'Average']]'  Tfilters the main dataset for female students whose hometown is Visayas, extracting the columns Name, Gender, GEAS, Electronics, and Average.

*  'VisFemale.loc[(VisFemale['Average'] >= 60)]' filters the VisFemale DataFrame to display only those female students who obtained an overall average grade of 60 or higher.

```python
VisFemale = df.loc[(df['Hometown'] == 'Visayas') & (df['Gender'] == 'Female'), ['Name', 'Gender', 'GEAS', 'Electronics', 'Average']]
VisFemale

VisFemale.loc[(VisFemale['Average'] >= 60)]

```

### C. CATEGORY-AVERAGE VISUALIZATION

 `Explanation:` 
 
 * 'df.groupby("Category")["Average"].mean().reset_index()' groups the dataset by a specific categorical column (Track, Gender, or Hometown), calculates the mean of the 'Average' scores for each group, and uses .reset_index() to convert the grouped series back into a clean, standard DataFrame indexed from 0.
 * 
```python

mean_track = df.groupby("Track")["Average"].mean().reset_index()
mean_gender = df.groupby("Gender")["Average"].mean().reset_index()
mean_hometown = df.groupby("Hometown")["Average"].mean().reset_index()

```

```python
plt.figure(figsize=(20, 7))

plt.subplot(1, 3, 1)
plt.bar(mean_track['Track'], mean_track['Average'])
plt.title('Mean Average by Track')
plt.xlabel('Track')
plt.ylabel('Mean Average Grade')
plt.text(-0.4, -17, 'The Communication track obtained the highest sample mean (67.975).')
plt.ylim(0, 100)

plt.subplot(1, 3, 2)
plt.bar(mean_gender['Gender'], mean_gender['Average'], color = 'Black')
plt.title('Mean Average by Gender')
plt.xlabel('Gender')
plt.text(-0.3, -17, 'Male Students recorded the highest sample mean(67.18).')
plt.ylim(0, 100)

plt.subplot(1, 3, 3)
plt.bar(mean_hometown['Hometown'], mean_hometown['Average'], color = 'green')
plt.title('Mean Average by Hometown')
plt.xlabel('Hometown')
plt.text(-0.2, -17, 'Students from Luzon obtained the highest sample mean (68.08).')
plt.ylim(0, 100)

plt.tight_layout()
plt.show()

```
`Explanation`
This final code block initializes a plotting layout with three side-by-side bar charts displaying the calculated mean average grades across Track, Gender, and Hometown. Each plot includes customized labels, title annotations indicating the highest-performing category, a fixed y-axis range from 0 to 100, and plt.tight_layout() to prevent subplots from overlapping.
