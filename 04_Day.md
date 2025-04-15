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

---

You're all set with `dplyr`'s foundation — next, we can dive into:
- `filter()`: row filtering (like `WHERE` in SQL)
- `mutate()`: creating/modifying columns
- `summarise()` + `group_by()`: groupwise summary stats
- Pipelining with `%>%` (pipe operator)

> 
> #_______________________________________________________________________
> 
> # Subsetting the Data (Filter)
> 
> filter(mtcars, mpg > 30)
                mpg cyl disp  hp drat    wt  qsec vs am gear carb      mileage
Fiat 128       32.4   4 78.7  66 4.08 2.200 19.47  1  1    4    1 Good Mileage
Honda Civic    30.4   4 75.7  52 4.93 1.615 18.52  1  1    4    2 Good Mileage
Toyota Corolla 33.9   4 71.1  65 4.22 1.835 19.90  1  1    4    1 Good Mileage
Lotus Europa   30.4   4 95.1 113 3.77 1.513 16.90  1  1    5    2 Good Mileage
> 
> filter(select(mtcars, mpg, wt, hp, am), mpg > 30, hp > 60)
                mpg    wt  hp am
Fiat 128       32.4 2.200  66  1
Toyota Corolla 33.9 1.835  65  1
Lotus Europa   30.4 1.513 113  1
> 
> #__________________________________________________________________________
> 
> # Rename Column Names
> 
> rename(mtcars, milage = mpg, weight = wt)
                    milage cyl  disp  hp drat weight  qsec vs am gear carb      mileage
Mazda RX4             21.0   6 160.0 110 3.90  2.620 16.46  0  1    4    4   OK Mileage
Mazda RX4 Wag         21.0   6 160.0 110 3.90  2.875 17.02  0  1    4    4   OK Mileage
Datsun 710            22.8   4 108.0  93 3.85  2.320 18.61  1  1    4    1   OK Mileage
Hornet 4 Drive        21.4   6 258.0 110 3.08  3.215 19.44  1  0    3    1   OK Mileage
Hornet Sportabout     18.7   8 360.0 175 3.15  3.440 17.02  0  0    3    2   OK Mileage
Valiant               18.1   6 225.0 105 2.76  3.460 20.22  1  0    3    1   OK Mileage
Duster 360            14.3   8 360.0 245 3.21  3.570 15.84  0  0    3    4   OK Mileage
Merc 240D             24.4   4 146.7  62 3.69  3.190 20.00  1  0    4    2   OK Mileage
Merc 230              22.8   4 140.8  95 3.92  3.150 22.90  1  0    4    2   OK Mileage
Merc 280              19.2   6 167.6 123 3.92  3.440 18.30  1  0    4    4   OK Mileage
Merc 280C             17.8   6 167.6 123 3.92  3.440 18.90  1  0    4    4   OK Mileage
Merc 450SE            16.4   8 275.8 180 3.07  4.070 17.40  0  0    3    3   OK Mileage
Merc 450SL            17.3   8 275.8 180 3.07  3.730 17.60  0  0    3    3   OK Mileage
Merc 450SLC           15.2   8 275.8 180 3.07  3.780 18.00  0  0    3    3   OK Mileage
Cadillac Fleetwood    10.4   8 472.0 205 2.93  5.250 17.98  0  0    3    4   OK Mileage
Lincoln Continental   10.4   8 460.0 215 3.00  5.424 17.82  0  0    3    4   OK Mileage
Chrysler Imperial     14.7   8 440.0 230 3.23  5.345 17.42  0  0    3    4   OK Mileage
Fiat 128              32.4   4  78.7  66 4.08  2.200 19.47  1  1    4    1 Good Mileage
Honda Civic           30.4   4  75.7  52 4.93  1.615 18.52  1  1    4    2 Good Mileage
Toyota Corolla        33.9   4  71.1  65 4.22  1.835 19.90  1  1    4    1 Good Mileage
Toyota Corona         21.5   4 120.1  97 3.70  2.465 20.01  1  0    3    1   OK Mileage
Dodge Challenger      15.5   8 318.0 150 2.76  3.520 16.87  0  0    3    2   OK Mileage
AMC Javelin           15.2   8 304.0 150 3.15  3.435 17.30  0  0    3    2   OK Mileage
Camaro Z28            13.3   8 350.0 245 3.73  3.840 15.41  0  0    3    4   OK Mileage
Pontiac Firebird      19.2   8 400.0 175 3.08  3.845 17.05  0  0    3    2   OK Mileage
Fiat X1-9             27.3   4  79.0  66 4.08  1.935 18.90  1  1    4    1 Good Mileage
Porsche 914-2         26.0   4 120.3  91 4.43  2.140 16.70  0  1    5    2 Good Mileage
Lotus Europa          30.4   4  95.1 113 3.77  1.513 16.90  1  1    5    2 Good Mileage
Ford Pantera L        15.8   8 351.0 264 4.22  3.170 14.50  0  1    5    4   OK Mileage
Ferrari Dino          19.7   6 145.0 175 3.62  2.770 15.50  0  1    5    6   OK Mileage
Maserati Bora         15.0   8 301.0 335 3.54  3.570 14.60  0  1    5    8   OK Mileage
Volvo 142E            21.4   4 121.0 109 4.11  2.780 18.60  1  1    4    2   OK Mileage
> 
> # Here, mpg is renamed to milage and wt to weight
> 
> #__________________________________________________________________________
> 
> # Creating / Adding New Column
> 
> mutate(mtcars, ratio = mpg/hp)
                     mpg cyl  disp  hp drat    wt  qsec vs am gear carb      mileage      ratio
Mazda RX4           21.0   6 160.0 110 3.90 2.620 16.46  0  1    4    4   OK Mileage 0.19090909
Mazda RX4 Wag       21.0   6 160.0 110 3.90 2.875 17.02  0  1    4    4   OK Mileage 0.19090909
Datsun 710          22.8   4 108.0  93 3.85 2.320 18.61  1  1    4    1   OK Mileage 0.24516129
Hornet 4 Drive      21.4   6 258.0 110 3.08 3.215 19.44  1  0    3    1   OK Mileage 0.19454545
Hornet Sportabout   18.7   8 360.0 175 3.15 3.440 17.02  0  0    3    2   OK Mileage 0.10685714
Valiant             18.1   6 225.0 105 2.76 3.460 20.22  1  0    3    1   OK Mileage 0.17238095
Duster 360          14.3   8 360.0 245 3.21 3.570 15.84  0  0    3    4   OK Mileage 0.05836735
Merc 240D           24.4   4 146.7  62 3.69 3.190 20.00  1  0    4    2   OK Mileage 0.39354839
Merc 230            22.8   4 140.8  95 3.92 3.150 22.90  1  0    4    2   OK Mileage 0.24000000
Merc 280            19.2   6 167.6 123 3.92 3.440 18.30  1  0    4    4   OK Mileage 0.15609756
Merc 280C           17.8   6 167.6 123 3.92 3.440 18.90  1  0    4    4   OK Mileage 0.14471545
Merc 450SE          16.4   8 275.8 180 3.07 4.070 17.40  0  0    3    3   OK Mileage 0.09111111
Merc 450SL          17.3   8 275.8 180 3.07 3.730 17.60  0  0    3    3   OK Mileage 0.09611111
Merc 450SLC         15.2   8 275.8 180 3.07 3.780 18.00  0  0    3    3   OK Mileage 0.08444444
Cadillac Fleetwood  10.4   8 472.0 205 2.93 5.250 17.98  0  0    3    4   OK Mileage 0.05073171
Lincoln Continental 10.4   8 460.0 215 3.00 5.424 17.82  0  0    3    4   OK Mileage 0.04837209
Chrysler Imperial   14.7   8 440.0 230 3.23 5.345 17.42  0  0    3    4   OK Mileage 0.06391304
Fiat 128            32.4   4  78.7  66 4.08 2.200 19.47  1  1    4    1 Good Mileage 0.49090909
Honda Civic         30.4   4  75.7  52 4.93 1.615 18.52  1  1    4    2 Good Mileage 0.58461538
Toyota Corolla      33.9   4  71.1  65 4.22 1.835 19.90  1  1    4    1 Good Mileage 0.52153846
Toyota Corona       21.5   4 120.1  97 3.70 2.465 20.01  1  0    3    1   OK Mileage 0.22164948
Dodge Challenger    15.5   8 318.0 150 2.76 3.520 16.87  0  0    3    2   OK Mileage 0.10333333
AMC Javelin         15.2   8 304.0 150 3.15 3.435 17.30  0  0    3    2   OK Mileage 0.10133333
Camaro Z28          13.3   8 350.0 245 3.73 3.840 15.41  0  0    3    4   OK Mileage 0.05428571
Pontiac Firebird    19.2   8 400.0 175 3.08 3.845 17.05  0  0    3    2   OK Mileage 0.10971429
Fiat X1-9           27.3   4  79.0  66 4.08 1.935 18.90  1  1    4    1 Good Mileage 0.41363636
Porsche 914-2       26.0   4 120.3  91 4.43 2.140 16.70  0  1    5    2 Good Mileage 0.28571429
Lotus Europa        30.4   4  95.1 113 3.77 1.513 16.90  1  1    5    2 Good Mileage 0.26902655
Ford Pantera L      15.8   8 351.0 264 4.22 3.170 14.50  0  1    5    4   OK Mileage 0.05984848
Ferrari Dino        19.7   6 145.0 175 3.62 2.770 15.50  0  1    5    6   OK Mileage 0.11257143
Maserati Bora       15.0   8 301.0 335 3.54 3.570 14.60  0  1    5    8   OK Mileage 0.04477612
Volvo 142E          21.4   4 121.0 109 4.11 2.780 18.60  1  1    4    2   OK Mileage 0.19633028
> select(mutate(mtcars, ratio = round(mpg/hp, 1)), mpg, wt, ratio, hp)
                     mpg    wt ratio  hp
Mazda RX4           21.0 2.620   0.2 110
Mazda RX4 Wag       21.0 2.875   0.2 110
Datsun 710          22.8 2.320   0.2  93
Hornet 4 Drive      21.4 3.215   0.2 110
Hornet Sportabout   18.7 3.440   0.1 175
Valiant             18.1 3.460   0.2 105
Duster 360          14.3 3.570   0.1 245
Merc 240D           24.4 3.190   0.4  62
Merc 230            22.8 3.150   0.2  95
Merc 280            19.2 3.440   0.2 123
Merc 280C           17.8 3.440   0.1 123
Merc 450SE          16.4 4.070   0.1 180
Merc 450SL          17.3 3.730   0.1 180
Merc 450SLC         15.2 3.780   0.1 180
Cadillac Fleetwood  10.4 5.250   0.1 205
Lincoln Continental 10.4 5.424   0.0 215
Chrysler Imperial   14.7 5.345   0.1 230
Fiat 128            32.4 2.200   0.5  66
Honda Civic         30.4 1.615   0.6  52
Toyota Corolla      33.9 1.835   0.5  65
Toyota Corona       21.5 2.465   0.2  97
Dodge Challenger    15.5 3.520   0.1 150
AMC Javelin         15.2 3.435   0.1 150
Camaro Z28          13.3 3.840   0.1 245
Pontiac Firebird    19.2 3.845   0.1 175
Fiat X1-9           27.3 1.935   0.4  66
Porsche 914-2       26.0 2.140   0.3  91
Lotus Europa        30.4 1.513   0.3 113
Ford Pantera L      15.8 3.170   0.1 264
Ferrari Dino        19.7 2.770   0.1 175
Maserati Bora       15.0 3.570   0.0 335
Volvo 142E          21.4 2.780   0.2 109
> mtcars
                     mpg cyl  disp  hp drat    wt  qsec vs am gear carb      mileage
Mazda RX4           21.0   6 160.0 110 3.90 2.620 16.46  0  1    4    4   OK Mileage
Mazda RX4 Wag       21.0   6 160.0 110 3.90 2.875 17.02  0  1    4    4   OK Mileage
Datsun 710          22.8   4 108.0  93 3.85 2.320 18.61  1  1    4    1   OK Mileage
Hornet 4 Drive      21.4   6 258.0 110 3.08 3.215 19.44  1  0    3    1   OK Mileage
Hornet Sportabout   18.7   8 360.0 175 3.15 3.440 17.02  0  0    3    2   OK Mileage
Valiant             18.1   6 225.0 105 2.76 3.460 20.22  1  0    3    1   OK Mileage
Duster 360          14.3   8 360.0 245 3.21 3.570 15.84  0  0    3    4   OK Mileage
Merc 240D           24.4   4 146.7  62 3.69 3.190 20.00  1  0    4    2   OK Mileage
Merc 230            22.8   4 140.8  95 3.92 3.150 22.90  1  0    4    2   OK Mileage
Merc 280            19.2   6 167.6 123 3.92 3.440 18.30  1  0    4    4   OK Mileage
Merc 280C           17.8   6 167.6 123 3.92 3.440 18.90  1  0    4    4   OK Mileage
Merc 450SE          16.4   8 275.8 180 3.07 4.070 17.40  0  0    3    3   OK Mileage
Merc 450SL          17.3   8 275.8 180 3.07 3.730 17.60  0  0    3    3   OK Mileage
Merc 450SLC         15.2   8 275.8 180 3.07 3.780 18.00  0  0    3    3   OK Mileage
Cadillac Fleetwood  10.4   8 472.0 205 2.93 5.250 17.98  0  0    3    4   OK Mileage
Lincoln Continental 10.4   8 460.0 215 3.00 5.424 17.82  0  0    3    4   OK Mileage
Chrysler Imperial   14.7   8 440.0 230 3.23 5.345 17.42  0  0    3    4   OK Mileage
Fiat 128            32.4   4  78.7  66 4.08 2.200 19.47  1  1    4    1 Good Mileage
Honda Civic         30.4   4  75.7  52 4.93 1.615 18.52  1  1    4    2 Good Mileage
Toyota Corolla      33.9   4  71.1  65 4.22 1.835 19.90  1  1    4    1 Good Mileage
Toyota Corona       21.5   4 120.1  97 3.70 2.465 20.01  1  0    3    1   OK Mileage
Dodge Challenger    15.5   8 318.0 150 2.76 3.520 16.87  0  0    3    2   OK Mileage
AMC Javelin         15.2   8 304.0 150 3.15 3.435 17.30  0  0    3    2   OK Mileage
Camaro Z28          13.3   8 350.0 245 3.73 3.840 15.41  0  0    3    4   OK Mileage
Pontiac Firebird    19.2   8 400.0 175 3.08 3.845 17.05  0  0    3    2   OK Mileage
Fiat X1-9           27.3   4  79.0  66 4.08 1.935 18.90  1  1    4    1 Good Mileage
Porsche 914-2       26.0   4 120.3  91 4.43 2.140 16.70  0  1    5    2 Good Mileage
Lotus Europa        30.4   4  95.1 113 3.77 1.513 16.90  1  1    5    2 Good Mileage
Ford Pantera L      15.8   8 351.0 264 4.22 3.170 14.50  0  1    5    4   OK Mileage
Ferrari Dino        19.7   6 145.0 175 3.62 2.770 15.50  0  1    5    6   OK Mileage
Maserati Bora       15.0   8 301.0 335 3.54 3.570 14.60  0  1    5    8   OK Mileage
Volvo 142E          21.4   4 121.0 109 4.11 2.780 18.60  1  1    4    2   OK Mileage
> 
> # Permanent column is not created
> 
> #__________________________________________________________________________
> 
> # Summarise the data
> 
> # summary(data) #Earlier Method
> 
> # Now, we want a customized summary, so we use summarise function
> 
> summarise(mtcars, avg_disp = mean(disp), sd_disp = sd(disp))
  avg_disp  sd_disp
1 230.7219 123.9387
> summarise(mtcars, avg_disp = mean(disp), sd_disp = sd(disp), avg_mpg = mean(disp), sd_mpg = sd(mpg))
  avg_disp  sd_disp  avg_mpg   sd_mpg
1 230.7219 123.9387 230.7219 6.026948
> 
> #_______________________________________________________________________________________________________
> 
> grp_cyl = group_by(mtcars, cyl)
> summarise(grp_cyl, avg_mpg = mean(mpg))
# A tibble: 3 × 2
    cyl avg_mpg
  <dbl>   <dbl>
1     4    26.7
2     6    19.7
3     8    15.1
> 
> # Similar to GROUP BY Function in RDBMS SQL
> 
> # SELECT cyl, avg(mpg), as avg_mpg
> # FROM mtcars
> # GROUP BY cyl;
> 
> #_____________________________________________________________________________________________
> 
> # We can pipeline the operations which are consecutive to one tbl object using %>% object
> 
> mtcars %>%
+   group_by(cyl) %>%
+   summarise(avg_mpg = mean(mpg))
# A tibble: 3 × 2
    cyl avg_mpg
  <dbl>   <dbl>
1     4    26.7
2     6    19.7
3     8    15.1
> 
> filter(select(mtcars, mpg, wt, hp, am), mpg > 30)
                mpg    wt  hp am
Fiat 128       32.4 2.200  66  1
Honda Civic    30.4 1.615  52  1
Toyota Corolla 33.9 1.835  65  1
Lotus Europa   30.4 1.513 113  1
> 
> # %>% magrittr operator 
> 
> # OR
> 
> mtcars |>
+   select(mpg, wt, hp, am) |>
+   filter(mpg > 30)
                mpg    wt  hp am
Fiat 128       32.4 2.200  66  1
Honda Civic    30.4 1.615  52  1
Toyota Corolla 33.9 1.835  65  1
Lotus Europa   30.4 1.513 113  1
> 
> # '|>' chaining operator
> 
> #________________________________________________________________________________________________
> 
> # Assignment
> 
> survey <- read.csv("C:/Datasets/survey.csv")
> survey
      Sex Wr.Hnd NW.Hnd W.Hnd    Fold Pulse    Clap Exer Smoke Height      M.I    Age
1  Female   18.5   18.0 Right  R on L    92    Left Some Never 173.00   Metric 18.250
2    Male   19.5   20.5  Left  R on L   104    Left None Regul 177.80 Imperial 17.583
3    Male   18.0   13.3 Right  L on R    87 Neither None Occas     NA     <NA> 16.917
4    Male   18.8   18.9 Right  R on L    NA Neither None Never 160.00   Metric 20.333
5    Male   20.0   20.0 Right Neither    35   Right Some Never 165.00   Metric 23.667
6  Female   18.0   17.7 Right  L on R    64   Right Some Never 172.72 Imperial 21.000
7    Male   17.7   17.7 Right  L on R    83   Right Freq Never 182.88 Imperial 18.833
8  Female   17.0   17.3 Right  R on L    74   Right Freq Never 157.00   Metric 35.833
9    Male   20.0   19.5 Right  R on L    72   Right Some Never 175.00   Metric 19.000
10   Male   18.5   18.5 Right  R on L    90   Right Some Never 167.00   Metric 22.333
11 Female   17.0   17.2 Right  L on R    80   Right Freq Never 156.20 Imperial 28.500
12   Male   21.0   21.0 Right  R on L    68    Left Freq Never     NA     <NA> 18.250
13 Female   16.0   16.0 Right  L on R    NA   Right Some Never 155.00   Metric 18.750
14 Female   19.5   20.2 Right  L on R    66 Neither Some Never 155.00   Metric 17.500
15   Male   16.0   15.5 Right  R on L    60   Right Some Never     NA     <NA> 17.167
16 Female   17.5   17.0 Right  R on L    NA   Right Freq Never 156.00   Metric 17.167
17 Female   18.0   18.0 Right  L on R    89 Neither Freq Never 157.00   Metric 19.333
18   Male   19.4   19.2  Left  R on L    74   Right Some Never 182.88 Imperial 18.333
19   Male   20.5   20.5 Right  L on R    NA    Left Some Never 190.50 Imperial 19.750
20   Male   21.0   20.9 Right  R on L    78   Right Freq Never 177.00   Metric 17.917
21   Male   21.5   22.0 Right  R on L    72    Left Freq Never 190.50 Imperial 17.917
22   Male   20.1   20.7 Right  L on R    72   Right Freq Never 180.34 Imperial 18.167
23   Male   18.5   18.0 Right  L on R    64   Right Freq Never 180.34 Imperial 17.833
24   Male   21.5   21.2 Right  R on L    62   Right Some Never 184.00   Metric 18.250
25 Female   17.0   17.5 Right  R on L    64    Left Some Never     NA     <NA> 19.167
26   Male   18.5   18.5 Right Neither    90 Neither Some Never     NA     <NA> 17.583
27   Male   21.0   20.7 Right  R on L    90   Right Some Never 172.72 Imperial 17.500
28   Male   20.8   21.4 Right  R on L    62 Neither Freq Never 175.26 Imperial 18.083
29   Male   17.8   17.8 Right  L on R    76 Neither Freq Never     NA     <NA> 21.917
30   Male   19.5   19.5 Right  L on R    79   Right Some Never 167.00   Metric 19.250
31 Female   18.5   18.0 Right  R on L    76   Right None Occas     NA     <NA> 41.583
32   Male   18.8   18.2 Right  L on R    78   Right Freq Never 180.00   Metric 17.500
33 Female   17.1   17.5 Right  R on L    72   Right Freq Heavy 166.40 Imperial 39.750
34   Male   20.1   20.0 Right  R on L    70   Right Some Never 180.00   Metric 17.167
35   Male   18.0   19.0 Right  L on R    54 Neither Some Regul     NA     <NA> 17.750
36   Male   22.2   21.0 Right  L on R    66   Right Freq Occas 190.00   Metric 18.000
37 Female   16.0   16.5 Right  L on R    NA   Right Some Never 168.00   Metric 19.000
38   Male   19.4   18.5 Right  R on L    72 Neither Freq Never 182.50   Metric 17.917
39   Male   22.0   22.0 Right  R on L    80   Right Some Never 185.00   Metric 35.500
40   Male   19.0   19.0 Right  R on L    NA Neither Freq Occas 171.00   Metric 19.917
41 Female   17.5   16.0 Right  L on R    NA   Right Some Never 169.00   Metric 17.500
42 Female   17.8   18.0 Right  R on L    72   Right Some Never 154.94 Imperial 17.083
43   Male     NA     NA Right  R on L    60    <NA> Some Never 172.00   Metric 28.583
44 Female   20.1   20.2 Right  L on R    80   Right Some Never 176.50 Imperial 17.500
45 Female   13.0   13.0  <NA>  L on R    70    Left Freq Never 180.34 Imperial 17.417
46   Male   17.0   17.5 Right  R on L    NA Neither Freq Never 180.34 Imperial 18.500
47   Male   23.2   22.7 Right  L on R    84    Left Freq Regul 180.00   Metric 18.917
48   Male   22.5   23.0 Right  R on L    96   Right None Never 170.00   Metric 19.417
49 Female   18.0   17.6 Right  R on L    60   Right Some Occas 168.00   Metric 18.417
50 Female   18.0   17.9 Right  R on L    50    Left None Never 165.00   Metric 30.750
51   Male   22.0   21.5  Left  R on L    55    Left Freq Never 200.00   Metric 18.500
52   Male   20.5   20.0 Right  L on R    68   Right Freq Never 190.00   Metric 17.500
53   Male   17.0   18.0 Right  L on R    78    Left Some Never 170.18 Imperial 18.333
54   Male   20.5   19.5 Right  L on R    56   Right Freq Never 179.00   Metric 17.417
55   Male   22.5   22.5 Right  R on L    65   Right Freq Regul 182.00   Metric 20.000
56   Male   18.5   18.5 Right  L on R    NA Neither Freq Never 171.00   Metric 18.333
57 Female   15.5   15.4 Right  R on L    70 Neither None Never 157.48 Imperial 17.167
58   Male   19.5   19.7 Right  R on L    72   Right Freq Never     NA     <NA> 17.417
59   Male   19.5   19.0 Right  L on R    62   Right Freq Never 177.80 Imperial 17.667
60   Male   20.6   21.0  Left  L on R    NA    Left Freq Occas 175.26 Imperial 18.417
61   Male   22.8   23.2 Right  R on L    66 Neither Freq Never 187.00   Metric 20.333
62 Female   18.5   18.2 Right  R on L    72 Neither Freq Never 167.64 Imperial 17.333
63 Female   19.6   19.7 Right  L on R    70   Right Freq Never 178.00   Metric 17.500
64 Female   18.7   18.0  Left  L on R    NA    Left None Never 170.00   Metric 19.833
65 Female   17.3   18.0 Right  L on R    64 Neither Freq Never 164.00   Metric 18.583
66   Male   19.5   19.8 Right Neither    NA   Right Freq Never 183.00   Metric 18.000
67 Female   19.0   19.1 Right  L on R    NA Neither Freq Never 172.00   Metric 30.667
68 Female   18.5   18.0 Right  R on L    64   Right Freq Never     NA     <NA> 16.917
69   Male   19.0   19.0 Right  L on R    NA   Right Some Never 180.00   Metric 19.917
70   Male   21.0   19.5 Right  L on R    80    Left None  <NA>     NA     <NA> 18.333
71 Female   18.0   17.5 Right  L on R    64    Left Freq Never 170.00   Metric 17.583
72   Male   19.4   19.5 Right  R on L    NA   Right Freq Heavy 176.00   Metric 17.833
73 Female   17.0   16.6 Right  R on L    68   Right Some Never 171.00   Metric 17.667
74 Female   16.5   17.0 Right  L on R    40    Left Freq Never 167.64 Imperial 17.417
75 Female   15.6   15.8 Right  R on L    88    Left Some Never 165.00   Metric 17.750
76 Female   17.5   17.5 Right Neither    68   Right Freq Heavy 170.00   Metric 20.667
77 Female   17.0   17.6 Right  L on R    76   Right Some Never 165.00   Metric 23.583
78 Female   18.6   18.0 Right  L on R    NA Neither Freq Heavy 165.10 Imperial 17.167
79 Female   18.3   18.5 Right  R on L    68 Neither Some Never 165.10 Imperial 17.083
80   Male   20.0   20.5 Right  L on R    NA   Right Freq Never 185.42 Imperial 18.750
81   Male   19.5   19.5  Left  R on L    66    Left Some Never     NA     <NA> 16.750
82   Male   19.2   18.9 Right  R on L    76   Right Freq Never 176.50 Imperial 20.167
83 Female   17.5   17.5 Right  R on L    98    Left Freq Never     NA     <NA> 17.667
 [ reached 'max' / getOption("max.print") -- omitted 154 rows ]
> 
> # Question 1
> 
> survey |>
+   select(Sex, Wr.Hnd, NW.Hnd, W.Hnd, Fold, Pulse, Clap, Exer, Smoke, Height, M.I, Age) |>
+   filter(Smoke == "Never")
      Sex Wr.Hnd NW.Hnd W.Hnd    Fold Pulse    Clap Exer Smoke Height      M.I    Age
1  Female   18.5   18.0 Right  R on L    92    Left Some Never 173.00   Metric 18.250
2    Male   18.8   18.9 Right  R on L    NA Neither None Never 160.00   Metric 20.333
3    Male   20.0   20.0 Right Neither    35   Right Some Never 165.00   Metric 23.667
4  Female   18.0   17.7 Right  L on R    64   Right Some Never 172.72 Imperial 21.000
5    Male   17.7   17.7 Right  L on R    83   Right Freq Never 182.88 Imperial 18.833
6  Female   17.0   17.3 Right  R on L    74   Right Freq Never 157.00   Metric 35.833
7    Male   20.0   19.5 Right  R on L    72   Right Some Never 175.00   Metric 19.000
8    Male   18.5   18.5 Right  R on L    90   Right Some Never 167.00   Metric 22.333
9  Female   17.0   17.2 Right  L on R    80   Right Freq Never 156.20 Imperial 28.500
10   Male   21.0   21.0 Right  R on L    68    Left Freq Never     NA     <NA> 18.250
11 Female   16.0   16.0 Right  L on R    NA   Right Some Never 155.00   Metric 18.750
12 Female   19.5   20.2 Right  L on R    66 Neither Some Never 155.00   Metric 17.500
13   Male   16.0   15.5 Right  R on L    60   Right Some Never     NA     <NA> 17.167
14 Female   17.5   17.0 Right  R on L    NA   Right Freq Never 156.00   Metric 17.167
15 Female   18.0   18.0 Right  L on R    89 Neither Freq Never 157.00   Metric 19.333
16   Male   19.4   19.2  Left  R on L    74   Right Some Never 182.88 Imperial 18.333
17   Male   20.5   20.5 Right  L on R    NA    Left Some Never 190.50 Imperial 19.750
18   Male   21.0   20.9 Right  R on L    78   Right Freq Never 177.00   Metric 17.917
19   Male   21.5   22.0 Right  R on L    72    Left Freq Never 190.50 Imperial 17.917
20   Male   20.1   20.7 Right  L on R    72   Right Freq Never 180.34 Imperial 18.167
21   Male   18.5   18.0 Right  L on R    64   Right Freq Never 180.34 Imperial 17.833
22   Male   21.5   21.2 Right  R on L    62   Right Some Never 184.00   Metric 18.250
23 Female   17.0   17.5 Right  R on L    64    Left Some Never     NA     <NA> 19.167
24   Male   18.5   18.5 Right Neither    90 Neither Some Never     NA     <NA> 17.583
25   Male   21.0   20.7 Right  R on L    90   Right Some Never 172.72 Imperial 17.500
26   Male   20.8   21.4 Right  R on L    62 Neither Freq Never 175.26 Imperial 18.083
27   Male   17.8   17.8 Right  L on R    76 Neither Freq Never     NA     <NA> 21.917
28   Male   19.5   19.5 Right  L on R    79   Right Some Never 167.00   Metric 19.250
29   Male   18.8   18.2 Right  L on R    78   Right Freq Never 180.00   Metric 17.500
30   Male   20.1   20.0 Right  R on L    70   Right Some Never 180.00   Metric 17.167
31 Female   16.0   16.5 Right  L on R    NA   Right Some Never 168.00   Metric 19.000
32   Male   19.4   18.5 Right  R on L    72 Neither Freq Never 182.50   Metric 17.917
33   Male   22.0   22.0 Right  R on L    80   Right Some Never 185.00   Metric 35.500
34 Female   17.5   16.0 Right  L on R    NA   Right Some Never 169.00   Metric 17.500
35 Female   17.8   18.0 Right  R on L    72   Right Some Never 154.94 Imperial 17.083
36   Male     NA     NA Right  R on L    60    <NA> Some Never 172.00   Metric 28.583
37 Female   20.1   20.2 Right  L on R    80   Right Some Never 176.50 Imperial 17.500
38 Female   13.0   13.0  <NA>  L on R    70    Left Freq Never 180.34 Imperial 17.417
39   Male   17.0   17.5 Right  R on L    NA Neither Freq Never 180.34 Imperial 18.500
40   Male   22.5   23.0 Right  R on L    96   Right None Never 170.00   Metric 19.417
41 Female   18.0   17.9 Right  R on L    50    Left None Never 165.00   Metric 30.750
42   Male   22.0   21.5  Left  R on L    55    Left Freq Never 200.00   Metric 18.500
43   Male   20.5   20.0 Right  L on R    68   Right Freq Never 190.00   Metric 17.500
44   Male   17.0   18.0 Right  L on R    78    Left Some Never 170.18 Imperial 18.333
45   Male   20.5   19.5 Right  L on R    56   Right Freq Never 179.00   Metric 17.417
46   Male   18.5   18.5 Right  L on R    NA Neither Freq Never 171.00   Metric 18.333
47 Female   15.5   15.4 Right  R on L    70 Neither None Never 157.48 Imperial 17.167
48   Male   19.5   19.7 Right  R on L    72   Right Freq Never     NA     <NA> 17.417
49   Male   19.5   19.0 Right  L on R    62   Right Freq Never 177.80 Imperial 17.667
50   Male   22.8   23.2 Right  R on L    66 Neither Freq Never 187.00   Metric 20.333
51 Female   18.5   18.2 Right  R on L    72 Neither Freq Never 167.64 Imperial 17.333
52 Female   19.6   19.7 Right  L on R    70   Right Freq Never 178.00   Metric 17.500
53 Female   18.7   18.0  Left  L on R    NA    Left None Never 170.00   Metric 19.833
54 Female   17.3   18.0 Right  L on R    64 Neither Freq Never 164.00   Metric 18.583
55   Male   19.5   19.8 Right Neither    NA   Right Freq Never 183.00   Metric 18.000
56 Female   19.0   19.1 Right  L on R    NA Neither Freq Never 172.00   Metric 30.667
57 Female   18.5   18.0 Right  R on L    64   Right Freq Never     NA     <NA> 16.917
58   Male   19.0   19.0 Right  L on R    NA   Right Some Never 180.00   Metric 19.917
59 Female   18.0   17.5 Right  L on R    64    Left Freq Never 170.00   Metric 17.583
60 Female   17.0   16.6 Right  R on L    68   Right Some Never 171.00   Metric 17.667
61 Female   16.5   17.0 Right  L on R    40    Left Freq Never 167.64 Imperial 17.417
62 Female   15.6   15.8 Right  R on L    88    Left Some Never 165.00   Metric 17.750
63 Female   17.0   17.6 Right  L on R    76   Right Some Never 165.00   Metric 23.583
64 Female   18.3   18.5 Right  R on L    68 Neither Some Never 165.10 Imperial 17.083
65   Male   20.0   20.5 Right  L on R    NA   Right Freq Never 185.42 Imperial 18.750
66   Male   19.5   19.5  Left  R on L    66    Left Some Never     NA     <NA> 16.750
67   Male   19.2   18.9 Right  R on L    76   Right Freq Never 176.50 Imperial 20.167
68 Female   17.5   17.5 Right  R on L    98    Left Freq Never     NA     <NA> 17.667
69 Female   17.0   17.4 Right  R on L    NA Neither Some Never     NA     <NA> 17.167
70   Male   23.0   23.5 Right  L on R    90   Right Freq Never 167.64 Imperial 17.167
71 Female   17.7   17.0 Right  R on L    76   Right Some Never 167.00   Metric 17.250
72 Female   18.2   18.0 Right  L on R    70   Right Some Never 162.56 Imperial 18.000
73 Female   18.3   18.5 Right  R on L    75    Left Freq Never 170.00   Metric 18.750
74   Male   18.0   18.0 Right Neither    60   Right Freq Never 179.00   Metric 21.583
75 Female   18.0   17.7  Left  R on L    92    Left Some Never     NA     <NA> 17.583
76   Male   20.5   20.0 Right  R on L    75    Left Some Never 183.00   Metric 19.667
77 Female   17.5   18.0 Right Neither    NA   Right Some Never     NA     <NA> 18.000
78 Female   18.2   17.5 Right  L on R    70   Right Some Never 165.00   Metric 19.667
79 Female   18.2   18.5 Right  R on L    NA   Right Some Never 168.00   Metric 17.083
80 Female   19.0   18.8 Right  L on R    NA   Right Some Never     NA     <NA> 17.083
81 Female   17.5   17.5 Right  R on L    60   Right Freq Never 166.50   Metric 23.250
82   Male   19.5   19.4 Right Neither    NA   Right Freq Never 165.00   Metric 18.083
83 Female   19.4   19.6 Right  R on L    68 Neither Freq Never 175.26 Imperial 19.083
 [ reached 'max' / getOption("max.print") -- omitted 106 rows ]
> 
> #__________________________________________________________________________________________________
> 
> #Question 2
> 
> survey |>
+   select(Sex, Exer, Smoke, Pulse) |>
+   filter
Error in filter : 
  The pipe operator requires a function call as RHS (<input>:3:3)
