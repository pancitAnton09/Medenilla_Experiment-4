# Medenilla_Experiment-4
# DATA WRANGLING AND VISUALIZATION

### I. Intended Learning Outcomes:
1. To identify the codes and functions needed in cleaning and visualizing data
2. To be able to apply and use the different codes and functions in creating a Python program that will
be used in data wrangling and data visualization
## ECE BOARD EXAM PROBLEM

Access Pandas' function
```python
import pandas as pd
```

Import the .csv file as dataframe called list
```python
list = pd.read_excel('board2.xlsx')
```

### For Part 1

1. Create dataframe Vis with columns “Name”, “Gender”, “Track”, and “Math”, where hometown is constant as Visayas and Math grade is less than 70. Then, display the dataframe.
```python
Vis = list[(list['Hometown'] == 'Visayas') & (list['Math']<70)][['Name','Gender','Track','Math']]
Vis
```

2. Create dataframe Instru with columns “Name”, “GEAS”, “Electronics” where track is Instrumentation, Hometown is Luzon and Electronics grade is greater than 70. After that, we can show the output.
```python
Instru = list[(list['Track'] == 'Instrumentation')
  & (list['Hometown'] == 'Luzon')
  & (list['Electronics'] > 70)][['Name', 'GEAS', 'Electronics']]
Instru
```

3. Create a column named Average and compute for the weighted average for each subjects
```python
list['Average'] = list[['Math','Electronics','GEAS','Communication']].mean(axis=1)
```

4. Create dataframe Mindy with columns 'Name','Track','Electronics', and 'Average', where hometown is mindanao, gender is female, and average is greater than equal to 55. Dataframe Mindy can be displayed.
```python
Mindy = list[(list['Hometown'] == 'Mindanao') & (list['Gender'] == 'Female') & (list['Average'] >= 55)][['Name', 'Track', 'Electronics','Average']]
Mindy
```


## Author
Medenilla, Jose Anton M.
