## 🔁 `ifelse()` – Functional Conditional Operator

### 📌 Description:
- A **vectorized** form of `if...else`.
- Syntax:
  ```r
  ifelse(condition, value_if_true, value_if_false)
  ```

### ✅ Example 1:

```r
v <- c(23, 13, 9, 24, 9, 3, 14, 8, 18, 20)
result <- ifelse(v > 10, "Pass", "Fail")
result
```

**Output:**

```r
[1] "Pass" "Pass" "Fail" "Pass" "Fail"
[6] "Fail" "Pass" "Fail" "Pass" "Pass"
```

---

### ✅ Example 2: Using `ifelse()` with `mtcars`

```r
# This fails because `if` expects a single logical value
# if (mtcars$mpg > 25) { print("Good Mileage") }

# Use vectorized ifelse instead
ifelse(mtcars$mpg > 25, "Good Mileage", "OK Mileage")
```

**Output (truncated):**

```r
[1] "OK Mileage"   "OK Mileage"   ...
[18] "Good Mileage" ...
```

### ✅ Create New Column Using `ifelse()`

```r
mtcars$mileage <- ifelse(mtcars$mpg > 25, "Good Mileage", "OK Mileage")
```

**New column added:**

| Model            | mpg  | mileage       |
|------------------|------|---------------|
| Mazda RX4        | 21.0 | OK Mileage    |
| Fiat 128         | 32.4 | Good Mileage  |
| Toyota Corolla   | 33.9 | Good Mileage  |
| Lotus Europa     | 30.4 | Good Mileage  |
| ...              | ...  | ...           |

---

## 📊 Mean, Variance, and Standard Deviation

### 📌 Functions:
- `mean()` – Arithmetic mean
- `sd()` – Standard deviation
- `var()` – Variance

### ✅ Examples:

```r
mean(mtcars$mpg, na.rm = TRUE)
sd(mtcars$mpg)
var(mtcars$mpg)
```

**Output:**

```r
> mean(mtcars$mpg)
[1] 20.09062

> sd(mtcars$mpg)
[1] 6.026948

> var(mtcars$mpg)
[1] 36.3241
```

---

## 📊 `summary()` – Statistical Summary of Data

### ✅ Numeric Vectors

```r
summary(mtcars$mpg)
```

**Output:**

```r
   Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
  10.4   15.43    19.2    20.09   22.8    33.9 
```

### ✅ Whole Data Frame

```r
summary(mtcars)
summary(airquality)
```

### ✅ Categorical Variables

```r
summary(c2018$Transmission)
```

**Output:**

```r
Automatic       CVT    Manual 
      760        85       299 
```

---

## 📦 `attach()` and `detach()`

### 📌 Use `attach()` to access variables in a dataset **without `$`**.

```r
attach(mtcars)
mean(mpg)
detach(mtcars)
```

After detaching:

```r
mean(mpg)  # Error: object 'mpg' not found
```

> 💡 Use with caution: avoid naming conflicts and always `detach()` after use.

---

## 🧰 Creating Functions in R

### 📘 Syntax:

```r
function_name <- function(arguments) {
  # function body
  return(output)
}
```

---

### ✅ Function Examples

#### ➕ Sum of Three Numbers

```r
add <- function(a, b, c) {
  return(a + b + c)
}

add(2, 4, 6)  # [1] 12
```

---

#### 📊 Descriptive Stats (Mean & SD)

```r
descriptive <- function(input) {
  df <- data.frame(
    Mean = mean(input, na.rm = TRUE),
    SD = sd(input, na.rm = TRUE)
  )
  return(df)
}

descriptive(mtcars$mpg)
```

**Output:**

| Mean     | SD       |
|----------|----------|
| 20.09062 | 6.026948 |

---

#### 🌡️ Fahrenheit to Celsius

```r
ftoC <- function(temp) {
  (temp - 32) * (5/9)
}

ftoC(100)  # [1] 37.77778
```

---

#### 🌡️ Celsius to Fahrenheit

```r
ctoF <- function(temp) {
  (temp * 9/5) + 32
}

ctoF(37.77778)  # [1] 100
```

---

#### 🧊 Cube of a Number

```r
cube <- function(num) {
  return(num^3)
}

cube(5)  # [1] 125
```

---

#### 💰 Simple Interest Calculator

```r
simple <- function(p, r, n) {
  return((p * r * n) / 100)
}

simple(10000, 10, 2)  # [1] 2000
```

---

### ✅ Using Vectors in Functions (Vectorized)

```r
principal <- c(10000, 20000, 30000, 40000, 50000)
rate <- c(10, 8, 12, 15, 20)
time <- c(2, 4, 5, 3, 7)

simple(principal, rate, time)
```

**Output:**

```r
[1]  2000  6400 18000 18000 70000
```

> 🔁 Similar to **NumPy broadcasting** in Python.

---

## ✅ Quick Recap Table

| Topic                | Function / Usage                     |
|----------------------|--------------------------------------|
| Vector if-else       | `ifelse()`                           |
| Descriptive stats    | `mean()`, `sd()`, `var()`, `summary()` |
| Category counts      | `table()`                            |
| Attach variables     | `attach()` / `detach()`              |
| Custom functions     | `function() {}`                      |
| Temperature convert  | `ftoC()`, `ctoF()`                   |
| Simple interest      | `simple(p, r, n)`                    |

---

## 📦 `dplyr` Basics: Installation, Import, and Usage

### ✅ Installing & Loading `dplyr`

```r
install.packages("dplyr")
library(dplyr)
```

> ⚠️ If prompted about **Rtools**, install it from:  
> https://cran.rstudio.com/bin/windows/Rtools/

---

## 📋 `tibble` – A Modern Data Frame

```r
class(mtcars)  # [1] "data.frame"

tbl_cars <- as_tibble(mtcars)
class(tbl_cars)
# [1] "tbl_df"     "tbl"        "data.frame"
```

> `tibble` is just a fancy data frame: cleaner printing and easier with `dplyr`.

---

## 🔃 `arrange()` – Sort Rows

### 🔼 Ascending Order:

```r
ssl <- arrange(mtcars, mpg)
```

> Sorts by `mpg` in **increasing** order.

### 🔽 Descending Order:

```r
ssl <- arrange(mtcars, desc(mpg))
```

> Sorts by `mpg` in **decreasing** order.

### ➕ Multiple Sort Keys (like SQL `ORDER BY mpg DESC, cyl ASC`):

```r
ssl <- arrange(mtcars, desc(mpg), cyl)
```

---

## 📌 `select()` – Choose Columns

### ✅ Select Specific Columns:

```r
select(mtcars, mpg, wt, am)
```

### ✅ Select Column Range:

```r
select(mtcars, mpg:wt)
```

> Includes columns from `mpg` to `wt` (inclusive).

---

## 🔍 Select by Column Name Pattern

### Columns Starting With:

```r
select(mtcars, starts_with("d"))
```

> Selects `disp`, `drat`.

### Columns Containing:

```r
select(mtcars, contains("t"))
```

> Selects `drat`, `wt`.

---

## 🧠 `dplyr` Cheat Sheet

| Function       | Purpose                               | Example                             |
|----------------|---------------------------------------|-------------------------------------|
| `arrange()`    | Sort rows                             | `arrange(df, var)`                  |
| `desc()`       | Descending order inside `arrange()`   | `arrange(df, desc(var))`            |
| `select()`     | Select columns                        | `select(df, col1, col2)`            |
| `starts_with()`| Select columns starting with string   | `select(df, starts_with("mp"))`     |
| `contains()`   | Select columns containing string      | `select(df, contains("t"))`         |

---

## 💡 Quick Notes

- `arrange()` is like **SQL ORDER BY**
- `select()` is like **SQL SELECT columns**
- `desc()` is used inside `arrange()` for descending order
- Use `as_tibble()` to work with cleaner output

# 🔍 dplyr Data Manipulation Functions

## 🎯 Subsetting with `filter()`
### Extract rows that meet specific conditions

**Basic Filtering**:
```r
> filter(mtcars, mpg > 30)
                mpg cyl disp  hp drat    wt  qsec vs am gear carb      mileage
Fiat 128       32.4   4 78.7  66 4.08 2.200 19.47  1  1    4    1 Good Mileage
Honda Civic    30.4   4 75.7  52 4.93 1.615 18.52  1  1    4    2 Good Mileage
Toyota Corolla 33.9   4 71.1  65 4.22 1.835 19.90  1  1    4    1 Good Mileage
Lotus Europa   30.4   4 95.1 113 3.77 1.513 16.90  1  1    5    2 Good Mileage
```

**Multiple Conditions** (comma = AND operator):
```r
> filter(select(mtcars, mpg, wt, hp, am), mpg > 30, hp > 60)
                mpg    wt  hp am
Fiat 128       32.4 2.200  66  1
Toyota Corolla 33.9 1.835  65  1
Lotus Europa   30.4 1.513 113  1
```

**Key Points**:
- Returns all columns by default
- Use `select()` inside `filter()` to limit columns
- Multiple conditions are ANDed together
- Use `|` for OR conditions

---

## 🏷️ Renaming Columns with `rename()`
### Change column names without modifying data

```r
> rename(mtcars, milage = mpg, weight = wt)
                    milage cyl  disp  hp drat weight  qsec vs am gear carb      mileage
Mazda RX4             21.0   6 160.0 110 3.90  2.620 16.46  0  1    4    4   OK Mileage
...
Fiat 128              32.4   4  78.7  66 4.08  2.200 19.47  1  1    4    1 Good Mileage
```

**Syntax**: `rename(data, new_name = old_name, ...)`
- Returns all columns, only changing specified names
- Non-standard evaluation (no quotes needed)

---

## ➕ Creating Columns with `mutate()`
### Add new columns while preserving existing ones

**Basic Usage**:
```r
> mutate(mtcars, ratio = mpg/hp)
                     mpg cyl  disp  hp ...      ratio
Mazda RX4           21.0   6 160.0 110     0.19090909
...
Fiat 128            32.4   4  78.7  66     0.49090909
```

**With Rounding**:
```r
> select(mutate(mtcars, ratio = round(mpg/hp, 1)), mpg, wt, ratio, hp)
                     mpg    wt ratio  hp
Mazda RX4           21.0 2.620   0.2 110
...
Fiat 128            32.4 2.200   0.5  66
```

**Key Features**:
- Creates temporary columns (not saved to original data)
- Can reference newly created columns in same call
- Use `transmute()` to keep only new columns
- Multiple operations can be chained with `%>%`

---

## 💡 Pro Tips

1. **Combining Operations**:
   ```r
   mtcars %>%
     filter(cyl == 4) %>%
     mutate(ratio = mpg/hp) %>%
     select(mpg, hp, ratio)
   ```

2. **Common Mistakes**:
   - Forgetting that `mutate()` doesn't modify original data
   - Confusing `=` (assignment) with `==` (comparison) in filters
   - Not using `round()` when creating ratio/difference columns

3. **Performance**:
   - `filter()` first to reduce data size before complex operations
   - Use `between()` for range filters instead of `x > a & x < b`

# 📊 Data Summarization with dplyr

## 🔍 Custom Summaries with `summarise()`
### Create tailored summary statistics

**Basic Summary**:
```r
> summarise(mtcars, avg_disp = mean(disp), sd_disp = sd(disp))
  avg_disp  sd_disp
1 230.7219 123.9387
```

**Multiple Metrics**:
```r
> summarise(mtcars, 
           avg_disp = mean(disp), 
           sd_disp = sd(disp), 
           avg_mpg = mean(mpg), 
           sd_mpg = sd(mpg))
  avg_disp  sd_disp  avg_mpg   sd_mpg
1 230.7219 123.9387 20.09062 6.026948
```

**Key Features**:
- Calculates one row of summary statistics
- Can compute multiple metrics in one call
- Handles NA values with `na.rm = TRUE` parameter

---

## 🏷️ Grouped Operations with `group_by()`
### SQL-like group aggregations

**Grouped Summary**:
```r
> grp_cyl <- group_by(mtcars, cyl)
> summarise(grp_cyl, avg_mpg = mean(mpg))
# A tibble: 3 × 2
    cyl avg_mpg
  <dbl>   <dbl>
1     4    26.7
2     6    19.7
3     8    15.1
```

**SQL Equivalent**:
```sql
SELECT cyl, avg(mpg) as avg_mpg
FROM mtcars
GROUP BY cyl;
```

**Common Grouping Functions**:
- `n()`: Count observations per group
- `first()`, `last()`: Get first/last value
- `quantile()`: Calculate percentiles

---

## ⛓️ Pipelining with `%>%` and `|>`
### Chain operations elegantly

**Magrittr Pipe (`%>%`)**:
```r
mtcars %>%
  group_by(cyl) %>%
  summarise(avg_mpg = mean(mpg))
```

**Native Pipe (`|>`, R 4.1+)**:
```r
mtcars |>
  select(mpg, wt, hp, am) |>
  filter(mpg > 30)
```

**Output**:
```
               mpg    wt  hp am
Fiat 128       32.4 2.200  66  1
Honda Civic    30.4 1.615  52  1
Toyota Corolla 33.9 1.835  65  1
Lotus Europa   30.4 1.513 113  1
```

**Pipe Benefits**:
1. Avoid nested function calls
2. Read left-to-right (vs inside-out)
3. Easy to add/remove steps
4. Visualize data transformation flow

---

## 💡 Pro Tips

1. **Common Summary Functions**:
   - Central tendency: `mean()`, `median()`
   - Spread: `sd()`, `IQR()`, `mad()`
   - Range: `min()`, `max()`, `quantile()`
   - Count: `n()`, `n_distinct()`

2. **Grouping Multiple Columns**:
   ```r
   mtcars %>%
     group_by(cyl, am) %>%
     summarise(avg_mpg = mean(mpg))
   ```

3. **After Grouping**:
   - Use `ungroup()` when done with grouped operations
   - `mutate()` after `group_by()` works within groups

4. **Piping Best Practices**:
   - Line break after each pipe
   - Indent subsequent lines
   - Comment complex steps
