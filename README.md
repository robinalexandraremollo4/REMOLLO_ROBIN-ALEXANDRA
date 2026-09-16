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

## B. Visayas Female DataFrame

Instructions:

Create a second DataFrame named `VisFemale` containing students whose `Hometown` is `Visayas` and
whose `Gender` is `Female`. Retain only:

``` python
Name, Track, GEAS, Electronics, Average`
```

Display `VisFemale`. Then display only the rows of `VisFemale` whose `Average` is at least 60. Do not overwrite `VisFemale` when performing this second filter.


## C. Categoty-Average Visualization

Instructions:

Examine how the recorded `Average` differs across the three categorical features `Track`, `Gender`, and `Hometown`.

a. For each feature, compute the mean of `Average` for every category using Pandas.\
b. Display the three summary tables.\
c. Create one figure containing three bar charts: mean `Average` by `Track`, by `Gender`, and by `Hometown`.\
d. Below the figure, write three concise statements identifying the category with the highest sample
mean for each feature.

**Interpretation Rule**: Describe the observed dataset only. A difference in group means does not, by itself, establish that a feature causes a higher board-exam score.









