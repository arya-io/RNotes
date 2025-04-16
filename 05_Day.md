# 📊 **R Data Manipulation Assignment**  
### *Using `dplyr` to Filter and Transform Survey Data*  

---

## 🔍 **1. Filtering Males Who Have Never Smoked**  
**Objective**: Extract male respondents who never smoked.  

### **Code**:  
```r
library(dplyr)  
survey <- read.csv("survey.csv", stringsAsFactors = TRUE)  

MaleNonSmokers <- survey |>  
  select(Sex, Wr.Hnd, NW.Hnd, W.Hnd, Fold, Pulse, Clap, Exer, Smoke, Height, M.I, Age) |>  
  filter(Sex == "Male" & Smoke == "Never")  
```

### **Output Preview**:  
```
      Sex Wr.Hnd NW.Hnd W.Hnd    Fold Pulse    Clap Exer Smoke Height      M.I    Age
2    Male   18.8   18.9 Right  R on L    NA Neither None Never 160.00   Metric 20.333  
3    Male   20.0   20.0 Right Neither    35   Right Some Never 165.00   Metric 23.667  
5    Male   17.7   17.7 Right  L on R    83   Right Freq Never 182.88 Imperial 18.833  
... [truncated]  
```
**🔎 Observations**:  
- `filter(Smoke == "Never")` includes **females** too (row 1). To fix:  
  ```r
  filter(Sex == "Male", Smoke == "Never")  
  ```
- Missing values (`NA`) in `Pulse`, `Height`, and `M.I` indicate incomplete records.

---

## ❤️ **2. Students with Pulse Rate > 80**  
**Objective**: Identify respondents with elevated pulse rates.  

### **Code**:  
```r
PulseGT80 <- survey |>  
  select(Sex, Exer, Smoke, Pulse) |>  
  filter(Pulse > 80)  
```

### **Output Snippet**:  
```
      Sex Exer Smoke Pulse
1  Female Some Never    92  
2    Male None Regul   104  
3    Male None Occas    87  
...  
```
**📌 Key Notes**:  
- **Highest Pulse**: 104 (both male and female).  
- **Smoking Status**: Includes "Never," "Regul" (regular), and "Occas" (occasional).  
- 💡 **Tip**: Use `arrange(desc(Pulse))` to sort by pulse rate.  

---

## ✋ **3. Creating a Handedness Ratio Variable**  
**Objective**: Compute the ratio of writing hand span (`Wr.Hnd`) to non-writing hand span (`NW.Hnd`).  

### **Code**:  
```r
RtHand <- survey |>  
  mutate(Ratio_Hnd = Wr.Hnd / NW.Hnd) |>  
  select(Ratio_Hnd, Clap, Age)  
```

### **Output Highlights**:  
```
    Ratio_Hnd    Clap    Age
1   1.0277778    Left 18.250  
2   0.9512195    Left 17.583  
3   1.3533835 Neither 16.917  
...  
```
**🔬 Analysis**:  
- **Ratio > 1**: Writing hand is larger (e.g., row 3: `1.35`).  
- **NA Values**: Missing hand measurements result in `NA` ratios.  
- **Clapping Preference**: Most right-handed respondents clap on the right (`Clap == "Right"`).  

---

## 🛠 **Improvements & Tips**  
1. **Fix Filter Logic**: Add `Sex == "Male"` to exclude females in **Task 1**.  
2. **Handle NAs**: Use `na.omit()` or `filter(!is.na(Pulse))` for cleaner analysis.  
3. **Visualize**: Plot `Ratio_Hnd` distribution:  
   ```r
   hist(RtHand$Ratio_Hnd, main = "Hand Span Ratio Distribution")  
   ```

---

## 📂 **Final Notes**  
- **Data Quality**: Check for inconsistencies (e.g., `Smoke` categories: "Heavy" vs. "Regul").  
- **Extensions**: Merge tasks (e.g., pulse rates of male non-smokers).  

**🎯 Practice Exercise**:  
> *Filter left-handed (`W.Hnd == "Left"`) females who exercise frequently (`Exer == "Freq"`).*  

```r
LeftHandFemales <- survey |>  
  filter(Sex == "Female", W.Hnd == "Left", Exer == "Freq")  
```

---


# 📊 **Descriptive Statistics in R**  
### *Calculating Mean and Standard Deviation with `dplyr`*  

---

## 📏 **4. Overall Age Statistics**  
**Objective**: Compute the mean and standard deviation for the `Age` variable across all respondents.  

### **Code**:  
```r
DescStats <- survey %>%
  summarise(
    avg_age = mean(Age, na.rm = TRUE),  # Mean (ignoring NAs)
    sd_age = sd(Age, na.rm = TRUE)      # Standard deviation
  )
```

### **Output**:  
```
   avg_age   sd_age
1 20.37451 6.474335
```

**🔍 Interpretation**:  
- **Mean Age**: ~20.37 years  
- **Standard Deviation**: ~6.47 years  
- **Key Note**: `na.rm = TRUE` ensures missing values (`NA`) are excluded.  

---

## 👥 **5. Age Statistics Grouped by Sex**  
**Objective**: Compare age distributions between genders.  

### **Code**:  
```r
DescGrp <- survey %>%
  group_by(Sex) %>%                   # Group data by Sex
  summarise(
    avg_age = mean(Age, na.rm = TRUE),
    sd_age = sd(Age, na.rm = TRUE)
  )
```

### **Output**:  
```
# A tibble: 3 × 3
  Sex    avg_age sd_age
  <fct>    <dbl>  <dbl>
1 Female    20.4   6.10
2 Male      20.3   6.81
3 <NA>      20.7   7.11
```

**📊 Insights**:  
- **Similar Mean Ages**: Females (~20.4) and Males (~20.3) have nearly identical average ages.  
- **Variability**: Males show slightly higher standard deviation (6.81 vs. 6.10), indicating more age diversity.  
- **Missing Data**: The `NA` group (likely non-binary/unreported sex) has a small sample size (high SD).  

---

### 🛠 **Common Pitfalls & Tips**  
1. **Handling NAs**: Always check for missing values with `sum(is.na(survey$Age))`.  
2. **Visualization**: Plot group differences:  
   ```r
   boxplot(Age ~ Sex, data = survey, main = "Age Distribution by Sex")
   ```  
3. **Extended Analysis**: Add median and IQR for skewed data:  
   ```r
   summarise(median_age = median(Age, na.rm = TRUE), IQR_age = IQR(Age, na.rm = TRUE))
   ```

---

## 🎯 **Practice Exercise**  
> *Calculate the mean `Height` grouped by `Smoke` status. Which group is tallest on average?*  

```r
survey %>%
  group_by(Smoke) %>%
  summarise(avg_height = mean(Height, na.rm = TRUE))
```

---

**💡 Pro Tip**: Use `kable()` from the `knitr` package for prettier tables in reports:  
```r
knitr::kable(DescGrp, caption = "Age Statistics by Sex")
```

---

# 🔗 **Data Joins in R**  
### *Mastering Inner Joins with `dplyr`*

---

## 📚 **1. Course Data Inner Join**  
**Objective**: Combine course details with their schedules using a common key (`CourseCode`).

### **Code**:
```r
# Load data
courses <- read.csv("Courses.csv")
courseSchedule <- read.csv("CourseSchedule.csv")

# Rename and join
crs_info <- courses %>%
  rename(CourseCode = CourseID) %>%      # Standardize column name
  inner_join(courseSchedule, by = "CourseCode")  # Merge datasets
```

### **Output Preview**:
```
  CourseCode                Course Duration_hours   Fee  BeginDate    EndDate       Venue
1          1       R Programming             20 10000 23-11-2014 13-12-2015    Hinjewadi
2          1       R Programming             20 10000 24-11-2014 15-12-2014   Vimannagar
... [truncated]
```

**🔍 Key Insights**:
- Each course (e.g., "R Programming") has multiple schedule entries.
- `inner_join()` retains only records with matching `CourseCode` in both datasets.
- Columns from both datasets are combined horizontally.

---

## 🛒 **2. Multi-Table Join Challenge**  
**Objective**: Combine order details with item and order master data (requires sequential joins).

### **Approach**:
Since R doesn't support 3-way joins directly, we chain two joins:

```r
# Step 1: Join Orders with Order Details
order_full <- orders %>%
  inner_join(ord_details, by = "Order.ID")

# Step 2: Join result with Items
final_data <- order_full %>%
  inner_join(items, by = "Item.ID")
```

**⚠️ Note**:  
- Always verify key column names match between tables.
- For large datasets, consider `data.table` for better performance.

---

## 💡 **Pro Tips for Joins**:
1. **Check Keys First**:
   ```r
   unique(courses$CourseID) %in% unique(courseSchedule$CourseCode)
   ```
2. **Join Types Matter**:
   - `inner_join`: Only matching rows
   - `left_join`: All rows from left table
   - `full_join`: All rows from both tables

3. **Handle Duplicates**:
   ```r
   courseSchedule %>% distinct(CourseCode, BeginDate, .keep_all = TRUE)
   ```

---

## 🧩 **Practice Exercise**:
> *Calculate total revenue per course by joining `crs_info` with a hypothetical "Registrations" table on `CourseCode`.*

```r
registrations <- data.frame(
  CourseCode = c(1, 2, 3),
  Students = c(50, 30, 20)
  
crs_info %>%
  left_join(registrations, by = "CourseCode") %>%
  mutate(Revenue = Fee * Students)
```

---

## 📊 **Why This Matters**:
- Joins are fundamental for combining relational data
- Used in 90%+ of real-world data analysis tasks
- Critical skill for SQL and big data tools (Spark, etc.)

---

# 📊 **Data Joins in R**  
### 🔄 **Two Methods for Joining Tables**  

### 1. **Traditional Method (Step-by-Step Joins)**  
```r
# Step 1: Join ord_details and items
join1 <- inner_join(ord_details, items, by = "Item.ID")

# Step 2: Join the result with orders
join2 <- inner_join(join1, orders, by = "Order.ID")

# Output
join2
```
**Output**:  
*(Truncated for brevity)*  
```
Order.ID   Item.ID  Qty  Item.Name                          Item.Type  Brand       Price  Order.Date  Place.of.Shipment
32 90 001  121 021   7   Artline Whiteboard Marker (Pack)   Marker    Artline     270   31-Dec-10   Pune
...
```

**Key Notes**:  
- Uses **`inner_join()`** to merge tables sequentially.  
- Explicitly creates intermediate objects (`join1`, `join2`).  

---

### 2. **Piped Method (Nested Joins)**  
```r
ord_info <- orders %>%
  inner_join(
    items %>% 
      inner_join(ord_details, by = "Item.ID"), 
    by = "Order.ID"
  )

# Output
ord_info
```
**Output**:  
*(Same as above, but created in one pipeline)*  

**Key Notes**:  
- **Nested `%>%` pipes** avoid intermediate variables.  
- More concise but may be harder to debug.  

---

### 🔍 **Comparison**  
| Method          | Pros                          | Cons                          |
|-----------------|-------------------------------|-------------------------------|
| **Traditional** | Easier to debug step-by-step. | More verbose; extra objects.  |
| **Piped**       | Concise; avoids intermediates. | Harder to trace errors.       |

---

# 📦 **Reshaping Data with `tidyr`**  
### 🔄 **From Wide to Long Format**  
**Example**: `gather()` combines columns into key-value pairs.  

```r
library(tidyr)

# Original wide data (table4a)
table4a
```
**Output**:  
```
country     1999    2000
Afghanistan 745     2666
Brazil      37737   80488
...
```

```r
# Convert to long format
long_data <- gather(table4a, '1999', '2000', key = 'year', value = 'cases')
long_data
```
**Output**:  
```
country       year   cases
Afghanistan   1999   745
Brazil        1999   37737
...
```

**Key Notes**:  
- **`gather()`** transforms wide → long format.  
- **`key`**: New column for old column names (e.g., `year`).  
- **`value`**: New column for values (e.g., `cases`).  

---

### 📂 **Reading and Viewing Data**  
```r
comb1 <- read.csv("comb1.csv")
comb1
```
**Output**:  
```
District      Highlighter  Marker  Pen  Refill
Ahmednagar    225         51      674   69
Aurangabad    162         159     755   50
...
```

**Key Notes**:  
- **`read.csv()`** imports data from a CSV file.  
- Useful for quick inspection of structured data.  

---

### 💡 **Tips for Clarity**  
1. **Use comments** to explain each step.  
2. **Break complex pipes** into smaller steps for debugging.  
3. **Leverage `tidyr`** for data reshaping tasks.  

--- 

# 📌 **Reshaping Data: `gather()` Function**  
### 🔄 *Convert Wide Data to Long Format*  

### **1. Explicit Column Selection**  
```r
gather(comb1, 'Highlighter', 'Marker', 'Pen', 'Refill', 
       key = 'ItemType', value = 'qty')
```
**What it does:**  
- Takes columns `Highlighter`, `Marker`, `Pen`, and `Refill` from `comb1`.  
- Melts them into two new columns:  
  - `key`: `ItemType` (stores the original column names).  
  - `value`: `qty` (stores the values).  
- Keeps `District` as an identifier column.

**Output Structure:**  
```
District    | ItemType    | qty
---------------------------------
Ahmednagar  | Highlighter | 225
Ahmednagar  | Marker      | 51
...
```

---

### **2. Implicit Column Selection (Excluding `District`)**  
```r
gather(comb1, -District, key = 'ItemType', value = 'qty')
```
**What it does:**  
- **Excludes** `District` from melting.  
- **Includes all other columns** automatically (same output as above).  
- Useful when you have many columns to pivot and don’t want to list them manually.

**Key Difference:**  
- Avoids typing all column names explicitly.  

---

### 🧠 **Key Insights**  
1. **`gather()` vs. `pivot_longer()`**:  
   - In newer **tidyr**, `pivot_longer()` replaces `gather()` (more intuitive syntax).  
   Example:  
   ```r
   pivot_longer(comb1, cols = -District, names_to = 'ItemType', values_to = 'qty')
   ```

2. **Handling `NA` Values**:  
   - Your data has `NA`s (e.g., Refill in Goa/Kolhapur). Use `na.rm = TRUE` to exclude them:  
     ```r
     gather(comb1, -District, key = 'ItemType', value = 'qty', na.rm = TRUE)
     ```

3. **Use Case**:  
   - Long format is ideal for plotting (e.g., `ggplot2`) or grouped operations (e.g., `group_by(ItemType)`).

---

### 📊 **Visualizing the Transformation**  
**Original (Wide):**  
```
District    | Highlighter | Marker | Pen  | Refill
--------------------------------------------------
Ahmednagar  | 225         | 51     | 674  | 69
```

**After `gather()` (Long):**  
```
District    | ItemType    | qty
---------------------------------
Ahmednagar  | Highlighter | 225
Ahmednagar  | Marker      | 51
Ahmednagar  | Pen         | 674
Ahmednagar  | Refill      | 69
```

---

### 💡 **Pro Tip**  
- **Check data structure** before/after reshaping:  
  ```r
  str(comb1)          # Before (wide)
  str(gathered_data)  # After (long)
  ```

# 📊 Tidyr Functions Cheat Sheet

## 🔄 Spreading (vs Gathering)
### `spread()` - The Opposite of `gather()`

```r
> table2
# A tibble: 12 × 4
   country      year type            count
   <chr>       <dbl> <chr>           <dbl>
 1 Afghanistan  1999 cases             745
 2 Afghanistan  1999 population   19987071
 3 Afghanistan  2000 cases            2666
 4 Afghanistan  2000 population   20595360
 5 Brazil       1999 cases           37737
 6 Brazil       1999 population  172006362
 7 Brazil       2000 cases           80488
 8 Brazil       2000 population  174504898
 9 China        1999 cases          212258
10 China        1999 population 1272915272
11 China        2000 cases          213766
12 China        2000 population 1280428583
```

**Problem**: Data is in "long" format with multiple rows per observation  
**Solution**: `spread()` converts to "wide" format with one row per observation

```r
> spread(table2, key = "type", value = "count")
# A tibble: 6 × 4
  country      year  cases population
  <chr>       <dbl>  <dbl>      <dbl>
1 Afghanistan  1999    745   19987071
2 Afghanistan  2000   2666   20595360
3 Brazil       1999  37737  172006362
4 Brazil       2000  80488  174504898
5 China        1999 212258 1272915272
6 China        2000 213766 1280428583
```

**Key Parameters**:
- `key`: Column containing names for new columns
- `value`: Column containing values for new columns

---

## ✂️ The `separate()` Function
### Splitting One Column into Multiple

**Original Data**:
```r
> table3
# A tibble: 6 × 3
  country      year rate             
  <chr>       <dbl> <chr>            
1 Afghanistan  1999 745/19987071     
2 Afghanistan  2000 2666/20595360    
3 Brazil       1999 37737/172006362  
4 Brazil       2000 80488/174504898  
5 China        1999 212258/1272915272
6 China        2000 213766/1280428583
```

**Basic Usage** (splits at non-alphanumeric characters by default):
```r
> separate(table3, rate, into = c("cases", "pop"))
# A tibble: 6 × 4
  country      year cases  pop       
  <chr>       <dbl> <chr>  <chr>     
1 Afghanistan  1999 745    19987071  
2 Afghanistan  2000 2666   20595360  
3 Brazil       1999 37737  172006362 
4 Brazil       2000 80488  174504898 
5 China        1999 212258 1272915272
6 China        2000 213766 1280428583
```

**Pro Tip**: Use `convert = TRUE` to automatically detect column types
```r
> separate(table3, rate, into = c("cases", "pop"), convert = TRUE)
# A tibble: 6 × 4
  country      year  cases        pop
  <chr>       <dbl>  <int>      <int>
1 Afghanistan  1999    745   19987071
2 Afghanistan  2000   2666   20595360
3 Brazil       1999  37737  172006362
4 Brazil       2000  80488  174504898
5 China        1999 212258 1272915272
6 China        2000 213766 1280428583
```

**Advanced Usage**:
- `sep`: Specify custom separator (regex pattern)
  ```r
  separate(table3, rate, into = c("cases", "pop"), sep = "/")
  ```
- `remove`: Keep original column (default is TRUE)
- `extra`: Handle cases with too many splits
- `fill`: Handle cases with too few splits

---

## 🧠 Key Concepts to Remember

1. **Tidy Data Principles**:
   - Each variable → column
   - Each observation → row
   - Each value → cell

2. **Function Families**:
   - `gather()` vs `spread()` - long/wide format conversion
   - `separate()` vs `unite()` - column splitting/combining

3. **Common Use Cases**:
   - Preparing data for visualization (ggplot2 prefers long format)
   - Cleaning imported data
   - Reshaping for statistical analysis
