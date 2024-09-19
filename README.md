# Medenilla_Experiment-4
# DATA WRANGLING AND VISUALIZATION

### I. Intended Learning Outcomes:
1. To identify the codes and functions needed in cleaning and visualizing data
2. To be able to apply and use the different codes and functions in creating a Python program that will
be used in data wrangling and data visualization
## ECE BOARD EXAM PROBLEM

### For Part 1
Access Pandas function
```python
import pandas as pd
```

Import the .csv file as dataframe called list
```python
list = pd.read_excel('board2.xlsx')
```



1. Create dataframe Vis with columns “Name”, “Gender”, “Track”, and “Math”, where hometown is constant as Visayas and Math grade is less than 70. Then, display the dataframe.
```python
Vis = list[(list['Hometown'] == 'Visayas') & (list['Math']<70)][['Name','Gender','Track','Math']]
Vis
```
![image](https://github.com/user-attachments/assets/8e9eff77-49f2-4fa9-bb42-13a8a5b7e8d9)

2. Create dataframe Instru with columns “Name”, “GEAS”, “Electronics” where track is Instrumentation, Hometown is Luzon and Electronics grade is greater than 70. After that, we can show the output.
```python
Instru = list[(list['Track'] == 'Instrumentation')
  & (list['Hometown'] == 'Luzon')
  & (list['Electronics'] > 70)][['Name', 'GEAS', 'Electronics']]
Instru
```
![image](https://github.com/user-attachments/assets/c0f7938f-8fa2-47a6-a716-2348dc45441a)

3. Save the file as .xlsx
```
Instru.to_excel('Instru.xlsx', index = False)
```

4. Create a column named Average and compute for the weighted average for each subjects
```python
list['Average'] = list[['Math','Electronics','GEAS','Communication']].mean(axis=1)
```

5. Create dataframe Mindy with columns 'Name','Track','Electronics', and 'Average', where hometown is mindanao, gender is female, and average is greater than equal to 55. Dataframe Mindy can be displayed.
```python
Mindy = list[(list['Hometown'] == 'Mindanao') & (list['Gender'] == 'Female') & (list['Average'] >= 55)][['Name', 'Track', 'Electronics','Average']]
Mindy
```
![image](https://github.com/user-attachments/assets/9a3d74aa-d5d0-4469-a319-81cd6ff0b4a4)

6. Save the file as .xlsx
```python
Mindy.to_excel('Mindy.xlsx', index=False)
```

### For Part 2
Access pandas, matplot, seaborn libraries
```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
```

Barplot 1
```python
#Define the size of the figure to be used
plt.figure(figsize=(30, 10))

#Specify the layout of subplots in a grid (no.of rows, no. of columns, position  in the grid)
plt.subplot(1, 3, 1)

#Define the color of the palette using hex codes
custom_palette = ['#3498db', '#e74c3c', '#2ecc71']  # Example: Blue, Red, Green

#Create a boxplot using Seaborn (sns) that visualizes the distribution of Average grades for each category in the Track column.
sns.barplot(x='Track', y='Average', data=list, hue='Track', palette=custom_palette)

# Add white grid background for better visualization
sns.set(style="whitegrid")

#Label the title of the barplot
plt.title('Average Grade by Track')

#Determine the rotation of the x-axis labels
plt.xticks(rotation=0)

#Display graph
plt.show()
```
![image](https://github.com/user-attachments/assets/3ca737ae-a058-4774-b5d2-0e46f3ecab24)

Barplot 2
```python
#Define the size of the figure to be used
plt.figure(figsize=(20, 10))

#Specify the layout of subplots in a grid (no.of rows, no. of columns, position  in the grid)
plt.subplot(1, 3,1)

#Define the color of the palette using hex codes
custom_palette = ['#ADD8E6', '#FFB6C1']  # Example: Blue, Red, Green

#Create a boxplot using Seaborn (sns) that visualizes the distribution of Average grades for each category in the Track column.
sns.barplot(x='Gender', y='Average', data=list, hue='Gender', palette=custom_palette)

#Add white grid background for better visualization
sns.set(style="whitegrid")

#Label the title of the barplot
plt.title('Average Grade by Gender')

#Determine the rotation of the x-axis labels
plt.xticks(rotation=0)

#Display graph
plt.show()
```
![image](https://github.com/user-attachments/assets/75bddfad-0db3-4b73-bce1-e21d21e1e749)

Barplot 3
```python
#Define the size of the figure to be used
plt.figure(figsize=(30, 10))

#Specify the layout of subplots in a grid (no.of rows, no. of columns, position  in the grid)
plt.subplot(1, 3, 1)

#Define the color of the palette using hex codes
custom_palette = ['#1E90FF', '#FF6347', '#32CD32']  # Example: Blue, Red, Green

#Create a boxplot using Seaborn (sns) that visualizes the distribution of Average grades for each category in the Track column.
sns.barplot(x='Hometown', y='Average', data=list, hue='Hometown', palette=custom_palette)

#Add white grid background for better visualization
sns.set(style="whitegrid")

#Label the title of the barplot
plt.title('Average Grade by Track')

#Determine the rotation of the x-axis labels
plt.xticks(rotation=0)

#Display graph
plt.show()
```
![image](https://github.com/user-attachments/assets/0c97ae59-497b-487a-8b07-64b86e0f5796)

## Conclusion:

In the case of the chosen track, we can conclude that it does not contribute to higher average score as seen in Barplot 1. As for the gender, Barplot 2 exhibits noticeably not much of a difference in regards to higher average scores of male and female. Lastly, we can conclude that hometown does not also have that much of an effect on the student's average scores as seen on Barplot 3.
## Author:
Medenilla, Jose Anton M.
  
## Date Published:
September 19, 2024
