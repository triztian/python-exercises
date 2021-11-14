# 002 Group Student Grades

The goal of this exercise is to be able to read csv files and to continue to get
familiear with data cleaning. In addition to learning about sorting, and grouping
with native python data structures.

## Problem statement 

Given a list of student grades for a variable number of schools, calculate the average 
grade accross the 3 periods and calculate the average of each school in general.

The schools are printed by their average ranks from top to bottom, as well
as the information of the average, the top and lowest average and the 
number of students for each school.

## Example

Consider the following reported grades:

**sample.csv:**

```
school;absences;G1;G2;G3
"UABC";6;"5";"6";6
"UTT";3;"14";"16";16
"WGU";4;"12";"3";"3"
"UABC";4;"5";"5";6
"UTT";3;"10";"8";7
```


```bash
python3 grades.py ./sample.csv
```

The output of the program should be:

```
UTT:
	Students: 2
	Average: 11.83
	Highest Average Grade: 15.33
	Lowest Average Grade: 8.33

UABC:
	Students: 2
	Average: 10.83
	Highest Average Grade: 5.66
	Lowest Average Grade: 5.33

WGU:
	Students: 1
	Average: 6.0
	Highest Average Grade: 6.0
	Lowest Average Grade: 6.0
```

How this was calculated:

  1. First we determine the averages for each student, we do this by adding 
     G1, G2, G3 and dividing by 3 for every student:  
	 s1 = (5 + 6 + 6) / 3 = 5.66  
	 s2 = (14 + 16 + 16) / 3 = 15.33  
	 s3 = (12 + 3 + 3) / 3 = 6.0  
	 s4 = (5 + 5 + 6) / 3 = 5.33  
	 s5 = (10 + 8 + 7) / 3 = 8.33

  2. Next we calculate the average for each school, this is done by adding the
     average of each student and dividing by the number of students of the same 
     school:

     UABC (2 students) = (s1 + s4) / 2 = (5.66 + 5.33) / 2 = 10.83  
     UTT (2 students) = (s2 + s5) / 2 = (15.33 + 8.33) / 2 = 11.83  
     WGU (1 student) = (s3) / 1 = (6) / 1 = 6.0 (1 student)  

  3. Now that we have the values we should be able to order the schools based on
     their average, this yields the following rank from top to bottom:
       
	   1. UTT 
	   2. UABC
	   3. WGU

  4. Now for each school we must determin the top and bottom average amongst the
    students and print them accordingly.

### Requirements

  1. The file to be processed must be specificed through as a command line 
     argument
  2. Grades should be rounded down to 2 decimal digits
  3. The file may have varying field numbers but is guaranteed to have
     school, G1, G2 and G3 fields.

----

## Useful Hints

### Reading a CSV file

```python
import csv
with open('eggs.csv', newline='') as csvfile:
    spamreader = csv.reader(csvfile, delimiter=' ', quotechar='|')
	# `row` is a list
    for row in spamreader:
        print(', '.join(row))
```

### Minimum and maximum of a list

**Minumum:**
```python
>>> nums = [12, 1, 11, 8, 15, 10, 5, 12, 3, 16]
>>> min(nums)
1
```

**Maximum:**
```python
>>> nums = [12, 1, 11, 8, 15, 10, 5, 12, 3, 16]
>>> max(nums)
16
```

### Sorting a list

```python
>>> nums = [12, 1, 11, 8, 15, 10, 5, 12, 3, 16]
>>> sorted(nums)
[1, 3, 5, 8, 10, 11, 12, 12, 15, 16]
```



### Rounding Decimals

```python
>>> round(10.333435, 2)
10.33
```

**Output:**
```
Spam, Spam, Spam, Spam, Spam, Baked Beans
Spam, Lovely Spam, Wonderful Spam
```

## References

  * [Python `csv` library](https://docs.python.org/3/library/csv.html)
  * [Python `round()` function](https://docs.python.org/3/library/functions.html#round)
  * [Python `min()` function](https://docs.python.org/3/library/functions.html#min)
  * [Python `max()` function](https://docs.python.org/3/library/functions.html#max)


## Credits

  * Original Student Data set  
    UCI Machine Learning Repository  
    [Student Performance Data Set](https://archive.ics.uci.edu/ml/datasets/student+performance)
