rbind( ) and cbind( ):

- Matrices can also be created by using
functions cbind() and rbind().
- rbind() binds the rows and cbind() binds the
columns
- rbind contains more columns, less rows.
- cbind contains less columns, more rows.

"Recycling is the mechanism where numbers are filled for the remaining vacant spaces.

This is the general behaviour of R. When we add two vectors with different element sizes, the larger one will traverse again from the start of smaller.

> a <- 1:5

> a
[1] 1 2 3 4 5

> b <- 46:50

> b
[1] 46 47 48 49 50

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

When values specified ≠ ncols / nrows:
• While using any binding function in case if no. of rows / columns are not
equal to no. of values specified then the values get repeated in that order
with a warning.

> a <- 1:3

> b <- 20:30

> rbind(a, b)
  [,1] [,2] [,3] [,4] [,5] [,6] [,7]
a    1    2    3    1    2    3    1
b   20   21   22   23   24   25   26
  [,8] [,9] [,10] [,11]
a    2    3     1     2
b   27   28    29    30

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
Warning messages:
1: In rbind(a, b) :
  number of columns of result is not a multiple of vector length (arg 1)
2: In cbind(a, b) :
  number of rows of result is not a multiple of vector length (arg 1)

Array:
• Array can be treated as a vector with multiple dimensions
• Array can be created with the function array specifying the
dimension using dim as argument
• By default the values are NA
Syntax : array(dim=c(r,c,…))

> k <- array(dim = c(8))

> k
[1] NA NA NA NA NA NA NA NA

> d <- array(dim = c(3, 4))

> d
     [,1] [,2] [,3] [,4]
[1,]   NA   NA   NA   NA
[2,]   NA   NA   NA   NA
[3,]   NA   NA   NA   NA

Data Frames:

• Data frame are used hold tabular data
• We can combine several vectors of same length into a data frame
• Data frames provide a simpler way for handling the data than lists
• Data frame gets usually created by calling functions like read.csv(),
read.xlsx etc.

> a <- c(12, 23, 14, 15)

> b <- c("X", "Y", "Z", "W")

> df <- data.frame(a, b)

> df
   a b
1 12 X
2 23 Y
3 14 Z
4 15 W

> bollywood <- read.csv("C:/Datasets/Bollywood_2015.csv")

> bollywood
                    Movie_Name BO_Collection Budget   Box_Office_Verdict
1         Pyaar Ka Punchnama 2         53.25   25.0                  Hit
2                     Shandaar         38.28   68.0                 Flop
3              Singh is Bliing         74.87   92.0                 Flop
4                       Jazbaa         24.30   30.0                 Flop
5                       Talvar         24.00   22.0                 Plus
6       Kis Kisko Pyaar Karoon         44.80   20.0                  Hit
7               Calendar Girls          7.00   12.0                 Flop
8                  Katti Batti         22.96   36.0                 Flop
9                         Hero         31.75   28.0                 Plus
10                Welcome Back         96.88  100.0              Average
11                     Phantom         49.84   70.0                 Flop
12                 All is Well         12.65   36.0                 Flop
13                      Manjhi         13.36    8.5                 Plus
14                    Brothers         77.18   82.0                 Flop
15                    Drishyam         65.22   65.0              Average
16           Bajrangi Bhaijaan        318.14  125.0 All Time Blockbuster
17                   Bangistan          5.42   26.0                 Flop
18           Baahubali (Hindi)        111.38  130.0                  Hit
19                      Masaan          2.10    6.0                 Flop
20                   I Love NY          2.50   15.0                 Flop
21                      ABCD 2        105.01   60.0            Super Hit
22              Guddu Rangeela          7.97   15.0                 Flop
23         Second Hand Husband          2.61    9.0                 Flop
24                    Tanakpur          1.87    9.0                 Flop
25        Hamari Adhuri Kahani         30.21   45.0                 Flop
26             Dil Dhadakne Do         74.18   86.0                 Flop
27              Tanu Weds Manu        148.47   40.0          Blockbuster
28          Welcome To Karachi          8.00   20.0                 Flop
29                        Piku         78.69   50.0                  Hit
30              Gabbar is Back         85.41   72.0                  Hit
31               Bombay Velvet         23.87  110.0             Disaster
32        Kuch Kuch Locha Hain          4.12   16.0                 Flop
33                        Mr X         19.43   39.0                 Flop
34                       Leela         20.34   18.0              Average
35          Dharam Sankat Mein          8.15   16.0                 Flop
36             Byomkesh Bakshi         22.08   19.0              Average
37                     Hunterr         12.00   12.0              Average
38                       NH 10         31.30   21.0                  Hit
39                     Barkhaa          1.11    7.0                 Flop
40          Dum Laga Ke Haisha         28.89   13.0                  Hit
41 Dilliwali Zaalim Girlfriend          2.73   12.0                 Flop
42              Dirty Politics          7.16   15.0                 Flop
43                    Badlapur         50.04   26.0                  Hit
44                         Roy         36.32   40.0                 Flop
45                   Shamitabh         19.13   45.0                 Flop
46                        Baby         81.67   75.0             Semi Hit
47                 Khamoshiyan         11.03   11.0              Average
48       Hawaizaada Collection          3.00   25.0             Disaster
49    Dolly Ki Doli Collection         13.04   25.0                 Flop
50                          PK        330.83   90.0 All Time Blockbuster
51                       Tevar         33.96   60.0                 Flop
52                       Alone         17.29   18.0                 Flop

colnames
• Colnames are set of row or column names of a
matrix-like object.
Colnames are specifically for datasets

names:
• For knowing the names of the elements of any
object names() function can be used

> names(df)
[1] "a" "b"

> names(bollywood)
[1] "Movie_Name"         "BO_Collection"     
[3] "Budget"             "Box_Office_Verdict"

Setting the current working directory:
• Instead of calling the same path multiple no. of times
we can set the working directory to the frequently
used file path with the help of the function setwd( )

> setwd("C:/Datasets/")

Hence instead of typing as:

read.csv("C:/Datasets/Bollywood_2015.csv")

We can simply type as:

read.csv("Bollywood_2015.csv")

FILE INPUT AND OUTPUT:

Reading Data:
• The data from files read gets directly stored into data frame
objects
• For reading data from flat (notepad) files we can use any of the
functions:
– read.csv()
– read.table()
• For reading data from Excel format (.xlsx) we can use read.xlsx
from xlsx package

read.table( ) - Some Important Arguments:
– This function is a general form of read.csv( ) and read.csv2()
– The default values have been shown above
– file : the name of the file which the data are to be read from
– header : (optional) a logical value indicating whether the file contains the
names of the variables as its first line. Here default is FALSE
– row.names : a vector of row names
– col.names : a vector of column names
– colClasses : a character vector indicating the class of each column in the
dataset
– skip : no. of lines to skip from the top of the file
– sep : separator (optional). Default is space
– stringsAsFactors : (optional) logical indicating should the character vectors be
converted to factors?

Example of read.table():

members.txt:
List of Members
ID Name Age
1 Sanjay 40
2 Rahul 37
3 Dinesh 39

> mem <- read.table("C:/Datasets/members.txt", header = TRUE, colClasses = c("character", "character", "integer"), skip=1, sep=" ")

> mem
  ID   Name Age
1  1 Sanjay  40
2  2  Rahul  37
3  3 Dinesh  39

read.csv( )
• This function assumes comma as a delimiter by
default while we read a file
• It assumes that file already has a header i.e. a line
indicating the names of the variables separated
by a delimiters

> bollywood <- read.csv("C:/Datasets/Bollywood_2015.csv")

> bollywood
                    Movie_Name BO_Collection Budget   Box_Office_Verdict
1         Pyaar Ka Punchnama 2         53.25   25.0                  Hit
2                     Shandaar         38.28   68.0                 Flop
3              Singh is Bliing         74.87   92.0                 Flop
4                       Jazbaa         24.30   30.0                 Flop
5                       Talvar         24.00   22.0                 Plus
6       Kis Kisko Pyaar Karoon         44.80   20.0                  Hit
7               Calendar Girls          7.00   12.0                 Flop
8                  Katti Batti         22.96   36.0                 Flop
9                         Hero         31.75   28.0                 Plus
10                Welcome Back         96.88  100.0              Average
11                     Phantom         49.84   70.0                 Flop
12                 All is Well         12.65   36.0                 Flop
13                      Manjhi         13.36    8.5                 Plus
14                    Brothers         77.18   82.0                 Flop
15                    Drishyam         65.22   65.0              Average
16           Bajrangi Bhaijaan        318.14  125.0 All Time Blockbuster
17                   Bangistan          5.42   26.0                 Flop
18           Baahubali (Hindi)        111.38  130.0                  Hit
19                      Masaan          2.10    6.0                 Flop
20                   I Love NY          2.50   15.0                 Flop
21                      ABCD 2        105.01   60.0            Super Hit
22              Guddu Rangeela          7.97   15.0                 Flop
23         Second Hand Husband          2.61    9.0                 Flop
24                    Tanakpur          1.87    9.0                 Flop
25        Hamari Adhuri Kahani         30.21   45.0                 Flop
26             Dil Dhadakne Do         74.18   86.0                 Flop
27              Tanu Weds Manu        148.47   40.0          Blockbuster
28          Welcome To Karachi          8.00   20.0                 Flop
29                        Piku         78.69   50.0                  Hit
30              Gabbar is Back         85.41   72.0                  Hit
31               Bombay Velvet         23.87  110.0             Disaster
32        Kuch Kuch Locha Hain          4.12   16.0                 Flop
33                        Mr X         19.43   39.0                 Flop
34                       Leela         20.34   18.0              Average
35          Dharam Sankat Mein          8.15   16.0                 Flop
36             Byomkesh Bakshi         22.08   19.0              Average
37                     Hunterr         12.00   12.0              Average
38                       NH 10         31.30   21.0                  Hit
39                     Barkhaa          1.11    7.0                 Flop
40          Dum Laga Ke Haisha         28.89   13.0                  Hit
41 Dilliwali Zaalim Girlfriend          2.73   12.0                 Flop
42              Dirty Politics          7.16   15.0                 Flop
43                    Badlapur         50.04   26.0                  Hit
44                         Roy         36.32   40.0                 Flop
45                   Shamitabh         19.13   45.0                 Flop
46                        Baby         81.67   75.0             Semi Hit
47                 Khamoshiyan         11.03   11.0              Average
48       Hawaizaada Collection          3.00   25.0             Disaster
49    Dolly Ki Doli Collection         13.04   25.0                 Flop
50                          PK        330.83   90.0 All Time Blockbuster
51                       Tevar         33.96   60.0                 Flop
52                       Alone         17.29   18.0                 Flop

read.csv( ) arguments:
• The default values have been shown above
– file : the name of the file which the data are to be
read from
– header : (optional) a logical value indicating whether
the file contains the names of the variables as its first
line
– sep : separator (optional)
– stringsAsFactors : (optional) logical indicating should
the character vectors be converted to factors?

read.csv2( ) arguments:
• The default values have been shown above
– file : the name of the file which the data are to be read
from
– header : (optional) a logical value indicating whether the
file contains the names of the variables as its first line
– sep : separator (optional). Default is semi-colon
– stringsAsFactors : (optional) logical indicating should the
character vectors be converted to factors?

Reading from MS Excel Sheet:
• There are various alternatives for reading Excel sheet.
One of them is provided by package xlsx
• We can use read.xlsx( ) to read the Excel sheet
Syntax: read.xlsx(file,sheetNo)
file : file path
sheetNo : sheet number of the sheet to be read

install.packages("xlsx")
library(xlsx)
bank <- read.xlsx("C:/Datasets/bankruptcy.xlsx", 3)
bank

> bank <- read.xlsx("C:/Datasets/bankruptcy.xlsx", 3)
> bank
   NO D YR   R1   R2   R3   R4    R5    R6    R7    R8   R9  R10  R11  R12
1   1 0 78 0.23 0.08 0.02 0.03  0.46  0.12  0.19 10.36 1.17 0.40 0.10 0.14
2   2 0 77 0.19 0.07 0.09 0.12  0.02  0.02  0.03  3.13 1.73 0.60 0.78 0.63
3   3 0 72 0.07 0.02 0.03 0.05  0.06  0.10  0.14  2.41 1.36 0.41 0.66 0.70
4   4 0 80 0.07 0.03 0.04 0.04  0.04  0.06  0.06  5.55 1.13 0.44 0.58 0.57
5   5 0 81 0.09 0.02 0.03 0.04  0.06  0.08  0.11  2.85 1.88 0.42 0.62 0.46
6   6 0 70 0.24 0.07 0.14 0.22  0.10  0.18  0.29  2.34 1.37 0.43 0.79 0.92
7   7 0 76 0.08 0.04 0.02 0.03  0.30  0.13  0.21  3.72 0.82 0.42 0.18 0.36
8   8 0 77 0.10 0.02 0.02 0.04 -0.05 -0.06 -0.09  8.91 1.17 0.24 0.27 0.37
9   9 0 73 0.16 0.09 0.07 0.10  0.10  0.08  0.11  1.31 1.64 0.91 0.72 0.62
10 10 0 71 0.16 0.08 0.06 0.08  0.03  0.02  0.03  1.46 1.58 0.75 0.55 0.47
11 11 0 78 0.10 0.04 0.07 0.07  0.02  0.04  0.04  5.88 0.83 0.32 0.57 0.72
12 12 0 75 0.06 0.04 0.03 0.05 -0.11 -0.08 -0.13  0.84 1.73 1.15 0.89 0.79
13 13 0 81 0.32 0.10 0.14 0.21 -0.01 -0.02 -0.03  2.17 1.82 0.55 0.82 0.67
14 14 0 78 0.05 0.02 0.03 0.04 -0.01 -0.02 -0.02  2.45 1.30 0.64 0.77 0.81
15 15 0 70 0.18 0.07 0.12 0.14 -0.11 -0.17 -0.20  3.63 1.28 0.51 0.83 0.74
16 16 0 74 0.07 0.01 0.02 0.02 -0.01 -0.02 -0.03 97.53 1.47 0.15 0.34 0.32
17 17 0 72 0.17 0.02 0.08 0.10  0.01  0.03  0.04  4.09 1.72 0.25 0.76 0.57
18 18 0 72 0.11 0.04 0.07 0.09  0.02  0.04  0.05  3.31 1.39 0.51 0.89 0.84
19 19 0 73 0.15 0.02 0.06 0.09  0.03  0.07  0.11  4.53 1.48 0.23 0.57 0.59
20 20 0 75 0.07 0.02 0.04 0.05  0.01  0.02  0.02  2.82 1.60 0.60 0.88 0.74
21 21 0 73 0.32 0.07 0.11 0.25 -0.06 -0.10 -0.22  4.46 1.42 0.30 0.49 0.79
22 22 0 74 0.07 0.01 0.03 0.04  0.01  0.02  0.03  8.70 1.11 0.11 0.42 0.50
23 23 0 82 0.24 0.10 0.07 0.10  0.03  0.02  0.04  5.62 1.50 0.61 0.43 0.44
24 24 0 73 0.11 0.09 0.03 0.03  0.20  0.06  0.07  3.30 0.84 0.69 0.21 0.29
25 25 0 70 0.00 0.00 0.00 0.00 -0.03 -0.04 -0.03  6.89 0.65 0.48 0.80 0.82
26 26 0 70 0.02 0.01 0.01 0.01 -0.01 -0.02 -0.02  2.66 1.08 0.45 0.60 0.63
27 27 0 70 0.04 0.02 0.02 0.03  0.01  0.01  0.01 11.02 1.01 0.40 0.50 0.74
28 28 0 70 0.08 0.03 0.03 0.05  0.02  0.02  0.03  2.65 1.34 0.52 0.54 0.61
29 29 0 70 1.14 0.37 0.28 0.31 -0.02 -0.01 -0.01  1.66 3.30 1.06 0.80 0.27
30 30 0 70 0.03 0.01 0.02 0.02 -0.01 -0.03 -0.04  2.80 1.37 0.40 0.97 0.97
31 31 0 70 0.55 0.04 0.07 0.16  0.05  0.10  0.23  4.64 2.38 0.16 0.31 0.29
32 32 0 70 0.25 0.04 0.04 0.05  0.04  0.04  0.06 34.93 0.96 0.14 0.15 0.22
33 33 0 70 0.07 0.04 0.05 0.06  0.04  0.05  0.06  2.68 1.19 0.66 0.84 0.96
34 34 0 70 0.07 0.04 0.03 0.04 -0.01 -0.01 -0.02  2.09 1.53 0.81 0.64 0.62
35 35 0 71 0.06 0.01 0.03 0.05  0.03  0.09  0.14  2.97 1.45 0.26 0.76 0.80
36 36 0 71 0.06 0.02 0.02 0.03  0.01  0.02  0.03  3.45 1.56 0.47 0.61 0.55
37 37 0 71 0.03 0.01 0.02 0.03  0.14  0.20  0.30  0.38 1.31 0.47 0.71 0.81
     R13   R14   R15   R16   R17   R18    R19  R20  R21   R22   R23   R24
1   0.13  0.03  0.05  0.57  0.15  0.23   3.56 0.26 1.55  0.43  0.11  0.17
2   0.05  0.06  0.09  0.12  0.16  0.22   3.78 1.29 1.40  0.06  0.07  0.10
3  -0.01 -0.02 -0.03  0.02  0.02  0.04  13.29 1.61 1.43  0.03  0.05  0.07
4  -0.02 -0.02 -0.02  0.01  0.02  0.02   5.36 1.30 1.12 -0.06 -0.08 -0.09
5   0.01  0.02  0.02  0.07  0.10  0.14   7.74 1.48 1.41  0.03  0.04  0.06
6   0.03  0.06  0.10  0.06  0.11  0.18   9.82 1.82 1.60  0.06  0.11  0.18
7   0.03  0.01  0.02  0.15  0.06  0.10   5.98 0.42 1.67  0.12  0.05  0.09
8  -0.07 -0.07 -0.12 -0.04 -0.05 -0.08  10.14 1.15 1.60 -0.05 -0.06 -0.09
9   0.04  0.03  0.05  0.12  0.09  0.13   4.07 0.79 1.40  0.12  0.09  0.13
10  0.01  0.00  0.01  0.08  0.06  0.08   4.39 0.74 1.35  0.09  0.06  0.09
11 -0.04 -0.07 -0.08 -0.04 -0.07 -0.07   7.75 1.81 1.05 -0.03 -0.05 -0.06
12  0.09  0.07  0.11  0.24  0.19  0.29   2.85 0.78 1.53  0.11  0.09  0.13
13  0.01  0.02  0.03  0.07  0.10  0.15   5.39 1.49 1.47  0.05  0.07  0.11
14 -0.05 -0.06 -0.08  0.01  0.01  0.01   3.36 1.20 1.37 -0.02 -0.03 -0.04
15 -0.17 -0.27 -0.31 -0.12 -0.20 -0.23   4.97 1.62 1.15 -0.13 -0.21 -0.24
16 -0.03 -0.07 -0.09  0.00  0.00 -0.01  10.41 2.23 1.35 -0.03 -0.06 -0.08
17 -0.04 -0.11 -0.15 -0.03 -0.08 -0.11  25.24 3.04 1.29 -0.03 -0.10 -0.12
18  0.00 -0.01 -0.01  0.02  0.03  0.04   4.26 1.76 1.31  0.02  0.03  0.04
19  0.00  0.00  0.00  0.02  0.05  0.07  33.85 2.48 1.53  0.02  0.05  0.08
20  0.00  0.01  0.01  0.03  0.05  0.07   3.09 1.48 1.35  0.04  0.06  0.08
21  0.01  0.01  0.03  0.01  0.01  0.02  16.19 1.64 2.27  0.01  0.01  0.02
22  0.00  0.00  0.00  0.02  0.07  0.09 100.61 3.92 1.34  0.02  0.07  0.09
23  0.08  0.06  0.09  0.23  0.16  0.25   2.67 0.70 1.54  0.22  0.15  0.24
24  0.03  0.01  0.01  0.14  0.04  0.05   2.42 0.31 1.14  0.16  0.05  0.06
25 -0.28 -0.46 -0.31 -0.26 -0.43 -0.29   2.95 1.67 0.67 -0.26 -0.43 -0.29
26 -0.31 -0.41 -0.47 -0.30 -0.40 -0.45   7.69 1.32 1.14 -0.29 -0.38 -0.44
27  0.01  0.02  0.03  0.03  0.04  0.06   4.70 1.26 1.48 -0.07 -0.09 -0.14
28  0.06  0.06  0.09  0.06  0.06  0.09   5.05 1.03 1.52  0.03  0.03  0.04
29  0.01  0.01  0.01  0.03  0.02  0.02   3.28 0.75 1.11  0.03  0.02  0.03
30 -0.02 -0.06 -0.08 -0.02 -0.05 -0.07   9.11 2.40 1.38 -0.02 -0.05 -0.07
31  0.00  0.01  0.02  0.05  0.09  0.20   9.08 1.99 2.26  0.05  0.09  0.20
32  0.06  0.07  0.10  0.06  0.07  0.09  17.69 1.08 1.42  0.06  0.06  0.09
33 -0.18 -0.23 -0.31 -0.16 -0.21 -0.28   4.35 1.28 1.36 -0.16 -0.21 -0.28
34  0.02  0.01  0.02  0.05  0.04  0.05   2.49 0.79 1.49  0.04  0.03  0.04
35 -0.03 -0.09 -0.14 -0.01 -0.03 -0.04  37.85 2.94 1.53 -0.01 -0.03 -0.04
36 -0.01 -0.01 -0.02  0.02  0.02  0.03   5.11 1.30 1.41  0.03  0.03  0.05
37 -0.02 -0.03 -0.04  0.06  0.10  0.14   3.56 1.51 1.48  0.06  0.10  0.14
 [ reached 'max' / getOption("max.print") -- omitted 95 rows ]

Writing to a file:
• For writing to file the functions write.table( ) ,
write.csv() etc. can be used
Syntax Usage : write.table(data frame , file path)
write.csv(data frame , file path)

SUBSETTING THE DATA:
• A vector can be subsetted by typing various
options in between the brackets [ ]

> x <- c(12, 23, 52, 78, 90, 10, 28, 93, 95, 92, 95, 79)

> x[1:5]
[1] 12 23 52 78 90

> x > 50
 [1] FALSE FALSE  TRUE  TRUE  TRUE
 [6] FALSE FALSE  TRUE  TRUE  TRUE
[11]  TRUE  TRUE

> x[x > 50]
[1] 52 78 90 93 95 92 95 79

Subsetting a list:
• A list can be subsetted by typing various
options in between the brackets [ ]

> f <- list(a=1:7, b="XYZ", c=FALSE, d=c(23.4,14,6))

> f[1]
$a
[1] 1 2 3 4 5 6 7


> f[2]
$b
[1] "XYZ"


> f$c
[1] FALSE

> f[["c"]]
[1] FALSE

> f["c"]
$c
[1] FALSE

Subsetting a matrix:
• Matrix can be subsetted by specifying the row
or column numbers

> m <- matrix(c(1:12), 4, 3)

> m
     [,1] [,2] [,3]
[1,]    1    5    9
[2,]    2    6   10
[3,]    3    7   11
[4,]    4    8   12

> m[3, 2]
[1] 7

> m[2, ]
[1]  2  6 10

> m[, 3]
[1]  9 10 11 12

> m[, 3, drop = FALSE]
     [,1]
[1,]    9
[2,]   10
[3,]   11
[4,]   12

Specifying the column / row indices:
• Subsetting can be done to a data frame by specifying rows / columns

subset ():
• subset() function gives the data frame object
Syntax: subset(data frame , condition, select, …)

Control Structures:
• if, else
• for loop
• while loop
• break – breaking an execution of a loop
• next – skipping an iteration

if , else Structure
• Conditional processing: If the condition given in the if() is true then the
corresponding code block gets executed otherwise else code block is executed
if Syntax : if(condition) {
statements
}
If-else syntax : if(condition) {
statements
} else {
statements
}

> a <- 34000

> b <- 50000

> if(a+b > 10000){
+   paste("Total greater than 10000")
+ } else{
+   paste("Total not greater than 10000")
+ }
[1] "Total greater than 10000"

for loop:
• Loop can be created with for() using following
syntax :
for(var in seq) expr

> for (i in 1:4){
+   print(i)
+ }
[1] 1
[1] 2
[1] 3
[1] 4

while( ) loop:
• Loop can be generated with while() using following
syntax :
while(cond) expr
• So long as the condition remains true the body of loop
continues to execute

> while(cnt < 5){
+   print(cnt)
+   cnt <- cnt + 1
+ }
[1] 1
[1] 2
[1] 3
[1] 4

Breaking an execution of loop:
• Breaking a loop can be possible with break statement

> for(i in 1:4){
+   if (i == 3) break
+   print(i)
+ }
[1] 1
[1] 2

Skipping an iteration of a loop:
• For skipping the iteration of the loop, next
statement is used

> for(i in 1:4){
+   if (i == 3) next
+   print(i)
+ }
[1] 1
[1] 2
[1] 4

Some Functions:
Some commonly used functions…
• str
• seq
• table
• log
• exp
• ifelse
• attach

str():
• str function displays the internal structure of an R
object
• It can be called as a diagnostic function, we often use
to know about the object before we work on it

seq():
• For sequence generation, seq() is used
Syntax :
  seq(from = 1, to = 1, by = incr/decr...)

> seq(1, 20)
 [1]  1  2  3  4  5  6  7  8  9 10
[11] 11 12 13 14 15 16 17 18 19 20

> seq(1, 20, by = 4)
[1]  1  5  9 13 17

table()
• Frequency table and Cross-tabulation can be
generated with table()
Syntax: table(var1,var2,…)

table():
• Multivariate Frequencies

log():
• For calculating the logarithm, we can use log()
function
Syntax: log(x)
log10(x)
log2(x)
log1p(x)

log() Contd…
• log computes logarithms, by default natural
logarithms,
• log10 computes common (i.e., base 10)
logarithms,
• log2 computes binary (i.e., base 2) logarithms.
• The general form log(x, base) computes
logarithms with base base.
• log1p(x) computes log(1+x) accurately also
for |x| << 1

log() and exp():
> log(2)
[1] 0.6931472

> log(2, 10)
[1] 0.30103

> log1p(2)
[1] 1.098612

> log10
function (x)  .Primitive("log10")

> log2(2)
[1] 1

> exp(0.6931472)
[1] 2

> 10^0.30103
[1] 2

> expm1(1.098612)
[1] 1.999999

> 2^1
[1] 2

exp():
• exp computes the exponential function.
• expm1(x) computes exp(x) - 1 accurately also for |x| << 1.
Syntax : exp(x)
expm1(x)

> exp(0.6931472)
[1] 2

> expm1(0.6931472)
[1] 1

ifelse():
• In a simple way, we can treat ifelse() as a functional
version of the if-else structure
Syntax : ifelse(condition, true-value, false-value)
• If the condition is TRUE then the function returns
true-value otherwise it returns false-value

> v <- c(23, 13, 9, 24, 09, 3, 14, 8, 18, 20)

> result <- ifelse(v > 10, "Pass", "Fail")

> result
 [1] "Pass" "Pass" "Fail" "Pass"
 [5] "Fail" "Fail" "Pass" "Fail"
 [9] "Pass" "Pass"

Mean and Variance Functions:
• mean()
• sd()
• var()
• Each of the functions above have the syntax usage in the
following way: function-name(variable-name,na.rm)
– na.rm by default is FALSE. It should be set to TRUE if we want to
ignore the NA values while computing
