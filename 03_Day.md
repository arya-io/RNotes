# 🧪 R Lab Exercises

## 📁 1. Subsetting Orders Dataset (Only "Online" Payments)

```r
# Set the working directory to where the dataset is stored
setwd("C:/Datasets/")

# Read the Orders dataset
orders = read.csv("Orders.csv")

# View column names of the dataset
names(orders)

# Subset the data for only 'Online' payments
ss_ord = subset(orders, Mode.of.Payment == "Online")
```

### ✅ Output:

```r
> names(orders)
[1] "Order.ID"          "Order.Date"        "Place.of.Shipment" "Mode.of.Payment"

> ss_ord
    Order.ID Order.Date Place.of.Shipment Mode.of.Payment
2  32 90 002  06-Jan-11             Nasik          Online
6  32 90 006  01-Mar-11          Buldhana          Online
...
68 32 90 068  02-Aug-13         Ratnagiri          Online
```

### 💡 Notes:
- `subset()` is a convenient function to filter data using condition(s).
- Make sure to use double equals `==` for comparison.
- Useful when analyzing transactions by payment type.

---

## 💾 2. Saving the Built-in `mtcars` Dataset to CSV

```r
# Load the built-in dataset
data("mtcars")

# Print the dataset (optional step)
mtcars

# Write the dataset to a CSV file
write.csv(mtcars, "C:/Datasets/mtcars.csv")
```

### ✅ Output:

```r
> write.csv(mtcars, "C:/Datasets/mtcars.csv")
# A file named 'mtcars.csv' will be saved in the specified directory
```

### 💡 Notes:
- `write.csv()` exports your data to a CSV file.
- By default, `write.csv()` includes row names. Use `row.names = FALSE` if you want to exclude them.

---

## 💎 3. Subsetting Diamonds Dataset (Cut = Premium and Color = J)

```r
# Load the diamonds dataset
diamond <- read.csv("diamonds.csv")

# View column names to understand available features
names(diamond)

# Subset diamonds with specific cut and color
ss_diamond <- subset(diamond, cut == "Premium" & color == "J")

# View the filtered data
ss_diamond
```

### ✅ Output:

```r
> names(diamond)
[1] "carat" "cut" "color" "clarity" "depth" "table" "price" "x" "y" "z"

> ss_diamond
    carat   cut   color clarity depth ... price
57  0.30 Premium     J     SI2   59.3 ...   405
...
```

### 💡 Notes:
- Logical AND condition is applied using `&`.
- You can use `|` for OR condition.
- Inspect the structure with `str(diamond)` if needed.

---

## 📝 Final Tips:
- Always inspect your dataset using `str()`, `head()`, or `names()` before applying filters or transformations.
- Use `write.csv()` or `write.table()` for saving your results.
- Subsetting with `subset()` is simpler for readability, but `dplyr::filter()` is more flexible for complex queries.

---

## 💎 3. Continued: Subset Diamonds with Cut = "Premium" and Color = "J"

```r
# View column names of the diamonds dataset
names(diamond)

# Subset diamonds where cut is "Premium" and color is "J"
ss_diamond <- subset(diamond, cut == "Premium" & color == "J")

# View the filtered data
ss_diamond
```

### ✅ Output (Excerpt):

```r
> names(diamond)
 [1] "carat" "cut" "color" "clarity" "depth" "table" "price" "x" "y" "z"

> ss_diamond
     carat     cut color clarity depth table price    x    y    z
57    0.30 Premium     J     SI2  59.3    61   405 4.43 4.38 2.61
325   1.00 Premium     J     SI2  62.3    58  2801 6.45 6.34 3.98
...
6285  1.25 Premium     J     SI2  61.3    58  4018 6.98 6.95 4.27
```

> ℹ️ The full output was truncated due to printing limits but includes all matching rows (over 70 entries).

### 💡 Notes:
- This is a multi-condition filter using `&`.
- The dataset is filtered to show **only Premium-cut, J-colored diamonds**.
- Always inspect the subset to ensure the correct filter logic.

---

## 🧮 4. Create a New Data Frame with Selected Columns from `diamond`

We now extract a subset of columns (`carat`, `color`, `depth`, `price`) into a new data frame.

```r
# Create a new data frame with specific columns by index
q4 <- diamond[, c(1, 3, 5, 7)]

# Display the new data frame
q4
```

### ✅ Output (Excerpt):

```r
> q4
    carat color depth price
1    0.23     E  61.5   326
2    0.21     E  59.8   326
3    0.23     E  56.9   327
4    0.29     I  62.4   334
5    0.31     J  63.3   335
...
250  0.70     E  61.6  2789
```

> ℹ️ This extracts over 53,000 rows. Output has been truncated for readability.

### 💡 Notes:
- `diamond[, c(1, 3, 5, 7)]` selects columns by index:
  - 1: `carat`
  - 3: `color`
  - 5: `depth`
  - 7: `price`
- You can also use column **names**:  
  ```r
  diamond[, c("carat", "color", "depth", "price")]
  ```

---

## 📘 Summary So Far:

| Concept | Function Used | Description |
|--------|----------------|-------------|
| Read data | `read.csv()` | Loads CSV files into a data frame |
| View columns | `names()` | Lists column names |
| Subset by condition | `subset()` | Filters data using condition(s) |
| Export data | `write.csv()` | Saves data to a CSV file |
| Column selection | `[ , c(...)]` | Selects specific columns |

---

## 🔁 Additional Subsetting (Column Selection by Name)

```r
# Alternate way to select specific columns using `subset()`
ss_diam3 = subset(diamond, select = c('carat', 'color', 'depth', 'price'))
ss_diam3
```

### ✅ Output:
Same as previous output from `q4` (columns: `carat`, `color`, `depth`, `price`)

### 💡 Notes:
- `subset(..., select = ...)` allows selection by **column names**, which is safer and more readable than using index numbers.

---

## 🧾 5. Select Specific Rows from `mtcars`

```r
# Select 2nd, 18th, 30th, and 12th rows
q5 <- mtcars[c(2, 18, 30, 12), ]
q5
```

### ✅ Output:

```r
               mpg cyl  disp  hp drat    wt  qsec vs am gear carb
Mazda RX4 Wag 21.0   6 160.0 110 3.90 2.875 17.02  0  1    4    4
Fiat 128      32.4   4  78.7  66 4.08 2.200 19.47  1  1    4    1
Ferrari Dino  19.7   6 145.0 175 3.62 2.770 15.50  0  1    5    6
Merc 450SE    16.4   8 275.8 180 3.07 4.070 17.40  0  0    3    3
```

---

# ⚙️ Control Structures in R

## 🧩 `if`, `else` - Conditional Statements

### Syntax:
```r
if (condition) {
  # Code block if condition is true
} else {
  # Code block if condition is false
}
```

### Example:
```r
a <- 34000
b <- 50000

if (a + b > 10000) {
  paste("Total greater than 10000")
} else {
  paste("Total not greater than 10000")
}
```

**✅ Output:**
```r
[1] "Total greater than 10000"
```

---

## 🔁 `for` Loop

### Syntax:
```r
for (variable in sequence) {
  # Loop body
}
```

### Example:
```r
for (i in 1:4) {
  print(i)
}
```

**✅ Output:**
```r
[1] 1
[1] 2
[1] 3
[1] 4
```

---

## 🔁 `while` Loop

### Syntax:
```r
while (condition) {
  # Loop body
}
```

### Example:
```r
cnt <- 1
while (cnt < 5) {
  print(cnt)
  cnt <- cnt + 1
}
```

**✅ Output:**
```r
[1] 1
[1] 2
[1] 3
[1] 4
```

---

## 🚫 `break` – Exit Loop Early

```r
for (i in 1:4) {
  if (i == 3) break
  print(i)
}
```

**✅ Output:**
```r
[1] 1
[1] 2
```

---

## ⏭️ `next` – Skip Current Iteration

```r
for (i in 1:4) {
  if (i == 3) next
  print(i)
}
```

**✅ Output:**
```r
[1] 1
[1] 2
[1] 4
```

---

# 🛠️ Useful R Functions

### 🔍 `str()` – Structure of an Object

```r
str(mtcars)
```
- Displays internal structure (data types, dimensions).
- Helpful for quick inspection before processing.

---

### 🔢 `seq()` – Sequence Generator

```r
seq(1, 20)
seq(1, 20, by = 4)
```

**✅ Output:**
```r
[1]  1  2  3 ... 20
[1]  1  5  9 13 17
```

---

### 📊 `table()` – Frequency Table

```r
table(mtcars$cyl)
```
- Generates frequency tables.
- Can also cross-tabulate multiple variables: `table(var1, var2)`

---

## 🧮 `log()` & `exp()` – Logarithmic and Exponential Functions

### Logarithmic Variants:

| Function | Description |
|---------|-------------|
| `log(x)` | Natural log (base *e*) |
| `log(x, base=10)` | Log to custom base |
| `log10(x)` | Log base 10 |
| `log2(x)` | Log base 2 |
| `log1p(x)` | Accurate log(1 + x) |

### Exponential Variants:

| Function | Description |
|----------|-------------|
| `exp(x)` | Computes *e^x* |
| `expm1(x)` | Computes *e^x - 1* accurately |

### Examples:

```r
log(2)           # [1] 0.6931472
log(2, 10)       # [1] 0.30103
log1p(2)         # [1] 1.098612
log2(2)          # [1] 1
exp(0.6931472)   # [1] 2
10^0.30103       # [1] 2
expm1(1.098612)  # [1] 1.999999
2^1              # [1] 2
```

---

### 🧠 Quick Recap Table

| Function   | Description                            |
|------------|----------------------------------------|
| `str()`    | Structure of object                    |
| `seq()`    | Generate sequences                     |
| `table()`  | Frequency distribution                 |
| `log()`    | Logarithmic functions (base *e*, 10…) |
| `exp()`    | Exponential functions                  |
| `ifelse()` | Vectorized condition evaluation        |
| `attach()` | Attach data frame to search path       |

---

## 🧮 `ifelse()` – Functional If-Else

### 📌 Description:
- `ifelse()` is a **vectorized** version of the `if-else` structure.
- Efficient for applying conditions over **vectors**.
- Syntax:
  ```r
  ifelse(condition, value_if_true, value_if_false)
  ```

### ✅ Example:

```r
# Create a numeric vector
v <- c(23, 13, 9, 24, 9, 3, 14, 8, 18, 20)

# Apply ifelse: check if values > 10
result <- ifelse(v > 10, "Pass", "Fail")

# Print the result
result
```

### 🔢 Output:

```r
[1] "Pass" "Pass" "Fail" "Pass" "Fail"
[6] "Fail" "Pass" "Fail" "Pass" "Pass"
```

### 💡 Notes:
- Great for quick categorization and transformations.
- Works element-wise over vectors.
- Use with numeric, character, or factor outputs.

---

## 📊 Mean and Variance Functions

R provides built-in functions for common statistical summaries:

| Function | Description                      |
|----------|----------------------------------|
| `mean()` | Arithmetic mean (average)        |
| `sd()`   | Standard deviation               |
| `var()`  | Variance                         |

### 🧾 Usage Syntax:

```r
function_name(x, na.rm = FALSE)
```

- `x`: A numeric vector
- `na.rm`: Logical, whether to remove missing values (`NA`)  
  Default is `FALSE`; set to `TRUE` if you want to **ignore NA values**.

### ✅ Example:

```r
x <- c(10, 20, 30, NA)

mean(x)             # Returns NA
mean(x, na.rm = TRUE)  # Returns 20
```

### 🔢 Output:

```r
> mean(x)
[1] NA

> mean(x, na.rm = TRUE)
[1] 20
```

---

## ✅ Summary Table: Descriptive Stats

| Function | Returns                  |
|----------|--------------------------|
| `mean(x)` | Average value            |
| `sd(x)`   | Standard deviation       |
| `var(x)`  | Variance                 |

> ℹ️ All functions can ignore missing values with `na.rm = TRUE`.

---
