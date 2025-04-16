### 🔹 `rbind()` and `cbind()`

- `rbind()` → binds rows (adds rows vertically)
- `cbind()` → binds columns (adds columns horizontally)
- Values are recycled with a **warning** if lengths don’t match.

```r
> a <- 1:5
> b <- 46:50

> cb <- cbind(a, b)
> cb
     a  b
[1,] 1 46
[2,] 2 47
[3,] 3 48
[4,] 4 49
[5,] 5 50

> rb <- rbind(a, b)
> rb
  [,1] [,2] [,3] [,4] [,5]
a    1    2    3    4    5
b   46   47   48   49   50
```

#### Example with mismatched lengths (recycling):

```r
> a <- 1:3
> b <- 20:30

> rbind(a, b)
  [,1] [,2] [,3] [,4] [,5] [,6] [,7] [,8] [,9] [,10] [,11]
a    1    2    3    1    2    3    1    2    3     1     2
b   20   21   22   23   24   25   26   27   28    29    30

> cbind(a, b)
      a  b
 [1,] 1 20
 [2,] 2 21
 [3,] 3 22
 [4,] 1 23
 [5,] 2 24
 [6,] 3 25
 [7,] 1 26
 [8,] 2 27
 [9,] 3 28
[10,] 1 29
[11,] 2 30
```

### ⚠️ Warnings

```r
Warning messages:
1: In rbind(a, b) :
  number of columns of result is not a multiple of vector length (arg 1)
2: In cbind(a, b) :
  number of rows of result is not a multiple of vector length (arg 1)
```

---

### 🔹 Dimensions with `dim()`

```r
> a <- 1:5
> b <- 46:50

> m1 <- cbind(a, b)
> m2 <- rbind(a, b)

> dim(m1)
[1] 5 2

> dim(m2)
[1] 2 5
```

---

### 🔹 Example with recycling:

```r
> d <- 31:40
> rbind(a, d)
  [,1] [,2] [,3] [,4] [,5] [,6] [,7] [,8] [,9] [,10]
a    1    2    3    4    5    1    2    3    4     5
d   31   32   33   34   35   36   37   38   39    40
```

---

### 🔹 Recycling with arithmetic

```r
> ab <- c(3, 5, 6, 7)
> cd <- c(2, 4, 1)

> ab + cd
[1] 5 9 7 9

Warning message:
In ab + cd :
  longer object length is not a multiple of shorter object length
```

---

### 🔹 Arrays

- Created using `array()` and `dim=`

```r
> k <- array(dim = c(8))
> k
[1] NA NA NA NA NA NA NA NA

> d <- array(dim = c(3, 4))
> d
     [,1] [,2] [,3] [,4]
[1,]   NA   NA   NA   NA
[2,]   NA   NA   NA   NA
[3,]   NA   NA   NA   NA
```

---

### 🔹 Data Frames

```r
> a <- c(12, 23, 14, 15)
> b <- c("X", "Y", "Z", "W")
> df <- data.frame(a, b)

> df
   a b
1 12 X
2 23 Y
3 14 Z
4 15 W
```

---

### 🔹 Reading CSV files

```r
> bollywood <- read.csv("C:/Datasets/Bollywood_2015.csv")
> bollywood
# Displays all rows from the CSV file
```

---

### 🔹 `colnames()` vs `names()`

```r
> names(df)
[1] "a" "b"

> colnames(df)
[1] "a" "b"

> names(bollywood)
[1] "Movie_Name"         "BO_Collection"     
[3] "Budget"             "Box_Office_Verdict"
```

---

### 🔹 Lists and `names()`

```r
> s <- list(p = c(4, 5, 2), q = c(3, 2), r = TRUE)
> names(s)
[1] "p" "q" "r"
```

---

### 🔹 `setwd()` – Set Working Directory

```r
> setwd("C:/Datasets/")
```

Now you can simply do:

```r
> read.csv("Bollywood_2015.csv")
```

Instead of:

```r
> read.csv("C:/Datasets/Bollywood_2015.csv")
```

---

Great! Here's the next part of your R notes including the output for the `read.csv()` command that loads the Boston dataset:

---

### **Loading and Viewing the Boston Housing Dataset**

```r
# Load the Boston dataset
boston <- read.csv("C:/Datasets/Boston.csv")

# View the dataset
boston
```

**Output (First Few Rows):**

| crim   | zn   | indus | chas | nox   | rm    | age  | dis   | rad | tax | ptratio | black  | lstat | medv |
|--------|------|-------|------|-------|-------|------|--------|-----|-----|---------|--------|-------|------|
| 0.00632| 18.0 | 2.31  | 0    | 0.538 | 6.575 | 65.2 | 4.0900 | 1   | 296 | 15.3    | 396.90 | 4.98  | 24.0 |
| 0.02731| 0.0  | 7.07  | 0    | 0.469 | 6.421 | 78.9 | 4.9671 | 2   | 242 | 17.8    | 396.90 | 9.14  | 21.6 |
| 0.02729| 0.0  | 7.07  | 0    | 0.469 | 7.185 | 61.1 | 4.9671 | 2   | 242 | 17.8    | 392.83 | 4.03  | 34.7 |
| 0.03237| 0.0  | 2.18  | 0    | 0.458 | 6.998 | 45.8 | 6.0622 | 3   | 222 | 18.7    | 394.63 | 2.94  | 33.4 |
| 0.06905| 0.0  | 2.18  | 0    | 0.458 | 7.147 | 54.2 | 6.0622 | 3   | 222 | 18.7    | 396.90 | 5.33  | 36.2 |
| 0.02985| 0.0  | 2.18  | 0    | 0.458 | 6.430 | 58.7 | 6.0622 | 3   | 222 | 18.7    | 394.12 | 5.21  | 28.7 |
| ...    | ...  | ...   | ...  | ...   | ...   | ...  | ...    | ... | ... | ...     | ...    | ...   | ...  |

> The `boston` dataset contains housing data for various neighborhoods in Boston. It includes variables like:
- **crim**: Crime rate per capita
- **zn**: Proportion of residential land zoned for large lots
- **indus**: Proportion of non-retail business acres per town
- **chas**: Charles River dummy variable (1 if tract bounds river; 0 otherwise)
- **nox**: Nitric oxides concentration (parts per 10 million)
- **rm**: Average number of rooms per dwelling
- **age**: Proportion of owner-occupied units built prior to 1940
- **dis**: Weighted distances to employment centers
- **rad**: Index of accessibility to radial highways
- **tax**: Property tax rate per $10,000
- **ptratio**: Pupil-teacher ratio by town
- **black**: 1000(Bk - 0.63)^2 where Bk is the proportion of Black residents
- **lstat**: % lower status of the population
- **medv**: Median value of owner-occupied homes in $1000s

---

# 📂 Setting the Working Directory

```r
setwd("C:/Datasets")
```
Sets the working directory to the specified folder. All file paths will now refer to this location.

---

# 🏘 Boston Housing Dataset

```r
boston <- read.csv("Boston.csv")
str(boston)
```

### 🔍 Structure of `boston` Data Frame

- **Observations**: 506  
- **Variables**: 14

| Column     | Type  | Description                                      |
|------------|-------|--------------------------------------------------|
| crim       | num   | Crime rate by town                               |
| zn         | num   | Proportion of residential land zoned            |
| indus      | num   | Proportion of non-retail business acres         |
| chas       | int   | Charles River dummy variable (1 = bounds river) |
| nox        | num   | Nitric oxide concentration                       |
| rm         | num   | Average number of rooms per dwelling             |
| age        | num   | Proportion of owner-occupied units built before 1940 |
| dis        | num   | Weighted distances to employment centers        |
| rad        | int   | Index of accessibility to radial highways       |
| tax        | int   | Property tax rate                                |
| ptratio    | num   | Pupil-teacher ratio                              |
| black      | num   | Proportion of blacks                             |
| lstat      | num   | % lower status of the population                 |
| medv       | num   | Median value of owner-occupied homes (in $1000s) |

---

# 🎬 Bollywood Box Office Dataset (2015)

```r
bolyw <- read.csv("Bollywood_2015_2.csv", header = FALSE)
colnames(bolyw) <- c("movie_name", "BO", "Budget", "Verdict")
```

### 🎞 Sample Output

| movie_name              | BO     | Budget | Verdict              |
|-------------------------|--------|--------|----------------------|
| Pyaar Ka Punchnama 2    | 53.25  | 25.0   | Hit                  |
| Shandaar                | 38.28  | 68.0   | Flop                 |
| Singh is Bliing         | 74.87  | 92.0   | Flop                 |
| Talvar                  | 24.00  | 22.0   | Plus                 |
| Bajrangi Bhaijaan       | 318.14 | 125.0  | All Time Blockbuster |
| PK                      | 330.83 | 90.0   | All Time Blockbuster |
| Bombay Velvet           | 23.87  | 110.0  | Disaster             |

> 💡 Useful for: Analyzing profitability, comparing budgets with box office collections, and classification by verdict.

---

# 📈 Monthly Sales Data (`aster2.csv`)

```r
aster2 <- read.csv("aster2.csv")
aster2
```

### 📊 Sales by Month

| Month   | Sales |
|---------|-------|
| January | 17.5  |
| March   | 24.5  |
| April   | 25.1  |
| May     | 23.1  |

> 💡 Small dataset to explore basic data manipulation and visualization.

---

# 💎 Diamonds Dataset

```r
diamonds <- read.csv2("diamonds.csv")
diamonds
```

### 🔹 Sample Records

| carat | cut       | color | clarity | depth | table | price | x    | y    | z    |
|-------|-----------|-------|---------|-------|-------|-------|------|------|------|
| 0.23  | Ideal     | E     | SI2     | 61.5  | 55.0  | 326   | 3.95 | 3.98 | 2.43 |
| 0.21  | Premium   | E     | SI1     | 59.8  | 61.0  | 326   | 3.89 | 3.84 | 2.31 |
| 0.24  | Very Good | J     | VVS2    | 62.8  | 57.0  | 336   | 3.94 | 3.96 | 2.48 |
| 0.33  | Ideal     | J     | SI1     | 61.1  | 56.0  | 403   | 4.49 | 4.55 | 2.76 |

> 💡 Excellent dataset for practicing:
> - Descriptive statistics
> - Correlation
> - Data visualization
> - Regression analysis

---

# 📂 R Notes: File Input and Output

---

## 📘 Overview

R provides multiple ways to **import data** from files into data frames for analysis. The most common sources include:
- Flat files (CSV, TXT)
- Excel files (.xlsx)

---

## 📄 Reading Data from Flat Files

### ✅ Functions Used:
- `read.table()`
- `read.csv()`
- `read.csv2()`

---

## 🔹 `read.table()` – General Purpose File Reader

### ➤ Description:
- A flexible function to read tabular data.
- Supports custom delimiters and column configurations.
- Similar to `read.csv()` but with customizable defaults.

### 📌 Common Arguments:
| Argument           | Description                                                                 |
|--------------------|-----------------------------------------------------------------------------|
| `file`             | File path                                                                   |
| `header`           | `TRUE` if the first line contains column names                             |
| `row.names`        | Vector of row names                                                         |
| `col.names`        | Vector of column names                                                      |
| `colClasses`       | Vector indicating the class of each column (`"character"`, `"numeric"`, etc.) |
| `skip`             | Lines to skip at the top                                                    |
| `sep`              | Separator (default: whitespace)                                             |
| `stringsAsFactors` | Whether to convert strings to factors                                       |

---

### 🔍 Example

**members.txt**
```
List of Members
ID Name Age
1 Sanjay 40
2 Rahul  37
3 Dinesh 39
```

**Code**
```r
mem <- read.table(
  "C:/Datasets/members.txt",
  header = TRUE,
  colClasses = c("character", "character", "integer"),
  skip = 1,
  sep = " "
)
mem
```

**Output**
```
  ID   Name Age
1  1 Sanjay  40
2  2  Rahul  37
3  3 Dinesh  39
```

---

## 🔹 `read.csv()` – Reading Comma-Separated Files

### ➤ Description:
- Special case of `read.table()`.
- Assumes:
  - Comma `,` as separator.
  - Header is present in the file.

### 📌 Common Arguments:
| Argument           | Description                                                                 |
|--------------------|-----------------------------------------------------------------------------|
| `file`             | File path                                                                   |
| `header`           | Whether first line contains column names (`TRUE` by default)                |
| `sep`              | Separator (default: `,`)                                                    |
| `stringsAsFactors` | Logical indicating if strings should be converted to factors                |

---

### 🔍 Example

**Code**
```r
bollywood <- read.csv("C:/Datasets/Bollywood_2015.csv")
bollywood
```

**Partial Output**
```
               Movie_Name BO_Collection Budget   Box_Office_Verdict
1  Pyaar Ka Punchnama 2         53.25   25.0                  Hit
2              Shandaar         38.28   68.0                 Flop
3       Singh is Bliing         74.87   92.0                 Flop
...
52               Alone         17.29   18.0                 Flop
```

---

## 🔹 `read.csv2()` – Semi-Colon Separated Files

### ➤ Description:
- Similar to `read.csv()`, but:
  - Uses `;` as separator.
  - Suitable for European decimal formats.

### 📌 Common Arguments:
| Argument           | Description                                                                 |
|--------------------|-----------------------------------------------------------------------------|
| `file`             | File path                                                                   |
| `header`           | Logical for header presence                                                 |
| `sep`              | Separator (default: `;`)                                                    |
| `stringsAsFactors` | Logical for string-to-factor conversion                                     |

---

## 📊 Reading from Excel Files (.xlsx)

### ➤ Using `xlsx` package

### 📦 Installation & Loading:
```r
install.packages("xlsx")
library(xlsx)
```

### 🧾 Syntax:
```r
read.xlsx(file, sheetIndex)
```
- `file`: Excel file path
- `sheetIndex`: Sheet number (e.g., 1, 2, 3...)

---

### 🔍 Example

**Code**
```r
bank <- read.xlsx("C:/Datasets/bankruptcy.xlsx", 3)
bank
```

**Partial Output**
```
   NO D YR   R1   R2   R3   R4    R5    R6    R7    R8   R9  R10  R11  R12
1   1 0 78 0.23 0.08 0.02 0.03  0.46  0.12  0.19 10.36 1.17 0.40 0.10 0.14
2   2 0 77 0.19 0.07 0.09 0.12  0.02  0.02  0.03  3.13 1.73 0.60 0.78 0.63
3   3 0 72 0.07 0.02 0.03 0.05  0.06  0.10  0.14  2.41 1.36 0.41 0.66 0.70
...
```

---

## ✅ Summary

| Function         | Default Separator | Excel Support | Default Header | Special Use |
|------------------|-------------------|---------------|----------------|--------------|
| `read.table()`   | Whitespace        | ❌            | FALSE          | General file reading |
| `read.csv()`     | Comma `,`         | ❌            | TRUE           | CSV files     |
| `read.csv2()`    | Semicolon `;`     | ❌            | TRUE           | European CSVs |
| `read.xlsx()`    | N/A               | ✅            | YES            | Excel sheets  |

---

# 📘 R Programming Notes (with Output)

## 📦 Loading Packages

```r
library(readxl)
```

> ⚠️ Warning: `package ‘readxl’ was built under R version 4.4.3`

---

## 📄 Reading Excel Files

```r
quality <- read_excel("quality.xlsx")
```

> New column names:
- `Id` → `Id...1`
- Empty headers → `...5`, `...6`, `...7`
- Second `Id` → `Id...8`

```r
quality
```

```
# A tibble: 15 × 10
   Id...1 `Policy A` `Policy B` `Policy C` ...5  ...6  ...7  Id...8 Policy   Value
    <dbl>      <dbl>      <dbl>      <dbl> <lgl> <lgl> <lgl>  <dbl> <chr>    <dbl>
 1      1         97         93         99 NA    NA    NA         1 Policy A    97
 2      2         73         14         94 NA    NA    NA         2 Policy A    73
 ...
15     NA         NA         NA         NA NA    NA    NA         5 Policy C    59
```

### 🎯 Reading Specific Ranges

```r
qual1 <- read_excel("quality.xlsx", range = "A1:C6", sheet = "quality")
```

```r
qual1
```

```
# A tibble: 5 × 3
     Id `Policy A` `Policy B`
  <dbl>      <dbl>      <dbl>
1     1         97         93
...
5     5         23         77
```

```r
qual2 <- read_excel("quality.xlsx", range = "H1:J16", sheet = "quality")
```

```r
qual2
```

```
# A tibble: 15 × 3
     Id Policy   Value
  <dbl> <chr>    <dbl>
1     1 Policy A    97
...
15    5 Policy C    59
```

---

## 📁 Built-in Dataset: Formaldehyde

```r
data("Formaldehyde")
Formaldehyde
```

```
  carb optden
1  0.1  0.086
...
6  0.9  0.782
```

### 💾 Writing to CSV and Excel

```r
write.csv(Formaldehyde, "C:/Datasets/Formaldehyde.csv", row.names = FALSE)

library(writexl)
write_xlsx(Formaldehyde, "C:/Datasets/Formal.xlsx")
```

---

## 🔎 Subsetting Data in R

### ✅ Vectors

```r
x <- c(12, 23, 52, 78, 90, 10, 28, 93, 95, 92, 95, 79)
x[1:5]
```

```
[1] 12 23 52 78 90
```

```r
x > 50
x[x > 50]
```

```
[1] FALSE FALSE  TRUE ...
[1] 52 78 90 93 95 92 95 79
```

---

### ✅ Lists

```r
f <- list(a=1:7, b="XYZ", c=FALSE, d=c(23.4,14,6))
f[1]       # List with element a
f[2]       # List with element b
f$c        # Access using $
f[["c"]]   # Access using [[]]
f["c"]     # Subset list
```

```
$a
[1] 1 2 3 4 5 6 7

$b
[1] "XYZ"

[1] FALSE
```

---

### ✅ Matrices

```r
m <- matrix(c(1:12), 4, 3)
m
```

```
     [,1] [,2] [,3]
[1,]    1    5    9
[2,]    2    6   10
...
```

```r
m[3, 2]
m[2, ]
m[, 3]
m[, 3, drop = FALSE]
```

```
[1] 7
[1]  2  6 10
[1]  9 10 11 12
     [,1]
[1,]    9
...
```

---

### ✅ Data Frames

```r
Formaldehyde[2, ]
Formaldehyde[c(1, 4, 6), ]
Formaldehyde[c(1, 4, 6), 2]
```

```
  carb optden
2  0.3  0.269

  carb optden
1  0.1  0.086
4  0.6  0.538
6  0.9  0.782

[1] 0.086 0.538 0.782
```

---

## 📌 `subset()` Function

Syntax:  
```r
subset(data_frame, condition, select)
```

### Example with `diamonds` Dataset

```r
subset(diamonds, cut == "Ideal", select = c(carat, price))
```

(Truncated data shown in your output, full display omitted for brevity)

---

## 📂 Writing Data to Files

- `write.table(df, "path")`
- `write.csv(df, "path")`

---

## 📊 Extracting Specific Columns in R using `[` Operator

In R, you can extract specific columns from a data frame using the square bracket notation `[,]`. Here's how you can extract the **3rd** and **4th** columns (in this case, `color` and `clarity`) from the `diamonds` dataset:

### ✅ Code
```r
diamonds[, c(3, 4)]
```

This selects **all rows** from the **3rd and 4th columns** of the dataset.

---

### 🖨️ Output (Partial View - First 10 Rows)

```r
   color clarity
1      E     SI2
2      E     SI1
3      E     VS1
4      I     VS2
5      J     SI2
6      J    VVS2
7      I    VVS1
8      H     SI1
9      E     VS2
10     H     VS1
```

---

### 🧠 Understanding the Output

- **color**: Represents the color grade of the diamond, ranging from D (best) to J (least).
- **clarity**: Describes the purity of the diamond (e.g., FL, IF, VVS1, VVS2, VS1, VS2, SI1, SI2, I1).

Both columns are **categorical variables** useful for visualizations and grouping.

---

### 📝 Learning Tip

If you're interested in viewing only a subset of rows, like the first 10:
```r
diamonds[1:10, c(3, 4)]
```

If you're unsure of column positions, use `names(diamonds)` to view all column names:
```r
names(diamonds)
```
---

# 📘 **R Notes: Subset with Conditions (`subset()` Function)**

## 🎯 **Objective**
Extract records from the `diamonds` dataset where:
- `cut` is `"Ideal"`
- `price` is greater than `2000`

---

## 🧪 **Code Used**
```r
ss3 <- subset(diamonds, cut == "Ideal" & price > 2000)
ss3
```

---

## 📊 **Explanation**

- `subset()` is used to filter rows from a data frame based on conditions.
- Here, we are:
  - Selecting only diamonds with `"Ideal"` cut.
  - Further filtering where the `price` is greater than 2000.

---

## 📥 **Sample Output (`ss3`)**

| carat | cut  | color | clarity | depth | table | price |   x   |   y   |   z   |
|-------|------|-------|---------|-------|-------|-------|-------|-------|-------|
| 0.70  | Ideal| E     | SI1     | 62.5  | 57    | 2757  | 5.70  | 5.72  | 3.57  |
| 0.70  | Ideal| G     | VS2     | 61.6  | 56    | 2757  | 5.70  | 5.67  | 3.50  |
| 0.74  | Ideal| G     | SI1     | 61.6  | 55    | 2760  | 5.80  | 5.85  | 3.59  |
| 0.80  | Ideal| I     | VS1     | 62.9  | 56    | 2760  | 5.94  | 5.87  | 3.72  |
| ...   | ...  | ...   | ...     | ...   | ...   | ...   | ...   | ...   | ...   |

> ✅ Output truncated: total rows = 109 (only sample shown for clarity)

---

## 🔍 **Quick Tips**

- `&` = AND condition. Use `|` for OR.
- Always verify column names with `names(diamonds)` if unsure.
- Use `head(ss3)` or `View(ss3)` for better visibility when data is large.

---

## 🧠 **Use Cases**
- Filter high-quality diamonds for analysis.
- Combine multiple filtering criteria efficiently.

---
