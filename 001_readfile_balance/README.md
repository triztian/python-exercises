# 001 Readfile Balance

The goal of this exercise is to read a file line-by-line, parse the numeric
value per line and provide the account balance (sum) as output with the currency
symbol.

## Goals

  1. The file must be specified as an argument to the script
  2. The program should be able to handle values with and without both the 
     currency and sign
  3. The program should handle values with leading and traling spaces (surrounded by spaces or tabs)
  3. Values in the file may or may not have decimals
  4. The output should have 2 decimal digits

## Sample input file

The contents of the input file shown below, they should add up to `100.00`:

```
$10
11
      45.12			
-10
-$55.00
     111.34
  134
-120
-34
8
-0.4634.8
-$123.53
+123.4
        +$123.8
```

> **NOTE:** See `account.txt` for a full sample input file

### Example

```bash
python3 balance.py account.txt
```

**Output:**

```
$100.00
```

----

### Snippet hints

#### Does a string contain another?

```python
>>> "$" in "$99.00"
True
```

#### Creating a substring

```python
>>> value = "$99.0"
>>> value[1:]
'99.0'
```

  * See common string operations reference

#### Creating another substrin

```python
>>> s = "$99.0$"
>>> s[1:len(s)-1]
'99.0'
```

  * See common string operations reference

#### Deleting characters from a string

```python
>>> s = "$88.00"
>>> s.replace("$", "")
'88.00'
```

  * See common string operations reference

#### Command Line arguments

```python
# args.py
import sys
print(sys.argv[1])
```

**Output:**
```bash
python3 args.py Hello
Hello
```

### Useful references

  * [File and Directory Access](https://docs.python.org/3/library/filesys.html)
  * [Python open function](https://docs.python.org/3/library/functions.html#open)
  * [Common String Operations](https://docs.python.org/3/library/string.html)
  * [Formatting Currency](https://stackoverflow.com/a/320951/496351)
  * [Python round() function](https://docs.python.org/3/tutorial/floatingpoint.html#tut-fp-issues)