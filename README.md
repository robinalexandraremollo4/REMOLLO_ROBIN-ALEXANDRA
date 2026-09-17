# ECE-2112-PA-4  

**Made by: Robin Alexandra B. Remollo | 2ECE-D**

This content of this repository contains the Programming Assignment 4 for our course "Advanced Computer Programming and Algorithms" this S.Y. 2026-2027. This project covers three Python problems pertaining to Experiment 4: Data Wrangling and Data Visualization.

## I. OBJECTIVES OF THE EXPERIMENT

The objectives of the experiment are the following:

- filter tabular data using several categorical and numerical conditions;
- construct focused DataFrames by selecting relevant features;
- summarize the relationship between categorical features and a numerical variable; and
- communicate a data comparison using clear and correctly labeled plots.

## II. PROGRAMMING PROBLEMS

## A. Visayas Communication DataFrame

Instructions:

Create a DataFrame named `VisComm` containing students whose `Hometown` is `Visayas` and whose `Track` is `Communication`. Retain only these columns, in the stated order:

``` python
Name, Gender, Math, Electronics, Average`
```

Display the resulting DataFrame and its number of rows. Both filtering conditions must be applied to
the source dataset before the columns are selected.


The following methods and functions were used in this problem:

- `import pandas as pd` = This imports the Pandas library.
- `df.loc[]` = This is used to select specific rows and columns from a DataFrame and applies Boolean conditions to filter rows.
- `==` = An equality operator used to check whether the values in a column are equal to a specified value or category.
- `&` = A logical AND operator used in Pandas to combine multiple Boolean conditions to ensure that a row is selected only when both the Hometown and Gender conditions are satisfied.
- `['Name', 'Gender', 'Math', 'Electronics', 'Average']` = This specifies the columns that should be included in the resulting DataFrame which are retained in the same order in which they are listed.
- `len()` = This returns the number of items in an object, which can be used to determine how many students satisfy the specified conditions.

### A. Hometown is Visayas, Track is Communications
``` python
df['Average'] = (
    
    +df['Math'] +
    df['GEAS'] +
    df['Electronics']
) / 3
```

``` python
VisComm = df.loc[(df['Hometown'] == 'Visayas') & (df['Track'] == 'Communication')].reset_index()
VisComm.loc[:,['Name','Gender','Math','Electronics','Average']]
```

### B. Number of rows

``` python
print('Number of Rows: ',len(VisComm))
```


## B. Visayas Female DataFrame

Instructions:

Create a second DataFrame named `VisFemale` containing students whose `Hometown` is `Visayas` and whose `Gender` is `Female`. Retain only:

``` python
Name, Track, GEAS, Electronics, Average`
```

Display `VisFemale`. Then display only the rows of `VisFemale` whose `Average` is at least 60. Do not overwrite `VisFemale` when performing this second filter.

The following methods and functions were used in this problem:

- `df.loc[]` = This is used to select specific rows and columns from a DataFrame and applies Boolean conditions to filter rows.
- `==` = An equality operator used to check whether the values in a column are equal to a specified value or category.
- `&` = A logical AND operator used in Pandas to combine multiple Boolean conditions to ensure that a row is selected only when both the Hometown and Gender conditions are satisfied.
` `>=` = A greater-than-or-equal-to comparison operator which checks whether a numerical value meets or exceeds a specified threshold.

### A. Display  `VisFemale`
```python
VisFemale = df.loc[(df['Hometown'] == 'Visayas') & (df['Gender'] == 'Female'),['Name','Track','GEAS','Electronics','Average']].reset_index()
VisFemale
```

### B. Rows of `VisFemale` with `Average` is at least 60
``` python
VisFemale.loc[(VisFemale['Average']>=60)]
```

## C. Category-Average Visualization

Instructions:

Examine how the recorded `Average` differs across the three categorical features `Track`, `Gender`, and `Hometown`.

a. For each feature, compute the mean of `Average` for every category using Pandas.\
b. Display the three summary tables.\
c. Create one figure containing three bar charts: mean `Average` by `Track`, by `Gender`, and by `Hometown`.\
d. Below the figure, write three concise statements identifying the category with the highest sample
mean for each feature.

**Interpretation Rule**: Describe the observed dataset only. A difference in group means does not, by itself, establish that a feature causes a higher board-exam score.

The following methods and functions were used in this problem:

- `.groupby()` = This groups the rows in a DataFrame for the data to be organized into separate categories so that the mean can be calculated individually.
- `['Average']` = This is the variable used to calculate the mean for each category.
- `.mean()` = This calculates the mean of the numerical values within each group.

## PLOT: BAR CHART ##
The following methods and functions for the bar charts were used in this problem:

- `plt.figure()` = This creates a figure where the graphs will be displayed. It is also used to specify the overall size of the figure.
- `plt.subplot()` = This allows the figure to be displayed into three bar charts within a single figure, allowing the results to be clumped together.
- `plt.bar()` = This creates the bar chart using categorical values, where the height of each bar represents the calculated mean.
- `plt.title()` = This gives a title to each graph and identify what the graph represents.
- `plt.xlabel()` = This identifies the variables shown on the x-axis.
- `plt.ylabel()` = This identifies the variables shown on the y-axis.
- `plt.xticks()` = This adjusts the positioning of the labels so that they are readable and do not overlap.
- `plt.tight_layout()` = This automatically adjusts the spacing between the three charts being displayed together.
- `plt.show()` = This displays the completed figure containing all the visualizations

### Mean Averages for `Track`, `Gender`, `Hometown` ###

``` python
track_mean = df.groupby('Track')['Average'].mean().reset_index()
display(track_mean)
```

``` python
gender_mean = df.groupby('Gender')['Average'].mean().reset_index()
display(gender_mean)
```

```python
hometown_mean = df.groupby('Hometown')['Average'].mean().reset_index()
display(hometown_mean)
```
### Plot for Bar Charts ###

```python
track_max = track_mean.max()
track_max
```

``` python
gender_max = gender_mean.max()
gender_max
```

``` python
hometown_max = hometown_mean.max()
hometown_max
```

``` python

plt.figure(figsize=(20, 5))

plt.subplot(1, 3, 1)
plt.bar(track_mean['Track'], track_mean['Average'])
plt.title('Mean Average by Track')
plt.xlabel('Track')
plt.ylabel('Mean Average Score')

plt.subplot(1, 3, 2)
plt.bar(gender_mean['Gender'], gender_mean['Average'])
plt.title('Mean Average by Gender')
plt.xlabel('Gender')
plt.ylabel('Average')

plt.subplot(1, 3, 3)
plt.bar(hometown_mean['Hometown'], hometown_mean['Average'])
plt.title('Mean Average by Hometown')
plt.xlabel('Hometown')
plt.ylabel('Average')

plt.tight_layout()
plt.show()

print("The Track that has the highest mean average is:\n")
print(track_max)

print("\nThe Gender that has the highest mean average is:\n")
print(gender_max)

print("\nThe Hometown that has the highest mean average is:\n")
print(hometown_max)

```

Thank you for reading!

To see the main python program for Programming Assignment 2, click this link 

READ ME FILE VERSION HISTORY

September 16, 2026 - Coding on Jupyter Notebook and finishing of Programming Problems. \
September 17, 2026 - Finalization of code structures and flow of README file. Creation of a cohesive Github repository for all requirements.
