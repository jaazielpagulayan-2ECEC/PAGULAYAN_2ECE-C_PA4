# Jaaziel Raighne M. Pagulayan
## 2ECE-C
## 09/17/2026

### I. Intended Learning Outcomes 

At the end of this laboratory activity, the student should be able to:
1. filter tabular data using several categorical and numerical conditions;
2. construct focused DataFrames by selecting relevant features;
3. summarize the relationship between categorical features and a numerical variable; and
4. communicate a data comparison using clear and correctly labeled plots.

### A. VISAYAS COMMUNICATION DATAFRAME

`Explanation`:

* 'import pandas as pd' loads the pandas Library into Python and gives it the shortcut name pd, so it's easier to type. Pandas is used to handle tabular data (like spreadsheets).


* 'cars = pd.read_csv('cars.csv')' reads the dataset file named 'cars.csv' using pandas and saves the table into a variable called cars.

* 'cars.shape' Returns the dimensions of the table as (rows, columns).

* 'cars.columns' displays the names of all the columns in the dataset

* 'cars_6_to_10 = cars.iloc[[0, 5,6,7,8,9]]' uses .iloc to pick specific rows by their index numbers: rows 0, 5, 6, 7, 8, and 9. It saves this small chunk of data into a new variable called cars_6_to_10

* 'cars_6_to_10.loc[[0,5,6,7,8,9],['Model','mpg','cyl','hp','gear']]' uses .loc to select specific rows (0, 5, 6, 7, 8, 9) AND specific column names ('Model', 'mpg', 'cyl', 'hp', 'gear'). This filters down the table so only those specific cells show up.

```python
import pandas as pd

cars = pd.read_csv('cars.csv')
cars

cars.shape

cars.columns

cars_6_to_10 = cars.iloc[[0, 5,6,7,8,9]]
cars_6_to_10

cars_6_to_10.loc[[0,5,6,7,8,9],['Model','mpg','cyl','hp','gear']]
```

### B. VISAYAS FEMALE DATAFRAME

`Explanation:`

* 'toyota = cars.loc[cars['Model'] == 'Toyota Corolla']' searches the 'Model' column for the exact string 'Toyota Corolla'. It filters out everything else and stores that single row in the variable toyota.

* 'pontiac = cars.loc[cars['Model']=='Pontiac Firebird', ['Model','mpg','hp','wt']]' finds the row where 'Model' is 'Pontiac Firebird', but only extracts four specific columns: 'Model', 'mpg', 'hp', and 'wt'. Saves this filtered result into pontiac.

```python
toyota = cars.loc[cars['Model'] == 'Toyota Corolla']
toyota

pontiac = cars.loc[cars['Model']=='Pontiac Firebird', ['Model','mpg','hp','wt']]
pontiac
```

### C. CATEGORY-AVERAGE VISUALIZATION

 `Explanation:` 
 
 * 'selected_cars = cars.loc[(cars['Model']=='Datsun 710') | (cars['Model']=='Lotus Europa') | (cars['Model']=='Ferrari Dino'), ['Model','mpg','cyl','hp','gear']]' This uses pandas .loc[] to filter specific rows and columns simultaneously, while this operator '|' selects any row where the model name matches 'Datsun 710', 'Lotus Europa', or 'Ferrari Dino' then ['Model','mpg','cyl','hp','gear'] specifies the exact list of columns to return for those matching rows.

 * 'selected_cars.shape'  returns the dimensions of the table as (rows, columns). 

   
```python

selected_cars = cars.loc[(cars['Model']=='Datsun 710') | (cars['Model']=='Lotus Europa') | (cars['Model']=='Ferrari Dino'), ['Model','mpg','cyl','hp','gear']]
selected_cars

selected_cars.shape

```
