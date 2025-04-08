# 📊 Introduction to R Programming

## Why R?

- ✅ **Leading tool** for **statistics**, **data analysis**, and **machine learning**.
- 💸 **Free & Open-source** – no license required!
- 🔗 Easily **integrates** with other languages like **C/C++**, **Java**, and **Python**.
- 🌐 **Platform-independent** – works on Windows, macOS, and Linux.
- 📚 Strong support from an active community and vast packages (over 18,000 on CRAN!).

> 💡 **Tip:** R is especially powerful for statistical computing and visualization. If you're heading into data science or analytics, this is your go-to tool!

---

## 🌱 Evolution of R

- 🧠 R is an **implementation of the S programming language**, with **lexical scoping** (variable visibility rules) inspired by **Scheme**.
- 📜 **S language** was developed by **John Chambers** at **Bell Labs**.
- 🌍 **R was created by Ross Ihaka and Robert Gentleman** at the University of Auckland, New Zealand.
- 👨‍💻 Currently maintained by the **R Development Core Team** (includes John Chambers).

> 📘 **Did you know?** The design of R emphasizes clean, readable code for statistical modeling.

---

## 🛠️ R as a Project

- R is part of the **GNU project**.
- Its **source code** is mainly written in **C**, **Fortran**, and **R**.
- Distributed under the **GNU General Public License (GPL)**.
- Available via **precompiled binaries** for all major platforms.
- Comes with a **Command Line Interface (CLI)** but can be used via graphical interfaces like:
  - **RStudio**
  - **Jupyter Notebook**
  - **Tinn-R**, etc.

---

## 🧰 Programming Features of R

- R is an **interpreted language** – you enter commands, and they run instantly.
- Uses a **command-line interpreter**.
- Highly **interactive**, great for quick prototyping and exploratory analysis.

> 🔄 **Use the R console or RStudio terminal** for most tasks. You'll get instant feedback!

---

## 📦 CRAN – Comprehensive R Archive Network

- 🌐 A **network of mirror sites** containing:
  - Core R distribution
  - User-contributed packages
  - Documentation
  - Precompiled binaries
- Over **18,000+ packages** for tasks ranging from bioinformatics to finance.

> 🔍 Explore CRAN here: [https://cran.r-project.org](https://cran.r-project.org)

---

## 🖥️ Warming Up with the CLI (Command Line Interface)

- Use the **Up/Down arrow keys** to scroll through previous commands.
- Press **Tab** for autocompletion.
- Use `q()` to quit the R session.

> 🧪 **Practice Tip:** Try running simple math operations or assign values using `<-` or `=`.

```r
x <- 10
y <- 5
x + y
```

## 🧠 R Workspace

Your workspace is the current working environment in R.

It includes:

- Variables  
- Functions  
- Data frames  

You can save and reload your workspace:

- `save.image()` – saves current environment.  
- `load("yourfile.RData")` – reloads saved workspace.  
- `.RData` files are loaded automatically when R starts.

📁 **Workspace files help preserve your progress across sessions. Always save before you close R!**

---

## ✅ Summary for Quick Revision

| Topic     | Key Point                                           |
|-----------|-----------------------------------------------------|
| Why R     | Free, open-source, stats-friendly, cross-platform   |
| Evolution | Built on S language, created in New Zealand         |
| Project   | Part of GNU, written in C/Fortran/R                 |
| CLI       | Interactive terminal, up/down for history           |
| CRAN      | Repository of R packages and binaries               |
| Workspace | Your current environment, can be saved/loaded       |


## 🔌 Extensibility in R

One of R’s greatest strengths is its **extensibility** — the ability to add new features and capabilities beyond the core language.

### 📦 Packages and Libraries

- R has a **modular architecture**. You can extend its functionality by installing **packages**.
- Packages are collections of:
  - Functions
  - Data
  - Documentation
- Thousands of packages are available on **CRAN**, **Bioconductor**, and **GitHub**.

> 🧪 Example: To install and use the `ggplot2` package for data visualization:
```r
install.packages("ggplot2")
library(ggplot2)
```

## 🔁 Integration with Other Languages

R can call code written in:

- **C/C++** – for performance-intensive tasks  
- **Java** – via the `rJava` package  
- **Python** – using the `reticulate` package  

This makes R highly flexible for complex projects that require features from multiple languages.

---

## 🌍 APIs and Web Integration

You can interact with web services using packages like:

- `httr`  
- `jsonlite`  
- `curl`  

R can consume **REST APIs** and process **JSON/XML** data.

📘 **Example: Using `httr` to fetch data from an API**
```r
library(httr)
response <- GET("https://api.example.com/data")
content(response)
```

## 📈 Extending R for Big Data & Machine Learning (ML)

R integrates with tools like:

- **Hadoop** (via `rhdfs`)  
- **Spark** (via `sparklyr`)  
- **TensorFlow** and **Keras** for deep learning  

This enables R to handle **distributed computing** and **large-scale machine learning** tasks efficiently.

---

## 🧠 Summary

| Feature               | Description                                      |
|-----------------------|--------------------------------------------------|
| Packages              | Extend R’s functionality easily                  |
| Language Integration  | Works with C/C++, Java, Python                   |
| Web Integration       | API consumption, JSON/XML handling               |
| Big Data & ML Support | Connects to Hadoop, Spark, TensorFlow, etc.      |

> 💡 **Tip:** When facing a new problem, search **CRAN** or **GitHub** — there's probably already a package that does what you need!

## 🤔 Python has PyPI, R has?

👉 **Python** has **PyPI** (*Python Package Index*) – a central repository for Python packages.

👉 **R** has **CRAN** (*Comprehensive R Archive Network*) – which serves the same purpose for R.

### 🔍 Quick Comparison

| Language | Package Repository | URL                          |
|----------|--------------------|------------------------------|
| Python   | PyPI               | https://pypi.org             |
| R        | CRAN               | https://cran.r-project.org   |

> 💡 Just like you use `pip install` in Python, in R you use `install.packages("package_name")` to install packages from CRAN.

## 🏷️ R Version Naming

- Every version of **R** is released with a **codename**.
- For example, **R version 4.4.3** is named **"Trophy Case"**.
- These names are mostly symbolic and used for identification or fun, much like Ubuntu's version names (e.g., "Jammy Jellyfish").

> 🔎 You can check your R version and its codename using:

```r
version
```

## 💻 Command-Line Interface Similarity: Python vs R

Both **R** and **Python** offer interactive CLI (Command Line Interface) environments.

### 🔹 In R, the prompt appears as:
```
>
```

### 🔹 In Python, using the built-in interactive shell or in the CMD, the prompt appears as:
```
>>>
```

These symbols indicate that the system is ready to accept commands interactively.

> 💡 **Fun Fact:** This interactive CLI experience is what makes both **R** and **Python** ideal for quick experiments and prototyping!

## 🧮 Basic Commands in R

R is an interactive language where you can perform calculations and assign values directly in the console.

### 📌 Assignment in R

You can assign values to variables using `<-` or `=` (though `<-` is preferred in R):

```r
x <- 10
y = 5
```

## ➕ Arithmetic Operations

```r
x + y     # Addition → 15
x - y     # Subtraction → 5
x * y     # Multiplication → 50
x / y     # Division → 2
x ^ y     # Exponentiation (x to the power y) → 100000
x %% y    # Modulo (remainder) → 0
x %/% y   # Integer division → 2
```

## 📥 Printing Values

```r
print(x)   # Prints the value of x
x          # Also prints x in console
```

## 📌 Notes

- Everything in **R is case-sensitive**.
- You **don’t need a `;`** at the end of each line — R understands where a statement ends.
- Use `#` to add **comments** in your code.

```r
# This is a comment
z <- x + y  # z will store the sum of x and y
```

> 💡 **Tip:** Use the **up/down arrow keys** in the CLI to navigate through your command history!

## 📝 Writing and Running R Scripts (Base R GUI)

Although we're using **R**, not **RStudio**, you don't have to run every command directly in the CLI.

➡️ You can:

1. Open a **new script** via `File > New Script`.
2. Write all your code there.
3. Press **Ctrl + A** to select all.
4. Press **Ctrl + R** to run it in the R console.

This makes it easier to write, edit, and debug multiple lines of code.

---

## 🧮 Example: Calculate Simple Interest in R

```r
# Simple Interest Calculator
p <- 1000     # Principal amount
r <- 5        # Rate of interest (per annum)
t <- 2        # Time in years

si <- (p * r * t) / 100   # Formula: SI = (P × R × T) / 100
print(paste("Simple Interest is:", si))
```

> 💡 **Tip:** Using scripts helps keep your code organized and easy to re-run.

## ☕ Java vs R: Not a Fair Comparison

- **Java** is a powerful, general-purpose programming language — **one of the best** in terms of robustness and scalability.
- However, **R belongs to a completely different category** of languages — it is **mathematically and statistically oriented**.
- Comparing them directly isn't meaningful, as they serve different purposes and audiences.

### 📊 R is Purpose-Built for Data Science

- **R** was specifically developed for:
  - Mathematicians
  - Statisticians
  - Scientists
- It includes **specialized libraries** and functions for:
  - Statistical analysis
  - Data visualization
  - Machine learning
- These libraries are **not part of Java’s standard ecosystem**.

---

### 🕰️ Brief History of R

- **R was developed in the 1990s** by Ross Ihaka and Robert Gentleman.
- It was inspired by the **S programming language** and designed to make statistical computing more accessible and open.

> 💡 **Note:** R isn’t built for general-purpose app development like Java — it excels in data analysis, modeling, and visualization.

## 🚀 Getting Started with R

### 🔽 Download R

To begin using R, download the latest version from the official CRAN website:

- **Version:** R 4.4.3  
- 🔗 [https://cran.r-project.org](https://cran.r-project.org)

Install it according to your operating system (Windows, Mac, or Linux).

---

## 📊 Built-in Datasets in R

R comes with several **preloaded datasets** that are great for learning and practice.

### 📥 To view available datasets:

```r
data()
```

This command opens a list of all datasets available in your current R environment (including datasets from loaded packages).

---

## 🌐 External Sources for Datasets

When you're ready to work with real-world or larger datasets, you can download them from platforms like:

- 🔗 [Kaggle](https://www.kaggle.com)
- 🔗 [Hugging Face Datasets](https://huggingface.co/datasets)

These platforms offer a wide variety of datasets for:

- Machine Learning
- Natural Language Processing (NLP)
- Computer Vision
- And much more

> 💡 **Tip:** Start with built-in datasets like `mtcars`, `iris`, and `airquality` to get familiar with R's data manipulation capabilities.

## 📂 Accessing a Particular Dataset in R

To load and view a specific built-in dataset in R, use the `data()` function followed by the dataset name:

```r
data(Indometh)  # Loads the dataset into memory
Indometh        # Displays the dataset
```

## ✏️ Editing a Dataset

To open the **Data Editor** for a dataset (a spreadsheet-like interface), use:

```r
fix(Indometh)   # Opens the dataset in Data Editor
```

### 🖱️ Alternative GUI Method

In the **R GUI**, you can also navigate through the menu:

```nginx
Edit > Data Editor
```


This lets you **view and manually edit datasets** in a spreadsheet-style format, making it easier for beginners to explore and update data.

---

## 🧬 What are Resident Datasets?

**Resident Datasets** are built-in datasets that come with R (or are available via packages).  
They are especially useful for:

- 🧪 Practicing data analysis  
- 📊 Learning statistical functions  
- 🛠️ Testing code examples

These datasets are great for learning purposes without needing to load external data.

> 💡 **Tip:** Use `?Indometh` or `help(Indometh)` in the console to view the description, usage, and structure of the dataset.

## 💾 Save Workspace Image?

When you **close the R console window**, you might see a prompt:

Save workspace image?

### ❌ Why You Should Select "No":

- Selecting **Yes** saves your entire current environment (variables, data, functions) into a file called `.RData`.
- Next time you open R, it will **automatically reload all previous objects**, which can cause **confusion or conflicts** with new scripts.
- It’s better to start fresh unless you intentionally want to preserve your session state.

> ✅ **Best Practice:**  
Always use scripts to save your work. Scripts are clean, reproducible, and prevent clutter in your environment.

> 💡 **Tip:** You can manually save only the objects you need using `save()` or `save.image()` — no need to rely on the auto-prompt.

## 📊 DataFrames in R vs Python

In **Python**, data manipulation is often done using the **`pandas`** library and its `DataFrame` object.

In **R**, the equivalent is simply called a **`DataFrame`**, and it's a **built-in class** in the base R language.

### 🧬 What is a DataFrame in R?

- A **DataFrame** is a table or 2D array-like structure.
- It can contain **different data types** (numeric, character, factor, etc.) in **each column**.
- Rows are observations, and columns are variables — just like in Excel or SQL.

### ✅ Key Features:

- **Built-in** class in R (no extra package required)
- Columns can have different types
- Easy to manipulate using base R functions or `dplyr` (from the tidyverse)

### 📌 Example:

```r
# Creating a simple data frame in R
df <- data.frame(
  Name = c("Alice", "Bob", "Charlie"),
  Age = c(25, 30, 22),
  Score = c(89.5, 95.0, 78.5)
)

print(df)
```

> 💡 **Tip:** Use `str(df)` in R to inspect the **structure** of the DataFrame — it shows the type of each column, sample data, and more!

## 📦 What is a Tibble (DataFrame) in R?

A **tibble** is a modern version of a **DataFrame** provided by the **`tibble`** package, which is part of the **tidyverse** ecosystem.

### 🔍 Key Differences from Base DataFrame:

| Feature             | Base DataFrame      | Tibble                  |
|---------------------|---------------------|--------------------------|
| Printing            | Shows entire data   | Shows first 10 rows, fits width |
| Data Type Display   | Not shown           | Column types shown      |
| Subsetting          | Can simplify types  | More consistent behavior |
| Row Names           | Supports row names  | Does not use row names  |

### ✅ Benefits of Tibbles:

- **Cleaner output** in console
- **Better type stability**
- Friendly with **piping** (`%>%`)
- Works seamlessly with `dplyr`, `ggplot2`, and other tidyverse tools

### 🛠️ Creating a Tibble:

```r
library(tibble)

tb <- tibble(
  Name = c("Alice", "Bob", "Charlie"),
  Age = c(25, 30, 22),
  Score = c(89.5, 95.0, 78.5)
)

print(tb)
```

> 💡 **Tip:** Tibbles are especially useful when working on **data science projects** using the **tidyverse** approach, thanks to their cleaner output and compatibility with packages like `dplyr` and `ggplot2`.

## 🔍 Identifying Data Types in R

You can use the `class()` function to identify the type of an object.

### 📦 Example: Checking the Type of a Built-in Dataset

```r
class(Indometh)
```

This will return:
```csharp
[1] "data.frame"
```

So, `Indometh` is a **DataFrame**.

### 🔢 Example: Checking the Type of a Numeric Value

```r
d <- 90
class(d)
```

**Output:**

```r
[1] "numeric"
```

In **R**, `numeric` includes both **integers** and **floating-point numbers** by default.

---

🧠 **Note:**  
In **Java** and **C++**, R’s `numeric` type is roughly equivalent to **`float`** or **`double`**, depending on the precision and usage.

---

💡 **Tip:**  
Use `typeof(d)` to get more specific type information — for example, to check if a number is stored as a **double** or **integer**.

```r
typeof(d)  # Returns "double"
```

## 🔄 Type Conversion in R

R provides functions to **explicitly convert** data from one type to another.

### 🔢 Converting Numeric to Integer

```r
d <- 90
f <- as.integer(d)
f
```

**Output:**

```r
[1] 90
```

```r
class(f)  # Returns "integer"
```

So, although `d` was **numeric** (stored as `double`), after conversion, `f` becomes an **integer**.

---

### 🔁 Common Type Conversion Functions

| Function            | Description                                |
|---------------------|--------------------------------------------|
| `as.integer(x)`     | Converts `x` to integer                     |
| `as.numeric(x)`     | Converts `x` to numeric (default: double)   |
| `as.character(x)`   | Converts `x` to character (string)          |
| `as.data.frame(x)`  | Converts `x` to a DataFrame                 |
| `as.logical(x)`     | Converts `x` to logical (`TRUE`/`FALSE`)   |
| `as.factor(x)`      | Converts `x` to a factor (categorical)      |

💡 **Tip:** Always check the result of your conversion using `class()` or `typeof()` to confirm it worked as expected.

## ✅ Type Checking in R

R provides built-in functions to **check the data type** of variables.

### 🔍 Common Type-Checking Functions

| Function           | Checks if...              | Example              |
|--------------------|---------------------------|----------------------|
| `is.integer(x)`    | `x` is of type integer     | `is.integer(5L)`     |
| `is.numeric(x)`    | `x` is numeric (int/double) | `is.numeric(5)`      |
| `is.character(x)`  | `x` is a character string  | `is.character("hi")` |
| `is.logical(x)`    | `x` is logical (TRUE/FALSE)| `is.logical(TRUE)`   |
| `is.data.frame(x)` | `x` is a data frame        | `is.data.frame(df)`  |
| `is.factor(x)`     | `x` is a factor            | `is.factor(fac)`     |

---

### 🔎 Examples:

```r
x <- 10
is.integer(x)    # FALSE (default is double)
is.numeric(x)    # TRUE

y <- as.integer(x)
is.integer(y)    # TRUE
```

💡 **Tip:** Use `is.*()` functions to verify types before performing operations that depend on them.

## 📝 Assignment in R

In R, you can assign values to variables using multiple syntaxes:

### ✅ Valid Assignment Operators:

```r
ab = 2     # Using '='
ab <- 2    # Preferred in R (leftward assignment)
2 -> ab    # Rightward assignment
```

All three forms work the same way, but:

- `<-` is the most **idiomatic** and widely recommended in the R community.
- `=` is commonly used in **function arguments**.
- `->` is used when you want to **assign a value to a variable in reverse**.

💡 **Tip:** Stick to `<-` for consistency and readability in your R scripts.


## 🔧 Underscore (`_`) vs Dot (`.`) in R

Unlike some other programming languages like Python or Java, **R does not use the dot (`.`) operator** to access members of an object like:

```python
object.member  # (Python/Java-style)
```

Instead, R typically uses functions like:
```r
class(object)
summary(object)
```

However, **dot (`.`)** is still valid in variable and function names in R. For example:
```r
my.data <- data.frame()
print.summary <- function(x) { print("Summary:") }
```

## 🧵 What about the Underscore (`_`)?

The underscore (`_`) is **just a character** in a name.

Earlier versions of R allowed `_` for assignment, like:

```r
x _ 10  # (OLD and deprecated)
```

But this usage is now **deprecated**. Currently, `_` is treated as part of variable or function names.

You can use `_` in names like:

```r
my_variable <- 5
```

✅ **The preferred style today is to use:**

- **`snake_case`** (using underscores) — recommended in **tidyverse**
- **`dot.case`** (using dots) — still common in **base R**

---

### 🆚 Quick Comparison Table

| Language | Member Access     | Naming Convention Example     |
|----------|-------------------|-------------------------------|
| R        | `$` or functions  | `my_variable`, `my.data`      |
| Python   | `.`               | `my_variable.name`            |
| Java     | `.`               | `object.method()`             |

---

💡 **Tip:** In R, use the `$` operator to access list or dataframe elements:

```r
df$name
```

💡 **Tip:** Stick to `snake_case` if you're following **tidyverse** conventions for better readability and consistency.

## 🔍 Accessing a Particular Column in `Indometh`

To access a specific column (e.g., `conc`) from the built-in dataset `Indometh`, you have multiple options:

### ❌ This won't work:
```r
Indometh.conc
```

❗ **This syntax is invalid in R:**

## ✅ Accessing Columns in a DataFrame

### ✅ Use `$` (Horizontal Output):
```r
Indometh$conc
```

## Accessing Columns in R

The `$` operator is used to access a specific column by name:

Using `$` returns the column as a **vector**.

The output is displayed **horizontally** in the console.

---

### ✅ Use `["column_name"]` or `['column_name']` (Vertical Output)

```r
Indometh["conc"]
Indometh['conc']
```

This returns the column as a **DataFrame** with one column.

The output appears **vertically**, preserving column formatting.

---

### 📌 Notes
- `$` is the **access specifier** used to extract components from **lists** or **data frames**.
- Both double quotes `" "` and single quotes `' '` can be used when referencing column names inside brackets.

---

### 💡 Tip
Use the following command to inspect the structure and available columns in a dataset:

```r
str(Indometh)
```

## 📊 Basic Statistical Functions in R

### ✅ Arithmetic Mean
To calculate the **mean (average)** of a column:

```r
mean(Indometh$conc)
```

## 🧮 Other Useful Summary Functions

```r
sum(Indometh$conc)   # Total sum of values  
max(Indometh$conc)   # Maximum value  
min(Indometh$conc)   # Minimum value  
mode(Indometh$conc)  # Mode (most frequent value) — *not always accurate*  
```

> ⚠️ **Note:**  
> `mode()` in R returns the **storage mode** (e.g., `"numeric"` or `"character"`),  
> not the **statistical mode** (the most frequent value).  
> To find the actual statistical mode, you need to define a custom function.

🧪 **Loading Data in RStudio**

In **RStudio**, click on the **broom icon 🧹** in the Environment pane to clear all existing objects.  
This ensures you start fresh and see the message:

Environment is empty


---

Now, type the following code and click on **Run**:

```r
data("Indometh")
```

📦 **After executing the command**, in the **Environment** pane (right-side dialog box), you'll see:

Indometh : promise


---

🐌 **What does "promise" mean?**  
This indicates **lazy loading** — the data is **not loaded into memory immediately**, but will load **only when accessed**.

---

💡 **Tip:**  
Lazy loading is useful for:
- Memory efficiency  
- Faster startup times  
- Handling large datasets more effectively

# 📊 Data Types & Collections in R

R provides a variety of data types and structures to work with. Here’s a quick overview:

---

## 🔸 Atomic Classes
Basic building blocks in R:
- `numeric`
- `integer`
- `character`
- `logical`
- `complex`
- `raw`

---

## 🧱 Vectors
- A sequence of elements of the **same type**.
- Created using `c()` function.
  
```r
v <- c(1, 2, 3)  # numeric vector
```

## 📦 Lists  
A collection that can hold elements of different types.

```r
l <- list(1, "a", TRUE)  # list with mixed types
```

## 🏷️ Factors  
Used to handle **categorical variables**.  
Internally stored as **integers with labels**.

```r
f <- factor(c("low", "medium", "high"))
```

## ❓ Missing Values
- Represented by `NA` (Not Available)  
- Use `is.na()` to check for missing values

---

## 🔲 Matrices
- A **2D array** where all elements are of the **same type**  
- Created using the `matrix()` function

```r
m <- matrix(1:6, nrow = 2, ncol = 3)
```

## 🧊 Arrays
- Can have **more than two dimensions**

```r
a <- array(1:8, dim = c(2, 2, 2))
```

## 📋 Data Frames

- Most commonly used **data structure** for analysis  
- Columns can contain **different data types**

```r
df <- data.frame(id = 1:3, name = c("A", "B", "C"))
```

## 🔬 Atomic Classes in R

R has several atomic classes, which represent the most basic data types:

- **Character**
  - Examples: `"a"`, `"Good"`, `"Bad"`

- **Numeric** (real numbers)
  - Examples: `12.3`, `0`, `-0.92`, `-1200.76`

- **Integer**
  - Examples: `12`, `-13`, `90`, `0`

- **Complex**
  - Examples: `2 + 4i`, `5 - 5i`

- **Logical**
  - Examples: `TRUE`, `FALSE`

```r
f <- 3
g <- f > 5
as.integer(g)
g
```

🔍 **Explanation:**

```r
f <- 3
```

Assigns the value `3` to variable `f`.

```r
g <- f > 5
```

Compares whether `f` is greater than `5`. Since `3 > 5` is `FALSE`, `g` is assigned `FALSE`.

```r
as.integer(g)
```

Converts the logical value `FALSE` to an integer:

- `FALSE` becomes `0`  
- (If it were `TRUE`, it would be `1`)

```r
g
```

Still holds the value `FALSE`.

🧠 **Final Output:**

```r
> g
[1] FALSE

> as.integer(g)
[1] 0
```

## 🔹 What is a Vector?

- A **vector** is the most basic data structure in R.
- It can only contain **elements of the same atomic class**.
    - Example: all elements must be numeric, or all must be character.
- Vectors are **one-dimensional**.

### ✅ Creating Vectors

Use the `c()` function to create a vector.

```r
b <- c(53, 89, 20, 90, 102, 5)
```

Here, `c()` stands for **combine** or **concatenate**.

This creates a numeric vector `b`.

---

## 📌 Accessing Vector Elements

```r
b[3]
```

This will return the **3rd element** of vector `b` (i.e., `20`).

---

🔸 **Important:** Indexing in R starts from **1**, not 0.

You can also access a range of elements:

```r
b[2:5]
```

This gives the 2nd to 5th elements: `89 20 90 102`.

---

## 🔍 Checking Type and Class

```r
type(b)  # ❌ Doesn't work as expected
class(b) # ✅ Returns "numeric"
```

`type()` is **not valid** in this context.

Use `class()` to check the data type of the vector.

---

## 🔡 Character Vectors

```r
z <- c("a", "b", "c", "d", "e")
class(z)  # "character"
```

Mixing types inside a vector will **coerce them into the same type**:

```r
z <- c("a", 2)
class(z)  # "character"
```

The number `2` is automatically converted to `"2"` (a character).

R uses **type coercion** to maintain **homogeneity in vectors**.

---

## 📊 Vectors in Data Frames

- In a **data frame**, every **column is a vector**.
- All columns can be of **different types** (e.g., numeric, character, factor), but each column is internally a **vector of a single type**.

---

### 🧠 Why this is useful?

Because you can process columns (vectors) **independently** and perform **vectorized operations** such as:

- **Filtering**
- **Aggregating**
- **Transforming**
- **Mutating values**

---

## 🔎 Structure of a Dataset

Use the `str()` function to inspect the internal structure of an object:

```r
str(Indometh)
```

`Indometh` is a built-in dataset in R.

The `str()` function shows:

- Each **column** (i.e., vector) with its **data type**
- A **preview of the values**
- Total number of **observations (rows)**

---

## 🧠 Pro Tip

Vectors are **highly optimized for performance** in R.  
Whenever possible, prefer **vectorized operations** over loops — they are:

- ✅ **Faster**
- ✅ **More readable**
- ✅ **More idiomatic to R**

```r
# Example of a vectorized operation
b * 2
```

## 📚 Lists in R

A **list** in R can contain elements of **different types and lengths**.

### 🔸 Example:

```r
s <- list(a = c(34, 90, 23), g = 3, h = TRUE)
```

In this example:

- `a` is a **numeric vector**
- `g` is a **numeric value**
- `h` is a **logical value** (`TRUE`)

---

## 🔄 Difference Between Lists in Python and R

| Concept           | R List                           | Python List            |
|-------------------|----------------------------------|------------------------|
| **Heterogeneity** | ✅ Can contain different types    | ✅ Can contain different types |
| **Named elements**| ✅ Supports named elements        | ❌ No native support for names |
| **Access by name**| ✅ `$` or `[[ ]]` supported       | ❌ Not possible         |
| **Similar to**    | Python’s `dict` or JSON object   | Regular list (`[]`)    |

> **Important:**  
> In **R**, a list is more like a **Python dictionary** than a Python list — especially when the elements are **named**.

---

## 🔍 Accessing List Elements in R

If you have the list:

```r
s <- list(a = c(34, 90, 23), g = 3, h = TRUE)
```

## 🔍 Accessing List Elements in R

You can access elements using:

- `s$a` → returns `c(34, 90, 23)`
- `s$g` → returns `3`
- `s$h` → returns `TRUE`
- `s$a[1]` → returns `34` (first element of vector `a`)

---

## 🧪 Another Example: Unnamed List

```r
w <- list(c(34, 90, 23), 3, TRUE)
```

Accessing elements:
```r
w[1]        # Returns the first element as a list
w[[1]]      # Returns the first element as a vector: c(34, 90, 23)
w[[1]][1]   # Returns 34 (the first value of the first vector)
```

## 🔧 Which Accessing Method is Recommended?

- ✅ Use `[[ ]]` for direct access to list elements.
- ✅ Use `$name` when the element has a name (e.g., `s$a`).
- ⚠️ Avoid using `[ ]` unless you need a sub-list (it returns a list, not the element directly).

---

## ❗ Quick Note on Python Dictionaries

A Python dictionary is **not indexable by position**:

```python
d = {"a": 10, "b": 20}
d[0]      # ❌ Raises an error
```

Instead, access elements using their **keys**:

```python
d["a"]    # ✅ Returns 10
```

## 🔢 Factor in R

- **Factors** are used to represent **categorical data** in R.
- Factors can be **unordered** or **ordered**.
- Internally, a factor is stored as an **integer vector** where each integer is associated with a **label**.
- Useful for modeling **categorical variables**, such as:

  - `Yes` / `No`
  - `Sold` / `Not Sold` / `On Hold`

---

### ❓ What is Categorical Data?

**Categorical data** is data that can be divided into **distinct groups or categories**.

- Categories can be **nominal** (no inherent order) or **ordinal** (with a meaningful order).
  
Examples:

| Variable        | Type       | Example Values             |
|----------------|------------|----------------------------|
| Gender          | Nominal    | Male, Female               |
| Product Status  | Ordinal    | Not Sold, On Hold, Sold    |
| Blood Type      | Nominal    | A, B, AB, O                |
| Survey Rating   | Ordinal    | Poor, Fair, Good, Excellent|

---

📌 **Why Factors?**

- Help in memory optimization (as integers).
- Used in statistical modeling (like regression).
- Allow consistent treatment of levels across datasets.

## 🎯 Working with Factors in R

### Step 1: Create a Character Vector

```r
gdr = c("f", "m", "m", "f", "f", "m")
class(gdr)  # "character"
```

`gdr` is a character vector containing gender labels `"f"` and `"m"`.

---

### Step 2: Convert to Factor

```r
f_gdr = factor(gdr)
class(f_gdr)  # "factor"
f_gdr
```

Now, `f_gdr` is a **factor**.

- The factor will automatically assign **integer levels** (e.g., `"f"` = 1, `"m"` = 2).
- The **order of levels** is based on **alphabetical order by default**.

---

### Step 3: Convert Factor to Integer

```r
as.integer(f_gdr)
```
 
This returns the underlying **integer codes** for the factor levels.

---

### 🔄 Step 4: Custom Order of Levels

```r
f_gdr = factor(gdr, levels = c("m", "f"))
f_gdr
as.integer(f_gdr)
```

Now, `"m"` becomes **level 1** and `"f"` becomes **level 2**.

Changing the **order of levels** affects how the factor is **interpreted**, especially in **modeling**.

---

### 🔍 Step 5: View Unique Values in Original Vector

```r
unique(gdr)
```

- Returns unique character values in the original vector: `"f"`, `"m"`

---

### 🚫 Step 6: Defining Incomplete Levels

```r
f_gdr = factor(gdr, levels = c("m"))
f_gdr
```

Since only `"m"` is defined in the levels, all `"f"` values will be shown as **NA**.

This is useful for **filtering** or checking for **unexpected values**.

---

### 📌 Key Takeaways

- `factor()` is used to create **categorical variables**.
- `levels` can be manually specified to enforce a **specific order**.
- **Unmatched levels** (e.g., `"f"` when only `"m"` is in levels) become **NA**.
- Use `as.integer()` to inspect the **internal level mapping**.

### 🔍 Missing Values in R

- **Indeterminate values** are called **NaN** (Not a Number).
- **Missing values** are represented as either **`NA`** or **`NaN`**.

---

### 🧪 Functions to Check Missing Values

- `is.na()` — Used to test if objects are `NA`.
- `is.nan()` — Used to test if values are specifically `NaN`.
- There are also functions like `is.finite()` and `is.infinite()` to check for **finite** and **infinite** values.

---

### ⚠️ Key Difference

- A **`NaN`** value is also an **`NA`**.
- But an **`NA`** is **not always** a **`NaN`**.

---

### 🧠 Example

A classic example of `NaN` is the result of:

```r
0 / 0  # Returns NaN
```

### 🔎 Checking for NULL / Missing Values in R

#### ✅ Basic Examples

```r
g <- NA
is.na(g)         # TRUE
```

```r
k <- c(34, NA, 3, 80, NA, 4, 1)
is.na(k)         # Returns a logical vector indicating which elements are NA
```

### 📊 Count the Number of Missing Values

```r
sum(is.na(k))    # 2 missing values in vector k
```

### 📁 Working with a Dataset

```r
data("airquality")
airquality$Ozone
sum(is.na(airquality$Ozone))  # Returns 37
```

### ⚠️ NaN vs NA

```r
f <- 0
p <- 0
g <- f / p
is.nan(g)    # TRUE (0/0 is NaN)
is.na(g)     # TRUE
```

> **Note:** `NaN` is a special case of `NA`, so it returns `TRUE` for both `is.nan()` and `is.na()`.

---

### 🔁 Finite & Infinite Values

```r
r <- 23
p <- 0
e <- r / p     # Result is Inf
is.finite(e)   # FALSE
is.infinite(e) # TRUE
```
