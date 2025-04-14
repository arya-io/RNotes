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

> a=1:5
> a
[1] 1 2 3 4 5
> b=46:50
> b
[1] 46 47 48 49 50
> 
> m1=cbind(a,b)
> m1
     a  b
[1,] 1 46
[2,] 2 47
[3,] 3 48
[4,] 4 49
[5,] 5 50
> m2=rbind(a,b)
> m2
  [,1] [,2] [,3] [,4] [,5]
a    1    2    3    4    5
b   46   47   48   49   50
> 
> dim(m1)
[1] 5 2
> dim(m2)
[1] 2 5
> 
> d=31:40
> d
 [1] 31 32 33 34 35 36 37 38 39 40
> rbind(a,d)
  [,1] [,2] [,3] [,4] [,5] [,6] [,7] [,8] [,9] [,10]
a    1    2    3    4    5    1    2    3    4     5
d   31   32   33   34   35   36   37   38   39    40
> 
> ab <- c(3, 5, 6, 7)
> cd <- c(2, 4, 1)
> 
> ab + cd
[1] 5 9 7 9
Warning message:
In ab + cd :
  longer object length is not a multiple of shorter object length

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

> a=c("A","B","C")
> b= c(6,5,4)
> df=data.frame(a,b)
> df
  a b
1 A 6
2 B 5
3 C 4
> colnames(df)
[1] "a" "b"
> names(df)
[1] "a" "b"
> names(Indometh)
[1] "Subject" "time"    "conc"   
> 
> s=list(p=c(4,5,2),q=c(3,2),r=TRUE)

> names(s)
[1] "p" "q" "r"

Setting the current working directory:
• Instead of calling the same path multiple no. of times
we can set the working directory to the frequently
used file path with the help of the function setwd( )

> setwd("C:/Datasets/")

Hence instead of typing as:

read.csv("C:/Datasets/Bollywood_2015.csv")

We can simply type as:

read.csv("Bollywood_2015.csv")

> csv_df <- read.csv("C:/Users/dbda.STUDENTSDC/Downloads/Housing.csv")
> csv_df
   price lotsize bedrooms bathrms stories driveway recroom fullbase gashw airco garagepl prefarea
1  42000    5850        3       1       2      yes      no      yes    no    no        1       no
2  38500    4000        2       1       1      yes      no       no    no    no        0       no
3  49500    3060        3       1       1      yes      no       no    no    no        0       no
4  60500    6650        3       1       2      yes     yes       no    no    no        0       no
5  61000    6360        2       1       1      yes      no       no    no    no        0       no
6  66000    4160        3       1       1      yes     yes      yes    no   yes        0       no
7  66000    3880        3       2       2      yes      no      yes    no    no        2       no
8  69000    4160        3       1       3      yes      no       no    no    no        0       no
9  83800    4800        3       1       1      yes     yes      yes    no    no        0       no
10 88500    5500        3       2       4      yes     yes       no    no   yes        1       no
11 90000    7200        3       2       1      yes      no      yes    no   yes        3       no
12 30500    3000        2       1       1       no      no       no    no    no        0       no
13 27000    1700        3       1       2      yes      no       no    no    no        0       no
14 36000    2880        3       1       1       no      no       no    no    no        0       no
15 37000    3600        2       1       1      yes      no       no    no    no        0       no
16 37900    3185        2       1       1      yes      no       no    no   yes        0       no
17 40500    3300        3       1       2       no      no       no    no    no        1       no
18 40750    5200        4       1       3      yes      no       no    no    no        0       no
19 45000    3450        1       1       1      yes      no       no    no    no        0       no
20 45000    3986        2       2       1       no     yes      yes    no    no        1       no
21 48500    4785        3       1       2      yes     yes      yes    no   yes        1       no
22 65900    4510        4       2       2      yes      no      yes    no    no        0       no
23 37900    4000        3       1       2      yes      no       no    no   yes        0       no
24 38000    3934        2       1       1      yes      no       no    no    no        0       no
25 42000    4960        2       1       1      yes      no       no    no    no        0       no
26 42300    3000        2       1       2      yes      no       no    no    no        0       no
27 43500    3800        2       1       1      yes      no       no    no    no        0       no
28 44000    4960        2       1       1      yes      no      yes    no   yes        0       no
29 44500    3000        3       1       1       no      no       no    no   yes        0       no
30 44900    4500        3       1       2      yes      no       no    no   yes        0       no
31 45000    3500        2       1       1       no      no      yes    no    no        0       no
32 48000    3500        4       1       2      yes      no       no    no   yes        2       no
33 49000    4000        2       1       1      yes      no       no    no    no        0       no
34 51500    4500        2       1       1      yes      no       no    no    no        0       no
35 61000    6360        2       1       2      yes      no       no    no    no        0       no
36 61000    4500        2       1       1      yes      no       no    no   yes        2       no
37 61700    4032        2       1       1      yes      no      yes    no    no        0       no
38 67000    5170        3       1       4      yes      no       no    no   yes        0       no
39 82000    5400        4       2       2      yes      no       no    no   yes        2       no
40 54500    3150        2       2       1       no      no      yes    no    no        0       no
41 66500    3745        3       1       2      yes      no      yes    no    no        0       no
42 70000    4520        3       1       2      yes      no      yes    no   yes        0       no
43 82000    4640        4       1       2      yes      no       no    no    no        1       no
44 92000    8580        5       3       2      yes      no       no    no    no        2       no
45 38000    2000        2       1       2      yes      no       no    no    no        0       no
46 44000    2160        3       1       2       no      no      yes    no    no        0       no
47 41000    3040        2       1       1       no      no       no    no    no        0       no
48 43000    3090        3       1       2       no      no       no    no    no        0       no
49 48000    4960        4       1       3       no      no       no    no    no        0       no
50 54800    3350        3       1       2      yes      no       no    no    no        0       no
51 55000    5300        5       2       2      yes      no       no    no    no        0       no
52 57000    4100        4       1       1       no      no      yes    no    no        0       no
53 68000    9166        2       1       1      yes      no      yes    no   yes        2       no
54 95000    4040        3       1       2      yes      no      yes   yes    no        1       no
55 38000    3630        3       3       2       no     yes       no    no    no        0       no
56 25000    3620        2       1       1      yes      no       no    no    no        0       no
57 25245    2400        3       1       1       no      no       no    no    no        0       no
58 56000    7260        3       2       1      yes     yes      yes    no    no        3       no
59 35500    4400        3       1       2      yes      no       no    no    no        0       no
60 30000    2400        3       1       2      yes      no       no    no    no        0       no
61 48000    4120        2       1       2      yes      no       no    no    no        0       no
62 48000    4750        2       1       1      yes      no       no    no    no        0       no
63 52000    4280        2       1       1      yes      no       no    no   yes        2       no
64 54000    4820        3       1       2      yes      no       no    no    no        0       no
65 56000    5500        4       1       2      yes     yes      yes    no    no        0       no
66 60000    5500        3       1       2      yes      no       no    no   yes        0       no
67 60000    5040        3       1       2      yes      no      yes    no   yes        0       no
68 67000    6000        2       1       1      yes      no      yes    no   yes        1       no
69 47000    2500        2       1       1       no      no       no    no   yes        0       no
70 70000    4095        3       1       2       no     yes      yes    no   yes        0       no
71 45000    4095        2       1       1      yes      no       no    no    no        2       no
72 51000    3150        3       1       2      yes      no      yes    no    no        0       no
73 32500    1836        2       1       1       no      no      yes    no    no        0       no
74 34000    2475        3       1       2      yes      no       no    no    no        0       no
75 35000    3210        3       1       2      yes      no      yes    no    no        0       no
76 36000    3180        3       1       1       no      no       no    no    no        0       no
77 45000    1650        3       1       2       no      no      yes    no    no        0       no
78 47000    3180        4       1       2      yes      no      yes    no   yes        0       no
79 55000    3180        2       2       1      yes      no      yes    no    no        2       no
80 63900    6360        2       1       1      yes      no      yes    no   yes        1       no
81 50000    4240        3       1       2      yes      no       no    no   yes        0       no
82 35000    3240        2       1       1       no     yes       no    no    no        1       no
83 50000    3650        3       1       2      yes      no       no    no    no        0       no
 [ reached 'max' / getOption("max.print") -- omitted 463 rows ]
> 
> boston <- read.csv("C:/Datasets/Boston.csv")
> boston
      crim    zn indus chas    nox    rm   age    dis rad tax ptratio  black lstat medv
1  0.00632  18.0  2.31    0 0.5380 6.575  65.2 4.0900   1 296    15.3 396.90  4.98 24.0
2  0.02731   0.0  7.07    0 0.4690 6.421  78.9 4.9671   2 242    17.8 396.90  9.14 21.6
3  0.02729   0.0  7.07    0 0.4690 7.185  61.1 4.9671   2 242    17.8 392.83  4.03 34.7
4  0.03237   0.0  2.18    0 0.4580 6.998  45.8 6.0622   3 222    18.7 394.63  2.94 33.4
5  0.06905   0.0  2.18    0 0.4580 7.147  54.2 6.0622   3 222    18.7 396.90  5.33 36.2
6  0.02985   0.0  2.18    0 0.4580 6.430  58.7 6.0622   3 222    18.7 394.12  5.21 28.7
7  0.08829  12.5  7.87    0 0.5240 6.012  66.6 5.5605   5 311    15.2 395.60 12.43 22.9
8  0.14455  12.5  7.87    0 0.5240 6.172  96.1 5.9505   5 311    15.2 396.90 19.15 27.1
9  0.21124  12.5  7.87    0 0.5240 5.631 100.0 6.0821   5 311    15.2 386.63 29.93 16.5
10 0.17004  12.5  7.87    0 0.5240 6.004  85.9 6.5921   5 311    15.2 386.71 17.10 18.9
11 0.22489  12.5  7.87    0 0.5240 6.377  94.3 6.3467   5 311    15.2 392.52 20.45 15.0
12 0.11747  12.5  7.87    0 0.5240 6.009  82.9 6.2267   5 311    15.2 396.90 13.27 18.9
13 0.09378  12.5  7.87    0 0.5240 5.889  39.0 5.4509   5 311    15.2 390.50 15.71 21.7
14 0.62976   0.0  8.14    0 0.5380 5.949  61.8 4.7075   4 307    21.0 396.90  8.26 20.4
15 0.63796   0.0  8.14    0 0.5380 6.096  84.5 4.4619   4 307    21.0 380.02 10.26 18.2
16 0.62739   0.0  8.14    0 0.5380 5.834  56.5 4.4986   4 307    21.0 395.62  8.47 19.9
17 1.05393   0.0  8.14    0 0.5380 5.935  29.3 4.4986   4 307    21.0 386.85  6.58 23.1
18 0.78420   0.0  8.14    0 0.5380 5.990  81.7 4.2579   4 307    21.0 386.75 14.67 17.5
19 0.80271   0.0  8.14    0 0.5380 5.456  36.6 3.7965   4 307    21.0 288.99 11.69 20.2
20 0.72580   0.0  8.14    0 0.5380 5.727  69.5 3.7965   4 307    21.0 390.95 11.28 18.2
21 1.25179   0.0  8.14    0 0.5380 5.570  98.1 3.7979   4 307    21.0 376.57 21.02 13.6
22 0.85204   0.0  8.14    0 0.5380 5.965  89.2 4.0123   4 307    21.0 392.53 13.83 19.6
23 1.23247   0.0  8.14    0 0.5380 6.142  91.7 3.9769   4 307    21.0 396.90 18.72 15.2
24 0.98843   0.0  8.14    0 0.5380 5.813 100.0 4.0952   4 307    21.0 394.54 19.88 14.5
25 0.75026   0.0  8.14    0 0.5380 5.924  94.1 4.3996   4 307    21.0 394.33 16.30 15.6
26 0.84054   0.0  8.14    0 0.5380 5.599  85.7 4.4546   4 307    21.0 303.42 16.51 13.9
27 0.67191   0.0  8.14    0 0.5380 5.813  90.3 4.6820   4 307    21.0 376.88 14.81 16.6
28 0.95577   0.0  8.14    0 0.5380 6.047  88.8 4.4534   4 307    21.0 306.38 17.28 14.8
29 0.77299   0.0  8.14    0 0.5380 6.495  94.4 4.4547   4 307    21.0 387.94 12.80 18.4
30 1.00245   0.0  8.14    0 0.5380 6.674  87.3 4.2390   4 307    21.0 380.23 11.98 21.0
31 1.13081   0.0  8.14    0 0.5380 5.713  94.1 4.2330   4 307    21.0 360.17 22.60 12.7
32 1.35472   0.0  8.14    0 0.5380 6.072 100.0 4.1750   4 307    21.0 376.73 13.04 14.5
33 1.38799   0.0  8.14    0 0.5380 5.950  82.0 3.9900   4 307    21.0 232.60 27.71 13.2
34 1.15172   0.0  8.14    0 0.5380 5.701  95.0 3.7872   4 307    21.0 358.77 18.35 13.1
35 1.61282   0.0  8.14    0 0.5380 6.096  96.9 3.7598   4 307    21.0 248.31 20.34 13.5
36 0.06417   0.0  5.96    0 0.4990 5.933  68.2 3.3603   5 279    19.2 396.90  9.68 18.9
37 0.09744   0.0  5.96    0 0.4990 5.841  61.4 3.3779   5 279    19.2 377.56 11.41 20.0
38 0.08014   0.0  5.96    0 0.4990 5.850  41.5 3.9342   5 279    19.2 396.90  8.77 21.0
39 0.17505   0.0  5.96    0 0.4990 5.966  30.2 3.8473   5 279    19.2 393.43 10.13 24.7
40 0.02763  75.0  2.95    0 0.4280 6.595  21.8 5.4011   3 252    18.3 395.63  4.32 30.8
41 0.03359  75.0  2.95    0 0.4280 7.024  15.8 5.4011   3 252    18.3 395.62  1.98 34.9
42 0.12744   0.0  6.91    0 0.4480 6.770   2.9 5.7209   3 233    17.9 385.41  4.84 26.6
43 0.14150   0.0  6.91    0 0.4480 6.169   6.6 5.7209   3 233    17.9 383.37  5.81 25.3
44 0.15936   0.0  6.91    0 0.4480 6.211   6.5 5.7209   3 233    17.9 394.46  7.44 24.7
45 0.12269   0.0  6.91    0 0.4480 6.069  40.0 5.7209   3 233    17.9 389.39  9.55 21.2
46 0.17142   0.0  6.91    0 0.4480 5.682  33.8 5.1004   3 233    17.9 396.90 10.21 19.3
47 0.18836   0.0  6.91    0 0.4480 5.786  33.3 5.1004   3 233    17.9 396.90 14.15 20.0
48 0.22927   0.0  6.91    0 0.4480 6.030  85.5 5.6894   3 233    17.9 392.74 18.80 16.6
49 0.25387   0.0  6.91    0 0.4480 5.399  95.3 5.8700   3 233    17.9 396.90 30.81 14.4
50 0.21977   0.0  6.91    0 0.4480 5.602  62.0 6.0877   3 233    17.9 396.90 16.20 19.4
51 0.08873  21.0  5.64    0 0.4390 5.963  45.7 6.8147   4 243    16.8 395.56 13.45 19.7
52 0.04337  21.0  5.64    0 0.4390 6.115  63.0 6.8147   4 243    16.8 393.97  9.43 20.5
53 0.05360  21.0  5.64    0 0.4390 6.511  21.1 6.8147   4 243    16.8 396.90  5.28 25.0
54 0.04981  21.0  5.64    0 0.4390 5.998  21.4 6.8147   4 243    16.8 396.90  8.43 23.4
55 0.01360  75.0  4.00    0 0.4100 5.888  47.6 7.3197   3 469    21.1 396.90 14.80 18.9
56 0.01311  90.0  1.22    0 0.4030 7.249  21.9 8.6966   5 226    17.9 395.93  4.81 35.4
57 0.02055  85.0  0.74    0 0.4100 6.383  35.7 9.1876   2 313    17.3 396.90  5.77 24.7
58 0.01432 100.0  1.32    0 0.4110 6.816  40.5 8.3248   5 256    15.1 392.90  3.95 31.6
59 0.15445  25.0  5.13    0 0.4530 6.145  29.2 7.8148   8 284    19.7 390.68  6.86 23.3
60 0.10328  25.0  5.13    0 0.4530 5.927  47.2 6.9320   8 284    19.7 396.90  9.22 19.6
61 0.14932  25.0  5.13    0 0.4530 5.741  66.2 7.2254   8 284    19.7 395.11 13.15 18.7
62 0.17171  25.0  5.13    0 0.4530 5.966  93.4 6.8185   8 284    19.7 378.08 14.44 16.0
63 0.11027  25.0  5.13    0 0.4530 6.456  67.8 7.2255   8 284    19.7 396.90  6.73 22.2
64 0.12650  25.0  5.13    0 0.4530 6.762  43.4 7.9809   8 284    19.7 395.58  9.50 25.0
65 0.01951  17.5  1.38    0 0.4161 7.104  59.5 9.2229   3 216    18.6 393.24  8.05 33.0
66 0.03584  80.0  3.37    0 0.3980 6.290  17.8 6.6115   4 337    16.1 396.90  4.67 23.5
67 0.04379  80.0  3.37    0 0.3980 5.787  31.1 6.6115   4 337    16.1 396.90 10.24 19.4
68 0.05789  12.5  6.07    0 0.4090 5.878  21.4 6.4980   4 345    18.9 396.21  8.10 22.0
69 0.13554  12.5  6.07    0 0.4090 5.594  36.8 6.4980   4 345    18.9 396.90 13.09 17.4
70 0.12816  12.5  6.07    0 0.4090 5.885  33.0 6.4980   4 345    18.9 396.90  8.79 20.9
71 0.08826   0.0 10.81    0 0.4130 6.417   6.6 5.2873   4 305    19.2 383.73  6.72 24.2
 [ reached 'max' / getOption("max.print") -- omitted 435 rows ]
> 
> ############################################
> 
> setwd("C:/Datasets")
> 
> boston <- read.csv("Boston.csv")
> str(boston)
'data.frame':	506 obs. of  14 variables:
 $ crim   : num  0.00632 0.02731 0.02729 0.03237 0.06905 ...
 $ zn     : num  18 0 0 0 0 0 12.5 12.5 12.5 12.5 ...
 $ indus  : num  2.31 7.07 7.07 2.18 2.18 2.18 7.87 7.87 7.87 7.87 ...
 $ chas   : int  0 0 0 0 0 0 0 0 0 0 ...
 $ nox    : num  0.538 0.469 0.469 0.458 0.458 0.458 0.524 0.524 0.524 0.524 ...
 $ rm     : num  6.58 6.42 7.18 7 7.15 ...
 $ age    : num  65.2 78.9 61.1 45.8 54.2 58.7 66.6 96.1 100 85.9 ...
 $ dis    : num  4.09 4.97 4.97 6.06 6.06 ...
 $ rad    : int  1 2 2 3 3 3 5 5 5 5 ...
 $ tax    : int  296 242 242 222 222 222 311 311 311 311 ...
 $ ptratio: num  15.3 17.8 17.8 18.7 18.7 18.7 15.2 15.2 15.2 15.2 ...
 $ black  : num  397 397 393 395 397 ...
 $ lstat  : num  4.98 9.14 4.03 2.94 5.33 ...
 $ medv   : num  24 21.6 34.7 33.4 36.2 28.7 22.9 27.1 16.5 18.9 ...
> 
> bolyw <- read.csv("Bollywood_2015_2.csv", header = F)
> colnames(bolyw) <- c("movie_name", "BO", "Budget", "Verdict")
> 
> bolyw
                    movie_name     BO Budget              Verdict
1         Pyaar Ka Punchnama 2  53.25   25.0                  Hit
2                     Shandaar  38.28   68.0                 Flop
3              Singh is Bliing  74.87   92.0                 Flop
4                       Jazbaa  24.30   30.0                 Flop
5                       Talvar  24.00   22.0                 Plus
6       Kis Kisko Pyaar Karoon  44.80   20.0                  Hit
7               Calendar Girls   7.00   12.0                 Flop
8                  Katti Batti  22.96   36.0                 Flop
9                         Hero  31.75   28.0                 Plus
10                Welcome Back  96.88  100.0              Average
11                     Phantom  49.84   70.0                 Flop
12                 All is Well  12.65   36.0                 Flop
13                      Manjhi  13.36    8.5                 Plus
14                    Brothers  77.18   82.0                 Flop
15                    Drishyam  65.22   65.0              Average
16           Bajrangi Bhaijaan 318.14  125.0 All Time Blockbuster
17                   Bangistan   5.42   26.0                 Flop
18           Baahubali (Hindi) 111.38  130.0                  Hit
19                      Masaan   2.10    6.0                 Flop
20                   I Love NY   2.50   15.0                 Flop
21                      ABCD 2 105.01   60.0            Super Hit
22              Guddu Rangeela   7.97   15.0                 Flop
23         Second Hand Husband   2.61    9.0                 Flop
24                    Tanakpur   1.87    9.0                 Flop
25        Hamari Adhuri Kahani  30.21   45.0                 Flop
26             Dil Dhadakne Do  74.18   86.0                 Flop
27              Tanu Weds Manu 148.47   40.0          Blockbuster
28          Welcome To Karachi   8.00   20.0                 Flop
29                        Piku  78.69   50.0                  Hit
30              Gabbar is Back  85.41   72.0                  Hit
31               Bombay Velvet  23.87  110.0             Disaster
32        Kuch Kuch Locha Hain   4.12   16.0                 Flop
33                        Mr X  19.43   39.0                 Flop
34                       Leela  20.34   18.0              Average
35          Dharam Sankat Mein   8.15   16.0                 Flop
36             Byomkesh Bakshi  22.08   19.0              Average
37                     Hunterr  12.00   12.0              Average
38                       NH 10  31.30   21.0                  Hit
39                     Barkhaa   1.11    7.0                 Flop
40          Dum Laga Ke Haisha  28.89   13.0                  Hit
41 Dilliwali Zaalim Girlfriend   2.73   12.0                 Flop
42              Dirty Politics   7.16   15.0                 Flop
43                    Badlapur  50.04   26.0                  Hit
44                         Roy  36.32   40.0                 Flop
45                   Shamitabh  19.13   45.0                 Flop
46                        Baby  81.67   75.0             Semi Hit
47                 Khamoshiyan  11.03   11.0              Average
48       Hawaizaada Collection   3.00   25.0             Disaster
49    Dolly Ki Doli Collection  13.04   25.0                 Flop
50                          PK 330.83   90.0 All Time Blockbuster
51                       Tevar  33.96   60.0                 Flop
52                       Alone  17.29   18.0                 Flop
> 
> aster2 <- read.csv("aster2.csv")
> aster2
    Month Sales
1 January  17.5
2   March  24.5
3   April  25.1
4     May  23.1
> 
> diamonds <- read.csv2("diamonds.csv")
> diamonds
    carat       cut color clarity depth table price    x    y    z
1    0.23     Ideal     E     SI2  61.5  55.0   326 3.95 3.98 2.43
2    0.21   Premium     E     SI1  59.8  61.0   326 3.89 3.84 2.31
3    0.23      Good     E     VS1  56.9  65.0   327 4.05 4.07 2.31
4    0.29   Premium     I     VS2  62.4  58.0   334 4.20 4.23 2.63
5    0.31      Good     J     SI2  63.3  58.0   335 4.34 4.35 2.75
6    0.24 Very Good     J    VVS2  62.8  57.0   336 3.94 3.96 2.48
7    0.24 Very Good     I    VVS1  62.3  57.0   336 3.95 3.98 2.47
8    0.26 Very Good     H     SI1  61.9  55.0   337 4.07 4.11 2.53
9    0.22      Fair     E     VS2  65.1  61.0   337 3.87 3.78 2.49
10   0.23 Very Good     H     VS1  59.4  61.0   338 4.00 4.05 2.39
11   0.30      Good     J     SI1  64.0  55.0   339 4.25 4.28 2.73
12   0.23     Ideal     J     VS1  62.8  56.0   340 3.93 3.90 2.46
13   0.22   Premium     F     SI1  60.4  61.0   342 3.88 3.84 2.33
14   0.31     Ideal     J     SI2  62.2  54.0   344 4.35 4.37 2.71
15   0.20   Premium     E     SI2  60.2  62.0   345 3.79 3.75 2.27
16   0.32   Premium     E      I1  60.9  58.0   345 4.38 4.42 2.68
17   0.30     Ideal     I     SI2  62.0  54.0   348 4.31 4.34 2.68
18   0.30      Good     J     SI1  63.4  54.0   351 4.23 4.29 2.70
19   0.30      Good     J     SI1  63.8  56.0   351 4.23 4.26 2.71
20   0.30 Very Good     J     SI1  62.7  59.0   351 4.21 4.27 2.66
21   0.30      Good     I     SI2  63.3  56.0   351 4.26 4.30 2.71
22   0.23 Very Good     E     VS2  63.8  55.0   352 3.85 3.92 2.48
23   0.23 Very Good     H     VS1  61.0  57.0   353 3.94 3.96 2.41
24   0.31 Very Good     J     SI1  59.4  62.0   353 4.39 4.43 2.62
25   0.31 Very Good     J     SI1  58.1  62.0   353 4.44 4.47 2.59
26   0.23 Very Good     G    VVS2  60.4  58.0   354 3.97 4.01 2.41
27   0.24   Premium     I     VS1  62.5  57.0   355 3.97 3.94 2.47
28   0.30 Very Good     J     VS2  62.2  57.0   357 4.28 4.30 2.67
29   0.23 Very Good     D     VS2  60.5  61.0   357 3.96 3.97 2.40
30   0.23 Very Good     F     VS1  60.9  57.0   357 3.96 3.99 2.42
31   0.23 Very Good     F     VS1  60.0  57.0   402 4.00 4.03 2.41
32   0.23 Very Good     F     VS1  59.8  57.0   402 4.04 4.06 2.42
33   0.23 Very Good     E     VS1  60.7  59.0   402 3.97 4.01 2.42
34   0.23 Very Good     E     VS1  59.5  58.0   402 4.01 4.06 2.40
35   0.23 Very Good     D     VS1  61.9  58.0   402 3.92 3.96 2.44
36   0.23      Good     F     VS1  58.2  59.0   402 4.06 4.08 2.37
37   0.23      Good     E     VS1  64.1  59.0   402 3.83 3.85 2.46
38   0.31      Good     H     SI1  64.0  54.0   402 4.29 4.31 2.75
39   0.26 Very Good     D     VS2  60.8  59.0   403 4.13 4.16 2.52
40   0.33     Ideal     I     SI2  61.8  55.0   403 4.49 4.51 2.78
41   0.33     Ideal     I     SI2  61.2  56.0   403 4.49 4.50 2.75
42   0.33     Ideal     J     SI1  61.1  56.0   403 4.49 4.55 2.76
43   0.26      Good     D     VS2  65.2  56.0   403 3.99 4.02 2.61
44   0.26      Good     D     VS1  58.4  63.0   403 4.19 4.24 2.46
45   0.32      Good     H     SI2  63.1  56.0   403 4.34 4.37 2.75
46   0.29   Premium     F     SI1  62.4  58.0   403 4.24 4.26 2.65
47   0.32 Very Good     H     SI2  61.8  55.0   403 4.35 4.42 2.71
48   0.32      Good     H     SI2  63.8  56.0   403 4.36 4.38 2.79
49   0.25 Very Good     E     VS2  63.3  60.0   404 4.00 4.03 2.54
50   0.29 Very Good     H     SI2  60.7  60.0   404 4.33 4.37 2.64
51   0.24 Very Good     F     SI1  60.9  61.0   404 4.02 4.03 2.45
52   0.23     Ideal     G     VS1  61.9  54.0   404 3.93 3.95 2.44
53   0.32     Ideal     I     SI1  60.9  55.0   404 4.45 4.48 2.72
54   0.22   Premium     E     VS2  61.6  58.0   404 3.93 3.89 2.41
55   0.22   Premium     D     VS2  59.3  62.0   404 3.91 3.88 2.31
56   0.30     Ideal     I     SI2  61.0  59.0   405 4.30 4.33 2.63
57   0.30   Premium     J     SI2  59.3  61.0   405 4.43 4.38 2.61
58   0.30 Very Good     I     SI1  62.6  57.0   405 4.25 4.28 2.67
59   0.30 Very Good     I     SI1  63.0  57.0   405 4.28 4.32 2.71
60   0.30      Good     I     SI1  63.2  55.0   405 4.25 4.29 2.70
61   0.35     Ideal     I     VS1  60.9  57.0   552 4.54 4.59 2.78
62   0.30   Premium     D     SI1  62.6  59.0   552 4.23 4.27 2.66
63   0.30     Ideal     D     SI1  62.5  57.0   552 4.29 4.32 2.69
64   0.30     Ideal     D     SI1  62.1  56.0   552 4.30 4.33 2.68
65   0.42   Premium     I     SI2  61.5  59.0   552 4.78 4.84 2.96
66   0.28     Ideal     G    VVS2  61.4  56.0   553 4.19 4.22 2.58
67   0.32     Ideal     I    VVS1  62.0  55.3   553 4.39 4.42 2.73
68   0.31 Very Good     G     SI1  63.3  57.0   553 4.33 4.30 2.73
69   0.31   Premium     G     SI1  61.8  58.0   553 4.35 4.32 2.68
70   0.24   Premium     E    VVS1  60.7  58.0   553 4.01 4.03 2.44
71   0.24 Very Good     D    VVS1  61.5  60.0   553 3.97 4.00 2.45
72   0.30 Very Good     H     SI1  63.1  56.0   554 4.29 4.27 2.70
73   0.30   Premium     H     SI1  62.9  59.0   554 4.28 4.24 2.68
74   0.30   Premium     H     SI1  62.5  57.0   554 4.29 4.25 2.67
75   0.30      Good     H     SI1  63.7  57.0   554 4.28 4.26 2.72
76   0.26 Very Good     F    VVS2  59.2  60.0   554 4.19 4.22 2.49
77   0.26 Very Good     E    VVS2  59.9  58.0   554 4.15 4.23 2.51
78   0.26 Very Good     D    VVS2  62.4  54.0   554 4.08 4.13 2.56
79   0.26 Very Good     D    VVS2  62.8  60.0   554 4.01 4.05 2.53
80   0.26 Very Good     E    VVS1  62.6  59.0   554 4.06 4.09 2.55
81   0.26 Very Good     E    VVS1  63.4  59.0   554 4.00 4.04 2.55
82   0.26 Very Good     D    VVS1  62.1  60.0   554 4.03 4.12 2.53
83   0.26     Ideal     E    VVS2  62.9  58.0   554 4.02 4.06 2.54
84   0.38     Ideal     I     SI2  61.6  56.0   554 4.65 4.67 2.87
85   0.26      Good     E    VVS1  57.9  60.0   554 4.22 4.25 2.45
86   0.24   Premium     G    VVS1  62.3  59.0   554 3.95 3.92 2.45
87   0.24   Premium     H    VVS1  61.2  58.0   554 4.01 3.96 2.44
88   0.24   Premium     H    VVS1  60.8  59.0   554 4.02 4.00 2.44
89   0.24   Premium     H    VVS2  60.7  58.0   554 4.07 4.04 2.46
90   0.32   Premium     I     SI1  62.9  58.0   554 4.35 4.33 2.73
91   0.70     Ideal     E     SI1  62.5  57.0  2757 5.70 5.72 3.57
92   0.86      Fair     E     SI2  55.1  69.0  2757 6.45 6.33 3.52
93   0.70     Ideal     G     VS2  61.6  56.0  2757 5.70 5.67 3.50
94   0.71 Very Good     E     VS2  62.4  57.0  2759 5.68 5.73 3.56
95   0.78 Very Good     G     SI2  63.8  56.0  2759 5.81 5.85 3.72
96   0.70      Good     E     VS2  57.5  58.0  2759 5.85 5.90 3.38
97   0.70      Good     F     VS1  59.4  62.0  2759 5.71 5.76 3.40
98   0.96      Fair     F     SI2  66.3  62.0  2759 6.27 5.95 4.07
99   0.73 Very Good     E     SI1  61.6  59.0  2760 5.77 5.78 3.56
100  0.80   Premium     H     SI1  61.5  58.0  2760 5.97 5.93 3.66
 [ reached 'max' / getOption("max.print") -- omitted 53840 rows ]
> 
> diamonds <- read.csv2("diamonds.csv", sep = ";", dec = ",")
> diamonds
    carat       cut color clarity depth table price    x    y    z
1    0.23     Ideal     E     SI2  61.5  55.0   326 3.95 3.98 2.43
2    0.21   Premium     E     SI1  59.8  61.0   326 3.89 3.84 2.31
3    0.23      Good     E     VS1  56.9  65.0   327 4.05 4.07 2.31
4    0.29   Premium     I     VS2  62.4  58.0   334 4.20 4.23 2.63
5    0.31      Good     J     SI2  63.3  58.0   335 4.34 4.35 2.75
6    0.24 Very Good     J    VVS2  62.8  57.0   336 3.94 3.96 2.48
7    0.24 Very Good     I    VVS1  62.3  57.0   336 3.95 3.98 2.47
8    0.26 Very Good     H     SI1  61.9  55.0   337 4.07 4.11 2.53
9    0.22      Fair     E     VS2  65.1  61.0   337 3.87 3.78 2.49
10   0.23 Very Good     H     VS1  59.4  61.0   338 4.00 4.05 2.39
11   0.30      Good     J     SI1  64.0  55.0   339 4.25 4.28 2.73
12   0.23     Ideal     J     VS1  62.8  56.0   340 3.93 3.90 2.46
13   0.22   Premium     F     SI1  60.4  61.0   342 3.88 3.84 2.33
14   0.31     Ideal     J     SI2  62.2  54.0   344 4.35 4.37 2.71
15   0.20   Premium     E     SI2  60.2  62.0   345 3.79 3.75 2.27
16   0.32   Premium     E      I1  60.9  58.0   345 4.38 4.42 2.68
17   0.30     Ideal     I     SI2  62.0  54.0   348 4.31 4.34 2.68
18   0.30      Good     J     SI1  63.4  54.0   351 4.23 4.29 2.70
19   0.30      Good     J     SI1  63.8  56.0   351 4.23 4.26 2.71
20   0.30 Very Good     J     SI1  62.7  59.0   351 4.21 4.27 2.66
21   0.30      Good     I     SI2  63.3  56.0   351 4.26 4.30 2.71
22   0.23 Very Good     E     VS2  63.8  55.0   352 3.85 3.92 2.48
23   0.23 Very Good     H     VS1  61.0  57.0   353 3.94 3.96 2.41
24   0.31 Very Good     J     SI1  59.4  62.0   353 4.39 4.43 2.62
25   0.31 Very Good     J     SI1  58.1  62.0   353 4.44 4.47 2.59
26   0.23 Very Good     G    VVS2  60.4  58.0   354 3.97 4.01 2.41
27   0.24   Premium     I     VS1  62.5  57.0   355 3.97 3.94 2.47
28   0.30 Very Good     J     VS2  62.2  57.0   357 4.28 4.30 2.67
29   0.23 Very Good     D     VS2  60.5  61.0   357 3.96 3.97 2.40
30   0.23 Very Good     F     VS1  60.9  57.0   357 3.96 3.99 2.42
31   0.23 Very Good     F     VS1  60.0  57.0   402 4.00 4.03 2.41
32   0.23 Very Good     F     VS1  59.8  57.0   402 4.04 4.06 2.42
33   0.23 Very Good     E     VS1  60.7  59.0   402 3.97 4.01 2.42
34   0.23 Very Good     E     VS1  59.5  58.0   402 4.01 4.06 2.40
35   0.23 Very Good     D     VS1  61.9  58.0   402 3.92 3.96 2.44
36   0.23      Good     F     VS1  58.2  59.0   402 4.06 4.08 2.37
37   0.23      Good     E     VS1  64.1  59.0   402 3.83 3.85 2.46
38   0.31      Good     H     SI1  64.0  54.0   402 4.29 4.31 2.75
39   0.26 Very Good     D     VS2  60.8  59.0   403 4.13 4.16 2.52
40   0.33     Ideal     I     SI2  61.8  55.0   403 4.49 4.51 2.78
41   0.33     Ideal     I     SI2  61.2  56.0   403 4.49 4.50 2.75
42   0.33     Ideal     J     SI1  61.1  56.0   403 4.49 4.55 2.76
43   0.26      Good     D     VS2  65.2  56.0   403 3.99 4.02 2.61
44   0.26      Good     D     VS1  58.4  63.0   403 4.19 4.24 2.46
45   0.32      Good     H     SI2  63.1  56.0   403 4.34 4.37 2.75
46   0.29   Premium     F     SI1  62.4  58.0   403 4.24 4.26 2.65
47   0.32 Very Good     H     SI2  61.8  55.0   403 4.35 4.42 2.71
48   0.32      Good     H     SI2  63.8  56.0   403 4.36 4.38 2.79
49   0.25 Very Good     E     VS2  63.3  60.0   404 4.00 4.03 2.54
50   0.29 Very Good     H     SI2  60.7  60.0   404 4.33 4.37 2.64
51   0.24 Very Good     F     SI1  60.9  61.0   404 4.02 4.03 2.45
52   0.23     Ideal     G     VS1  61.9  54.0   404 3.93 3.95 2.44
53   0.32     Ideal     I     SI1  60.9  55.0   404 4.45 4.48 2.72
54   0.22   Premium     E     VS2  61.6  58.0   404 3.93 3.89 2.41
55   0.22   Premium     D     VS2  59.3  62.0   404 3.91 3.88 2.31
56   0.30     Ideal     I     SI2  61.0  59.0   405 4.30 4.33 2.63
57   0.30   Premium     J     SI2  59.3  61.0   405 4.43 4.38 2.61
58   0.30 Very Good     I     SI1  62.6  57.0   405 4.25 4.28 2.67
59   0.30 Very Good     I     SI1  63.0  57.0   405 4.28 4.32 2.71
60   0.30      Good     I     SI1  63.2  55.0   405 4.25 4.29 2.70
61   0.35     Ideal     I     VS1  60.9  57.0   552 4.54 4.59 2.78
62   0.30   Premium     D     SI1  62.6  59.0   552 4.23 4.27 2.66
63   0.30     Ideal     D     SI1  62.5  57.0   552 4.29 4.32 2.69
64   0.30     Ideal     D     SI1  62.1  56.0   552 4.30 4.33 2.68
65   0.42   Premium     I     SI2  61.5  59.0   552 4.78 4.84 2.96
66   0.28     Ideal     G    VVS2  61.4  56.0   553 4.19 4.22 2.58
67   0.32     Ideal     I    VVS1  62.0  55.3   553 4.39 4.42 2.73
68   0.31 Very Good     G     SI1  63.3  57.0   553 4.33 4.30 2.73
69   0.31   Premium     G     SI1  61.8  58.0   553 4.35 4.32 2.68
70   0.24   Premium     E    VVS1  60.7  58.0   553 4.01 4.03 2.44
71   0.24 Very Good     D    VVS1  61.5  60.0   553 3.97 4.00 2.45
72   0.30 Very Good     H     SI1  63.1  56.0   554 4.29 4.27 2.70
73   0.30   Premium     H     SI1  62.9  59.0   554 4.28 4.24 2.68
74   0.30   Premium     H     SI1  62.5  57.0   554 4.29 4.25 2.67
75   0.30      Good     H     SI1  63.7  57.0   554 4.28 4.26 2.72
76   0.26 Very Good     F    VVS2  59.2  60.0   554 4.19 4.22 2.49
77   0.26 Very Good     E    VVS2  59.9  58.0   554 4.15 4.23 2.51
78   0.26 Very Good     D    VVS2  62.4  54.0   554 4.08 4.13 2.56
79   0.26 Very Good     D    VVS2  62.8  60.0   554 4.01 4.05 2.53
80   0.26 Very Good     E    VVS1  62.6  59.0   554 4.06 4.09 2.55
81   0.26 Very Good     E    VVS1  63.4  59.0   554 4.00 4.04 2.55
82   0.26 Very Good     D    VVS1  62.1  60.0   554 4.03 4.12 2.53
83   0.26     Ideal     E    VVS2  62.9  58.0   554 4.02 4.06 2.54
84   0.38     Ideal     I     SI2  61.6  56.0   554 4.65 4.67 2.87
85   0.26      Good     E    VVS1  57.9  60.0   554 4.22 4.25 2.45
86   0.24   Premium     G    VVS1  62.3  59.0   554 3.95 3.92 2.45
87   0.24   Premium     H    VVS1  61.2  58.0   554 4.01 3.96 2.44
88   0.24   Premium     H    VVS1  60.8  59.0   554 4.02 4.00 2.44
89   0.24   Premium     H    VVS2  60.7  58.0   554 4.07 4.04 2.46
90   0.32   Premium     I     SI1  62.9  58.0   554 4.35 4.33 2.73
91   0.70     Ideal     E     SI1  62.5  57.0  2757 5.70 5.72 3.57
92   0.86      Fair     E     SI2  55.1  69.0  2757 6.45 6.33 3.52
93   0.70     Ideal     G     VS2  61.6  56.0  2757 5.70 5.67 3.50
94   0.71 Very Good     E     VS2  62.4  57.0  2759 5.68 5.73 3.56
95   0.78 Very Good     G     SI2  63.8  56.0  2759 5.81 5.85 3.72
96   0.70      Good     E     VS2  57.5  58.0  2759 5.85 5.90 3.38
97   0.70      Good     F     VS1  59.4  62.0  2759 5.71 5.76 3.40
98   0.96      Fair     F     SI2  66.3  62.0  2759 6.27 5.95 4.07
99   0.73 Very Good     E     SI1  61.6  59.0  2760 5.77 5.78 3.56
100  0.80   Premium     H     SI1  61.5  58.0  2760 5.97 5.93 3.66

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

> library(readxl)
Warning message:
package ‘readxl’ was built under R version 4.4.3 
> quality <- read_excel("quality.xlsx")
New names:
• `Id` -> `Id...1`
• `` -> `...5`
• `` -> `...6`
• `` -> `...7`
• `Id` -> `Id...8`
> quality
# A tibble: 15 × 10
   Id...1 `Policy A` `Policy B` `Policy C` ...5  ...6  ...7  Id...8 Policy   Value
    <dbl>      <dbl>      <dbl>      <dbl> <lgl> <lgl> <lgl>  <dbl> <chr>    <dbl>
 1      1         97         93         99 NA    NA    NA         1 Policy A    97
 2      2         73         14         94 NA    NA    NA         2 Policy A    73
 3      3         93         93         87 NA    NA    NA         3 Policy A    93
 4      4        100         55         66 NA    NA    NA         4 Policy A   100
 5      5         23         77         59 NA    NA    NA         5 Policy A    23
 6     NA         NA         NA         NA NA    NA    NA         1 Policy B    93
 7     NA         NA         NA         NA NA    NA    NA         2 Policy B    14
 8     NA         NA         NA         NA NA    NA    NA         3 Policy B    93
 9     NA         NA         NA         NA NA    NA    NA         4 Policy B    55
10     NA         NA         NA         NA NA    NA    NA         5 Policy B    77
11     NA         NA         NA         NA NA    NA    NA         1 Policy C    99
12     NA         NA         NA         NA NA    NA    NA         2 Policy C    94
13     NA         NA         NA         NA NA    NA    NA         3 Policy C    87
14     NA         NA         NA         NA NA    NA    NA         4 Policy C    66
15     NA         NA         NA         NA NA    NA    NA         5 Policy C    59
> 
> qual1 <- read_excel("quality.xlsx",
+                     range = "A1:C6", sheet = "quality")
> qual1
# A tibble: 5 × 3
     Id `Policy A` `Policy B`
  <dbl>      <dbl>      <dbl>
1     1         97         93
2     2         73         14
3     3         93         93
4     4        100         55
5     5         23         77
> qual2 <- read_excel("quality.xlsx",
+                     range = "H1:J16", sheet = "quality")
> qual2
# A tibble: 15 × 3
      Id Policy   Value
   <dbl> <chr>    <dbl>
 1     1 Policy A    97
 2     2 Policy A    73
 3     3 Policy A    93
 4     4 Policy A   100
 5     5 Policy A    23
 6     1 Policy B    93
 7     2 Policy B    14
 8     3 Policy B    93
 9     4 Policy B    55
10     5 Policy B    77
11     1 Policy C    99
12     2 Policy C    94
13     3 Policy C    87
14     4 Policy C    66
15     5 Policy C    59
> 
> data("Formaldehyde")
> Formaldehyde
  carb optden
1  0.1  0.086
2  0.3  0.269
3  0.5  0.446
4  0.6  0.538
5  0.7  0.626
6  0.9  0.782
> write.csv(Formaldehyde, "C:/Datasets/Formaldehyde.csv")
> 
> write.csv(Formaldehyde, "C:/Datasets/Formaldehyde.csv", row.names = F)
> 
> fdf = read.csv("C:/Datasets/Formaldehyde.csv")
> fdf
  carb optden
1  0.1  0.086
2  0.3  0.269
3  0.5  0.446
4  0.6  0.538
5  0.7  0.626
6  0.9  0.782
> 
> library(writexl)
Warning message:
package ‘writexl’ was built under R version 4.4.3 
> 
> write_xlsx(Formaldehyde, "C:/Datasets/Formal.xlsx")

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

> # SUBSETTING
> 
> v=c(56,89,10,90,45,67,22,30)
> v>50
[1]  TRUE  TRUE FALSE  TRUE FALSE  TRUE FALSE FALSE
> v[v>50]
[1] 56 89 90 67

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

> # MATRIX
> 
> m = matrix(1:12, 4:4)
> m
     [,1] [,2] [,3]
[1,]    1    5    9
[2,]    2    6   10
[3,]    3    7   11
[4,]    4    8   12
> 
> m[2, ]
[1]  2  6 10
> m[, 2]
[1] 5 6 7 8

Specifying the column / row indices:
• Subsetting can be done to a data frame by specifying rows / columns

> Formaldehyde
  carb optden
1  0.1  0.086
2  0.3  0.269
3  0.5  0.446
4  0.6  0.538
5  0.7  0.626
6  0.9  0.782
> Formaldehyde[2, ]
  carb optden
2  0.3  0.269
> Formaldehyde[c(1, 4, 6), ]
  carb optden
1  0.1  0.086
4  0.6  0.538
6  0.9  0.782
> Formaldehyde[c(1, 4, 6), 2]
[1] 0.086 0.538 0.782


subset ():
• subset() function gives the data frame object
Syntax: subset(data frame , condition, select, …)

> diamonds
    carat       cut color clarity depth table price    x    y    z
1    0.23     Ideal     E     SI2  61.5  55.0   326 3.95 3.98 2.43
2    0.21   Premium     E     SI1  59.8  61.0   326 3.89 3.84 2.31
3    0.23      Good     E     VS1  56.9  65.0   327 4.05 4.07 2.31
4    0.29   Premium     I     VS2  62.4  58.0   334 4.20 4.23 2.63
5    0.31      Good     J     SI2  63.3  58.0   335 4.34 4.35 2.75
6    0.24 Very Good     J    VVS2  62.8  57.0   336 3.94 3.96 2.48
7    0.24 Very Good     I    VVS1  62.3  57.0   336 3.95 3.98 2.47
8    0.26 Very Good     H     SI1  61.9  55.0   337 4.07 4.11 2.53
9    0.22      Fair     E     VS2  65.1  61.0   337 3.87 3.78 2.49
10   0.23 Very Good     H     VS1  59.4  61.0   338 4.00 4.05 2.39
11   0.30      Good     J     SI1  64.0  55.0   339 4.25 4.28 2.73
12   0.23     Ideal     J     VS1  62.8  56.0   340 3.93 3.90 2.46
13   0.22   Premium     F     SI1  60.4  61.0   342 3.88 3.84 2.33
14   0.31     Ideal     J     SI2  62.2  54.0   344 4.35 4.37 2.71
15   0.20   Premium     E     SI2  60.2  62.0   345 3.79 3.75 2.27
16   0.32   Premium     E      I1  60.9  58.0   345 4.38 4.42 2.68
17   0.30     Ideal     I     SI2  62.0  54.0   348 4.31 4.34 2.68
18   0.30      Good     J     SI1  63.4  54.0   351 4.23 4.29 2.70
19   0.30      Good     J     SI1  63.8  56.0   351 4.23 4.26 2.71
20   0.30 Very Good     J     SI1  62.7  59.0   351 4.21 4.27 2.66
21   0.30      Good     I     SI2  63.3  56.0   351 4.26 4.30 2.71
22   0.23 Very Good     E     VS2  63.8  55.0   352 3.85 3.92 2.48
23   0.23 Very Good     H     VS1  61.0  57.0   353 3.94 3.96 2.41
24   0.31 Very Good     J     SI1  59.4  62.0   353 4.39 4.43 2.62
25   0.31 Very Good     J     SI1  58.1  62.0   353 4.44 4.47 2.59
26   0.23 Very Good     G    VVS2  60.4  58.0   354 3.97 4.01 2.41
27   0.24   Premium     I     VS1  62.5  57.0   355 3.97 3.94 2.47
28   0.30 Very Good     J     VS2  62.2  57.0   357 4.28 4.30 2.67
29   0.23 Very Good     D     VS2  60.5  61.0   357 3.96 3.97 2.40
30   0.23 Very Good     F     VS1  60.9  57.0   357 3.96 3.99 2.42
31   0.23 Very Good     F     VS1  60.0  57.0   402 4.00 4.03 2.41
32   0.23 Very Good     F     VS1  59.8  57.0   402 4.04 4.06 2.42
33   0.23 Very Good     E     VS1  60.7  59.0   402 3.97 4.01 2.42
34   0.23 Very Good     E     VS1  59.5  58.0   402 4.01 4.06 2.40
35   0.23 Very Good     D     VS1  61.9  58.0   402 3.92 3.96 2.44
36   0.23      Good     F     VS1  58.2  59.0   402 4.06 4.08 2.37
37   0.23      Good     E     VS1  64.1  59.0   402 3.83 3.85 2.46
38   0.31      Good     H     SI1  64.0  54.0   402 4.29 4.31 2.75
39   0.26 Very Good     D     VS2  60.8  59.0   403 4.13 4.16 2.52
40   0.33     Ideal     I     SI2  61.8  55.0   403 4.49 4.51 2.78
41   0.33     Ideal     I     SI2  61.2  56.0   403 4.49 4.50 2.75
42   0.33     Ideal     J     SI1  61.1  56.0   403 4.49 4.55 2.76
43   0.26      Good     D     VS2  65.2  56.0   403 3.99 4.02 2.61
44   0.26      Good     D     VS1  58.4  63.0   403 4.19 4.24 2.46
45   0.32      Good     H     SI2  63.1  56.0   403 4.34 4.37 2.75
46   0.29   Premium     F     SI1  62.4  58.0   403 4.24 4.26 2.65
47   0.32 Very Good     H     SI2  61.8  55.0   403 4.35 4.42 2.71
48   0.32      Good     H     SI2  63.8  56.0   403 4.36 4.38 2.79
49   0.25 Very Good     E     VS2  63.3  60.0   404 4.00 4.03 2.54
50   0.29 Very Good     H     SI2  60.7  60.0   404 4.33 4.37 2.64
51   0.24 Very Good     F     SI1  60.9  61.0   404 4.02 4.03 2.45
52   0.23     Ideal     G     VS1  61.9  54.0   404 3.93 3.95 2.44
53   0.32     Ideal     I     SI1  60.9  55.0   404 4.45 4.48 2.72
54   0.22   Premium     E     VS2  61.6  58.0   404 3.93 3.89 2.41
55   0.22   Premium     D     VS2  59.3  62.0   404 3.91 3.88 2.31
56   0.30     Ideal     I     SI2  61.0  59.0   405 4.30 4.33 2.63
57   0.30   Premium     J     SI2  59.3  61.0   405 4.43 4.38 2.61
58   0.30 Very Good     I     SI1  62.6  57.0   405 4.25 4.28 2.67
59   0.30 Very Good     I     SI1  63.0  57.0   405 4.28 4.32 2.71
60   0.30      Good     I     SI1  63.2  55.0   405 4.25 4.29 2.70
61   0.35     Ideal     I     VS1  60.9  57.0   552 4.54 4.59 2.78
62   0.30   Premium     D     SI1  62.6  59.0   552 4.23 4.27 2.66
63   0.30     Ideal     D     SI1  62.5  57.0   552 4.29 4.32 2.69
64   0.30     Ideal     D     SI1  62.1  56.0   552 4.30 4.33 2.68
65   0.42   Premium     I     SI2  61.5  59.0   552 4.78 4.84 2.96
66   0.28     Ideal     G    VVS2  61.4  56.0   553 4.19 4.22 2.58
67   0.32     Ideal     I    VVS1  62.0  55.3   553 4.39 4.42 2.73
68   0.31 Very Good     G     SI1  63.3  57.0   553 4.33 4.30 2.73
69   0.31   Premium     G     SI1  61.8  58.0   553 4.35 4.32 2.68
70   0.24   Premium     E    VVS1  60.7  58.0   553 4.01 4.03 2.44
71   0.24 Very Good     D    VVS1  61.5  60.0   553 3.97 4.00 2.45
72   0.30 Very Good     H     SI1  63.1  56.0   554 4.29 4.27 2.70
73   0.30   Premium     H     SI1  62.9  59.0   554 4.28 4.24 2.68
74   0.30   Premium     H     SI1  62.5  57.0   554 4.29 4.25 2.67
75   0.30      Good     H     SI1  63.7  57.0   554 4.28 4.26 2.72
76   0.26 Very Good     F    VVS2  59.2  60.0   554 4.19 4.22 2.49
77   0.26 Very Good     E    VVS2  59.9  58.0   554 4.15 4.23 2.51
78   0.26 Very Good     D    VVS2  62.4  54.0   554 4.08 4.13 2.56
79   0.26 Very Good     D    VVS2  62.8  60.0   554 4.01 4.05 2.53
80   0.26 Very Good     E    VVS1  62.6  59.0   554 4.06 4.09 2.55
81   0.26 Very Good     E    VVS1  63.4  59.0   554 4.00 4.04 2.55
82   0.26 Very Good     D    VVS1  62.1  60.0   554 4.03 4.12 2.53
83   0.26     Ideal     E    VVS2  62.9  58.0   554 4.02 4.06 2.54
84   0.38     Ideal     I     SI2  61.6  56.0   554 4.65 4.67 2.87
85   0.26      Good     E    VVS1  57.9  60.0   554 4.22 4.25 2.45
86   0.24   Premium     G    VVS1  62.3  59.0   554 3.95 3.92 2.45
87   0.24   Premium     H    VVS1  61.2  58.0   554 4.01 3.96 2.44
88   0.24   Premium     H    VVS1  60.8  59.0   554 4.02 4.00 2.44
89   0.24   Premium     H    VVS2  60.7  58.0   554 4.07 4.04 2.46
90   0.32   Premium     I     SI1  62.9  58.0   554 4.35 4.33 2.73
91   0.70     Ideal     E     SI1  62.5  57.0  2757 5.70 5.72 3.57
92   0.86      Fair     E     SI2  55.1  69.0  2757 6.45 6.33 3.52
93   0.70     Ideal     G     VS2  61.6  56.0  2757 5.70 5.67 3.50
94   0.71 Very Good     E     VS2  62.4  57.0  2759 5.68 5.73 3.56
95   0.78 Very Good     G     SI2  63.8  56.0  2759 5.81 5.85 3.72
96   0.70      Good     E     VS2  57.5  58.0  2759 5.85 5.90 3.38
97   0.70      Good     F     VS1  59.4  62.0  2759 5.71 5.76 3.40
98   0.96      Fair     F     SI2  66.3  62.0  2759 6.27 5.95 4.07
99   0.73 Very Good     E     SI1  61.6  59.0  2760 5.77 5.78 3.56
100  0.80   Premium     H     SI1  61.5  58.0  2760 5.97 5.93 3.66
 [ reached 'max' / getOption("max.print") -- omitted 53840 rows ]
> diamonds[, c(3, 4)]
    color clarity
1       E     SI2
2       E     SI1
3       E     VS1
4       I     VS2
5       J     SI2
6       J    VVS2
7       I    VVS1
8       H     SI1
9       E     VS2
10      H     VS1
11      J     SI1
12      J     VS1
13      F     SI1
14      J     SI2
15      E     SI2
16      E      I1
17      I     SI2
18      J     SI1
19      J     SI1
20      J     SI1
21      I     SI2
22      E     VS2
23      H     VS1
24      J     SI1
25      J     SI1
26      G    VVS2
27      I     VS1
28      J     VS2
29      D     VS2
30      F     VS1
31      F     VS1
32      F     VS1
33      E     VS1
34      E     VS1
35      D     VS1
36      F     VS1
37      E     VS1
38      H     SI1
39      D     VS2
40      I     SI2
41      I     SI2
42      J     SI1
43      D     VS2
44      D     VS1
45      H     SI2
46      F     SI1
47      H     SI2
48      H     SI2
49      E     VS2
50      H     SI2
51      F     SI1
52      G     VS1
53      I     SI1
54      E     VS2
55      D     VS2
56      I     SI2
57      J     SI2
58      I     SI1
59      I     SI1
60      I     SI1
61      I     VS1
62      D     SI1
63      D     SI1
64      D     SI1
65      I     SI2
66      G    VVS2
67      I    VVS1
68      G     SI1
69      G     SI1
70      E    VVS1
71      D    VVS1
72      H     SI1
73      H     SI1
74      H     SI1
75      H     SI1
76      F    VVS2
77      E    VVS2
78      D    VVS2
79      D    VVS2
80      E    VVS1
81      E    VVS1
82      D    VVS1
83      E    VVS2
84      I     SI2
85      E    VVS1
86      G    VVS1
87      H    VVS1
88      H    VVS1
89      H    VVS2
90      I     SI1
91      E     SI1
92      E     SI2
93      G     VS2
94      E     VS2
95      G     SI2
96      E     VS2
97      F     VS1
98      F     SI2
99      E     SI1
100     H     SI1
101     D     SI1
102     E     SI1
103     G     SI1
104     G     VS2
105     I     VS1
106     G     SI1
107     G     SI1
108     I    VVS2
109     F     SI2
110     E    VVS2
111     F     SI2
112     E     SI2
113     I     VS2
114     G     SI1
115     F     VS2
116     F     VS2
117     F     SI2
118     G     VS2
119     E     VS2
120     F     SI2
121     D     SI2
122     E     SI1
123     F     VS2
124     F     VS2
125     F     VS2
126     F     VS2
127     H     SI1
128     D    VVS2
129     H     SI2
130     H     SI2
131     H     VS2
132     D     SI1
133     D     SI1
134     E     VS2
135     H     VS1
136     E    VVS1
137     F     VS1
138     F     VS1
139     H     SI1
140     G    VVS1
141     G     VS2
142     G     VS2
143     D     VS2
144     F     VS1
145     D     SI2
146     H    VVS2
147     G     VS1
148     D     SI1
149     D     SI1
150     E     SI1
151     D     SI2
152     I     SI1
153     D     VS2
154     G     VS2
155     F     SI1
156     D     SI2
157     F     SI1
158     G     VS2
159     G     VS1
160     D     SI2
161     G     VS2
162     H    VVS2
163     F     SI1
164     G     VS2
165     F     SI2
166     H    VVS1
167     F     SI2
168     G    VVS1
169     F    VVS1
170     E     VS2
171     D     SI2
172     D     VS2
173     J      I1
174     E     VS1
175     E     SI1
176     I     VS2
177     F     VS2
178     G     VS2
179     E     VS2
180     E     VS2
181     E    VVS2
182     E    VVS2
183     G     SI1
184     G     SI1
185     G     VS2
186     G     SI1
187     D     VS1
188     F     VS2
189     F     VS2
190     F     VS2
191     F     VS2
192     E     VS2
193     E     VS2
194     E     SI1
195     E     SI1
196     E     SI1
197     E     SI1
198     E     SI1
199     E     SI1
200     F     SI1
201     E     SI1
202     E     SI1
203     E     SI1
204     E     VS2
205     H     SI2
206     F     SI1
207     E     SI1
208     F    VVS1
209     H     VS2
210     E     SI1
211     F     VS2
212     G     VS2
213     F     VS2
214     G     VS1
215     G     VS1
216     F      I1
217     H     SI1
218     H     SI1
219     H     VS1
220     D    VVS2
221     G     VS2
222     E     VS1
223     E     VS1
224     D     SI2
225     D     SI1
226     D     SI1
227     D     SI1
228     G     SI1
229     F     SI1
230     F      IF
231     F     VS2
232     H     VS1
233     F     VS2
234     F    VVS1
235     D     VS1
236     H    VVS1
237     I     VS1
238     I    VVS2
239     D     VS2
240     G     VS1
241     F     SI1
242     E      I1
243     H     SI2
244     F     SI1
245     E     SI1
246     E     SI1
247     E     SI1
248     J     SI2
249     G     SI2
250     E     SI1
251     G      IF
252     G     SI2
253     E    VVS2
254     E    VVS1
255     H     VS1
256     J     SI2
257     G      IF
258     I    VVS1
259     F     SI2
260     F     VS1
261     F     VS1
262     I     SI1
263     E     SI1
264     E     SI1
265     E     SI1
266     E     SI1
267     F     VS1
268     F     VS1
269     H    VVS2
270     F     VS1
271     G     SI1
272     E     VS2
273     E     VS2
274     I     VS2
275     H     VS2
276     E     SI1
277     E     VS2
278     I    VVS2
279     F     SI2
280     F     VS1
281     D     SI2
282     I      IF
283     H     VS2
284     G     VS2
285     I     SI2
286     E     SI1
287     H     SI2
288     E     SI1
289     D     SI1
290     D     SI1
291     D     SI1
292     F    VVS2
293     D    VVS1
294     G     VS2
295     H     VS1
296     H     VS1
297     G    VVS1
298     F     SI2
299     E     SI2
300     H     VS2
301     I     VS1
302     E     SI2
303     F     SI2
304     D     SI1
305     G      IF
306     I     SI2
307     E     VS1
308     I     SI2
309     G     SI1
310     G     SI1
311     H     SI1
312     G     VS1
313     I     VS1
314     G      IF
315     G     VS1
316     F      I1
317     F     VS2
318     F     VS2
319     H     SI1
320     F     VS2
321     F     VS2
322     F     VS2
323     F     VS2
324     G      I1
325     J     SI2
326     G     SI2
327     F      IF
328     E     VS2
329     F     VS1
330     F     VS2
331     E     SI1
332     G     VS2
333     E     SI1
334     G     VS1
335     F     VS2
336     F     VS2
337     G     VS1
338     G     VS2
339     G     VS2
340     G     VS2
341     G     VS1
342     D     SI2
343     E     VS2
344     E     VS2
345     E     SI2
346     D     SI1
347     F     VS1
348     F     VS1
349     H     VS2
350     D     SI1
351     D     SI1
352     D     SI1
353     I     SI1
354     F     VS2
355     F     VS2
356     E     SI2
357     E    VVS1
358     F     VS2
359     G     VS2
360     F     VS2
361     G     VS2
362     G     SI1
363     H    VVS1
364     F     SI1
365     F     VS1
366     F     VS1
367     J     SI2
368     H     VS2
369     F     VS1
370     G      I1
371     G     VS2
372     E    VVS2
373     D     SI1
374     F     SI1
375     D     SI2
376     F     SI1
377     F      I1
378     F     VS1
379     F     VS1
380     D     SI2
381     F     VS1
382     G     SI1
383     F     SI1
384     D     SI1
385     J     VS2
386     I     SI2
387     G     VS1
388     F     VS2
389     E     SI1
390     F     VS2
391     I     SI1
392     I     SI1
393     I     SI1
394     I     SI1
395     I     SI1
396     I     SI1
397     H     SI1
398     H     SI1
399     H     SI1
400     H     SI1
401     H     SI1
402     H     SI1
403     H     SI1
404     I     SI1
405     H     SI2
406     E     VS1
407     E     VS1
408     F     SI1
409     H     VS2
410     H     VS2
411     I     VS1
412     I     VS1
413     G     VS1
414     F     VS1
415     G     SI1
416     E      I1
417     F     VS2
418     I     VS2
419     G     VS2
420     E     VS1
421     F     VS2
422     F     VS2
423     D     SI1
424     J     SI1
425     E     VS2
426     F    VVS1
427     G     SI2
428     E     SI1
429     I     VS2
430     E     SI1
431     E     SI1
432     E     SI1
433     D    VVS1
434     F     SI2
435     G     VS1
436     H     SI1
437     H     SI1
438     H     SI1
439     H     SI1
440     J     VS2
441     F     SI2
442     H     SI2
443     E     VS2
444     E     SI2
445     G      I1
446     I    VVS2
447     G    VVS2
448     D     VS1
449     F     SI1
450     H     SI2
451     H     SI1
452     E     SI1
453     I    VVS2
454     E     VS2
455     E     VS2
456     F    VVS2
457     E     SI1
458     E     SI1
459     E     SI1
460     E     SI1
461     J     VS2
462     E     SI1
463     E     VS2
464     E     VS2
465     E     VS2
466     H      I1
467     F     SI2
468     H     SI1
469     E     VS1
470     E     VS1
471     F     VS2
472     E     VS1
473     H     SI2
474     G     VS1
475     H     VS1
476     F     VS1
477     F     SI2
478     G     VS1
479     E     SI1
480     E     VS2
481     E    VVS1
482     E     SI1
483     E     SI1
484     E     SI1
485     E     SI1
486     D     SI1
487     E     SI1
488     E     VS1
489     E     VS2
490     E     VS2
491     E     VS2
492     E     VS2
493     F    VVS2
494     I    VVS1
495     F     SI1
496     D     SI1
497     D     SI1
498     D     SI1
499     D     SI1
500     J     VS2
 [ reached 'max' / getOption("max.print") -- omitted 53440 rows ]
> diamonds[1:10, c(3, 4)]
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
> ss = subset(diamonds, carat > 4)
> ss2 = subset(diamonds, cut == "Ideal")
> ss2
    carat   cut color clarity depth table price    x    y    z
1    0.23 Ideal     E     SI2  61.5  55.0   326 3.95 3.98 2.43
12   0.23 Ideal     J     VS1  62.8  56.0   340 3.93 3.90 2.46
14   0.31 Ideal     J     SI2  62.2  54.0   344 4.35 4.37 2.71
17   0.30 Ideal     I     SI2  62.0  54.0   348 4.31 4.34 2.68
40   0.33 Ideal     I     SI2  61.8  55.0   403 4.49 4.51 2.78
41   0.33 Ideal     I     SI2  61.2  56.0   403 4.49 4.50 2.75
42   0.33 Ideal     J     SI1  61.1  56.0   403 4.49 4.55 2.76
52   0.23 Ideal     G     VS1  61.9  54.0   404 3.93 3.95 2.44
53   0.32 Ideal     I     SI1  60.9  55.0   404 4.45 4.48 2.72
56   0.30 Ideal     I     SI2  61.0  59.0   405 4.30 4.33 2.63
61   0.35 Ideal     I     VS1  60.9  57.0   552 4.54 4.59 2.78
63   0.30 Ideal     D     SI1  62.5  57.0   552 4.29 4.32 2.69
64   0.30 Ideal     D     SI1  62.1  56.0   552 4.30 4.33 2.68
66   0.28 Ideal     G    VVS2  61.4  56.0   553 4.19 4.22 2.58
67   0.32 Ideal     I    VVS1  62.0  55.3   553 4.39 4.42 2.73
83   0.26 Ideal     E    VVS2  62.9  58.0   554 4.02 4.06 2.54
84   0.38 Ideal     I     SI2  61.6  56.0   554 4.65 4.67 2.87
91   0.70 Ideal     E     SI1  62.5  57.0  2757 5.70 5.72 3.57
93   0.70 Ideal     G     VS2  61.6  56.0  2757 5.70 5.67 3.50
103  0.74 Ideal     G     SI1  61.6  55.0  2760 5.80 5.85 3.59
105  0.80 Ideal     I     VS1  62.9  56.0  2760 5.94 5.87 3.72
106  0.75 Ideal     G     SI1  62.2  55.0  2760 5.87 5.80 3.63
108  0.74 Ideal     I    VVS2  62.3  55.0  2761 5.77 5.81 3.61
109  0.81 Ideal     F     SI2  58.8  57.0  2761 6.14 6.11 3.60
110  0.59 Ideal     E    VVS2  62.0  55.0  2761 5.38 5.43 3.35
111  0.80 Ideal     F     SI2  61.4  57.0  2761 5.96 6.00 3.67
112  0.74 Ideal     E     SI2  62.2  56.0  2761 5.80 5.84 3.62
115  0.73 Ideal     F     VS2  62.6  56.0  2762 5.77 5.74 3.60
116  0.73 Ideal     F     VS2  62.7  53.0  2762 5.80 5.75 3.62
118  0.71 Ideal     G     VS2  62.4  54.0  2762 5.72 5.76 3.58
119  0.70 Ideal     E     VS2  60.7  58.0  2762 5.73 5.76 3.49
120  0.80 Ideal     F     SI2  59.9  59.0  2762 6.01 6.07 3.62
121  0.71 Ideal     D     SI2  62.3  56.0  2762 5.73 5.69 3.56
122  0.74 Ideal     E     SI1  62.3  54.0  2762 5.80 5.83 3.62
131  0.77 Ideal     H     VS2  62.0  56.0  2763 5.89 5.86 3.64
133  0.71 Ideal     D     SI1  61.9  59.0  2764 5.69 5.72 3.53
139  0.76 Ideal     H     SI1  61.2  57.0  2765 5.88 5.91 3.61
140  0.64 Ideal     G    VVS1  61.9  56.0  2766 5.53 5.56 3.43
145  0.71 Ideal     D     SI2  61.6  55.0  2767 5.74 5.76 3.54
150  0.70 Ideal     E     SI1  60.9  57.0  2768 5.73 5.76 3.50
152  0.74 Ideal     I     SI1  61.3  56.0  2769 5.82 5.86 3.57
156  0.76 Ideal     D     SI2  62.4  57.0  2770 5.78 5.83 3.62
157  0.71 Ideal     F     SI1  60.7  56.0  2770 5.77 5.80 3.51
160  0.73 Ideal     D     SI2  59.9  57.0  2770 5.92 5.89 3.54
164  0.71 Ideal     G     VS2  61.9  57.0  2771 5.73 5.77 3.56
165  0.79 Ideal     F     SI2  61.9  55.0  2771 5.97 5.92 3.68
168  0.58 Ideal     G    VVS1  61.5  55.0  2772 5.39 5.44 3.33
169  0.58 Ideal     F    VVS1  61.7  56.0  2772 5.33 5.37 3.30
171  0.75 Ideal     D     SI2  61.3  56.0  2773 5.85 5.89 3.60
174  0.60 Ideal     E     VS1  61.7  55.0  2774 5.41 5.44 3.35
175  0.70 Ideal     E     SI1  62.7  55.0  2774 5.68 5.74 3.58
180  0.71 Ideal     E     VS2  62.2  57.0  2776 5.79 5.62 3.55
181  0.54 Ideal     E    VVS2  61.6  56.0  2776 5.25 5.27 3.24
182  0.54 Ideal     E    VVS2  61.5  57.0  2776 5.24 5.26 3.23
183  0.72 Ideal     G     SI1  61.8  56.0  2776 5.72 5.75 3.55
184  0.72 Ideal     G     SI1  60.7  56.0  2776 5.79 5.82 3.53
186  0.71 Ideal     G     SI1  60.5  56.0  2776 5.80 5.76 3.50
192  0.70 Ideal     E     VS2  62.1  55.0  2777 5.70 5.67 3.53
199  0.70 Ideal     E     SI1  61.4  57.0  2777 5.76 5.70 3.52
208  0.52 Ideal     F    VVS1  61.3  55.0  2778 5.19 5.22 3.19
210  0.74 Ideal     E     SI1  61.7  56.0  2779 5.84 5.80 3.59
213  0.71 Ideal     F     VS2  62.1  54.0  2780 5.68 5.72 3.54
214  0.74 Ideal     G     VS1  61.5  55.0  2780 5.81 5.86 3.59
215  0.70 Ideal     G     VS1  61.4  59.0  2780 5.64 5.73 3.49
217  0.77 Ideal     H     SI1  62.2  56.0  2781 5.83 5.88 3.64
218  0.78 Ideal     H     SI1  61.2  56.0  2781 5.92 5.99 3.64
221  0.76 Ideal     G     VS2  61.3  56.0  2782 5.90 5.94 3.63
225  0.72 Ideal     D     SI1  60.8  57.0  2782 5.76 5.75 3.50
230  0.52 Ideal     F      IF  62.2  55.0  2783 5.14 5.18 3.21
234  0.51 Ideal     F    VVS1  62.0  57.0  2787 5.11 5.15 3.18
235  0.64 Ideal     D     VS1  61.5  56.0  2787 5.54 5.55 3.41
238  0.76 Ideal     I    VVS2  61.8  56.0  2788 5.85 5.87 3.62
241  0.71 Ideal     F     SI1  62.5  55.0  2788 5.71 5.65 3.55
249  0.81 Ideal     G     SI2  61.6  56.0  2789 5.97 6.01 3.69
250  0.70 Ideal     E     SI1  61.6  56.0  2789 5.72 5.75 3.53
251  0.55 Ideal     G      IF  60.9  57.0  2789 5.28 5.30 3.22
257  0.64 Ideal     G      IF  61.3  56.0  2790 5.54 5.58 3.41
259  0.83 Ideal     F     SI2  62.3  55.0  2790 6.02 6.05 3.76
263  0.73 Ideal     E     SI1  62.2  56.0  2791 5.74 5.78 3.58
266  0.71 Ideal     E     SI1  61.3  55.0  2792 5.72 5.77 3.52
270  0.70 Ideal     F     VS1  62.2  56.0  2792 5.73 5.68 3.55
274  0.76 Ideal     I     VS2  61.3  56.0  2793 5.87 5.91 3.61
275  0.73 Ideal     H     VS2  62.7  55.0  2793 5.72 5.76 3.60
279  0.81 Ideal     F     SI2  62.6  55.0  2795 5.92 5.96 3.72
292  0.57 Ideal     F    VVS2  61.9  55.0  2797 5.34 5.35 3.31
293  0.51 Ideal     D    VVS1  61.7  56.0  2797 5.12 5.16 3.17
294  0.72 Ideal     G     VS2  61.9  58.0  2797 5.72 5.75 3.55
295  0.74 Ideal     H     VS1  61.8  58.0  2797 5.77 5.81 3.58
296  0.74 Ideal     H     VS1  61.6  56.0  2797 5.81 5.82 3.58
301  0.77 Ideal     I     VS1  61.5  59.0  2798 5.87 5.91 3.62
303  0.82 Ideal     F     SI2  62.4  54.0  2799 5.97 6.02 3.74
304  0.78 Ideal     D     SI1  61.9  57.0  2799 5.91 5.86 3.64
309  0.83 Ideal     G     SI1  62.3  57.0  2800 5.99 6.08 3.76
310  0.83 Ideal     G     SI1  61.8  57.0  2800 6.03 6.07 3.74
313  0.79 Ideal     I     VS1  61.8  59.0  2800 5.92 5.95 3.67
314  0.61 Ideal     G      IF  62.3  56.0  2800 5.43 5.45 3.39
316  0.96 Ideal     F      I1  60.7  55.0  2801 6.37 6.41 3.88
317  0.73 Ideal     F     VS2  62.5  55.0  2801 5.80 5.76 3.61
319  0.75 Ideal     H     SI1  60.4  57.0  2801 5.93 5.96 3.59
327  0.53 Ideal     F      IF  61.9  54.0  2802 5.22 5.25 3.24
 [ reached 'max' / getOption("max.print") -- omitted 21451 rows ]
> ss3 <- subset(diamonds, cut == "Ideal" & price > 2000)
> ss3
    carat   cut color clarity depth table price    x    y    z
91   0.70 Ideal     E     SI1  62.5    57  2757 5.70 5.72 3.57
93   0.70 Ideal     G     VS2  61.6    56  2757 5.70 5.67 3.50
103  0.74 Ideal     G     SI1  61.6    55  2760 5.80 5.85 3.59
105  0.80 Ideal     I     VS1  62.9    56  2760 5.94 5.87 3.72
106  0.75 Ideal     G     SI1  62.2    55  2760 5.87 5.80 3.63
108  0.74 Ideal     I    VVS2  62.3    55  2761 5.77 5.81 3.61
109  0.81 Ideal     F     SI2  58.8    57  2761 6.14 6.11 3.60
110  0.59 Ideal     E    VVS2  62.0    55  2761 5.38 5.43 3.35
111  0.80 Ideal     F     SI2  61.4    57  2761 5.96 6.00 3.67
112  0.74 Ideal     E     SI2  62.2    56  2761 5.80 5.84 3.62
115  0.73 Ideal     F     VS2  62.6    56  2762 5.77 5.74 3.60
116  0.73 Ideal     F     VS2  62.7    53  2762 5.80 5.75 3.62
118  0.71 Ideal     G     VS2  62.4    54  2762 5.72 5.76 3.58
119  0.70 Ideal     E     VS2  60.7    58  2762 5.73 5.76 3.49
120  0.80 Ideal     F     SI2  59.9    59  2762 6.01 6.07 3.62
121  0.71 Ideal     D     SI2  62.3    56  2762 5.73 5.69 3.56
122  0.74 Ideal     E     SI1  62.3    54  2762 5.80 5.83 3.62
131  0.77 Ideal     H     VS2  62.0    56  2763 5.89 5.86 3.64
133  0.71 Ideal     D     SI1  61.9    59  2764 5.69 5.72 3.53
139  0.76 Ideal     H     SI1  61.2    57  2765 5.88 5.91 3.61
140  0.64 Ideal     G    VVS1  61.9    56  2766 5.53 5.56 3.43
145  0.71 Ideal     D     SI2  61.6    55  2767 5.74 5.76 3.54
150  0.70 Ideal     E     SI1  60.9    57  2768 5.73 5.76 3.50
152  0.74 Ideal     I     SI1  61.3    56  2769 5.82 5.86 3.57
156  0.76 Ideal     D     SI2  62.4    57  2770 5.78 5.83 3.62
157  0.71 Ideal     F     SI1  60.7    56  2770 5.77 5.80 3.51
160  0.73 Ideal     D     SI2  59.9    57  2770 5.92 5.89 3.54
164  0.71 Ideal     G     VS2  61.9    57  2771 5.73 5.77 3.56
165  0.79 Ideal     F     SI2  61.9    55  2771 5.97 5.92 3.68
168  0.58 Ideal     G    VVS1  61.5    55  2772 5.39 5.44 3.33
169  0.58 Ideal     F    VVS1  61.7    56  2772 5.33 5.37 3.30
171  0.75 Ideal     D     SI2  61.3    56  2773 5.85 5.89 3.60
174  0.60 Ideal     E     VS1  61.7    55  2774 5.41 5.44 3.35
175  0.70 Ideal     E     SI1  62.7    55  2774 5.68 5.74 3.58
180  0.71 Ideal     E     VS2  62.2    57  2776 5.79 5.62 3.55
181  0.54 Ideal     E    VVS2  61.6    56  2776 5.25 5.27 3.24
182  0.54 Ideal     E    VVS2  61.5    57  2776 5.24 5.26 3.23
183  0.72 Ideal     G     SI1  61.8    56  2776 5.72 5.75 3.55
184  0.72 Ideal     G     SI1  60.7    56  2776 5.79 5.82 3.53
186  0.71 Ideal     G     SI1  60.5    56  2776 5.80 5.76 3.50
192  0.70 Ideal     E     VS2  62.1    55  2777 5.70 5.67 3.53
199  0.70 Ideal     E     SI1  61.4    57  2777 5.76 5.70 3.52
208  0.52 Ideal     F    VVS1  61.3    55  2778 5.19 5.22 3.19
210  0.74 Ideal     E     SI1  61.7    56  2779 5.84 5.80 3.59
213  0.71 Ideal     F     VS2  62.1    54  2780 5.68 5.72 3.54
214  0.74 Ideal     G     VS1  61.5    55  2780 5.81 5.86 3.59
215  0.70 Ideal     G     VS1  61.4    59  2780 5.64 5.73 3.49
217  0.77 Ideal     H     SI1  62.2    56  2781 5.83 5.88 3.64
218  0.78 Ideal     H     SI1  61.2    56  2781 5.92 5.99 3.64
221  0.76 Ideal     G     VS2  61.3    56  2782 5.90 5.94 3.63
225  0.72 Ideal     D     SI1  60.8    57  2782 5.76 5.75 3.50
230  0.52 Ideal     F      IF  62.2    55  2783 5.14 5.18 3.21
234  0.51 Ideal     F    VVS1  62.0    57  2787 5.11 5.15 3.18
235  0.64 Ideal     D     VS1  61.5    56  2787 5.54 5.55 3.41
238  0.76 Ideal     I    VVS2  61.8    56  2788 5.85 5.87 3.62
241  0.71 Ideal     F     SI1  62.5    55  2788 5.71 5.65 3.55
249  0.81 Ideal     G     SI2  61.6    56  2789 5.97 6.01 3.69
250  0.70 Ideal     E     SI1  61.6    56  2789 5.72 5.75 3.53
251  0.55 Ideal     G      IF  60.9    57  2789 5.28 5.30 3.22
257  0.64 Ideal     G      IF  61.3    56  2790 5.54 5.58 3.41
259  0.83 Ideal     F     SI2  62.3    55  2790 6.02 6.05 3.76
263  0.73 Ideal     E     SI1  62.2    56  2791 5.74 5.78 3.58
266  0.71 Ideal     E     SI1  61.3    55  2792 5.72 5.77 3.52
270  0.70 Ideal     F     VS1  62.2    56  2792 5.73 5.68 3.55
274  0.76 Ideal     I     VS2  61.3    56  2793 5.87 5.91 3.61
275  0.73 Ideal     H     VS2  62.7    55  2793 5.72 5.76 3.60
279  0.81 Ideal     F     SI2  62.6    55  2795 5.92 5.96 3.72
292  0.57 Ideal     F    VVS2  61.9    55  2797 5.34 5.35 3.31
293  0.51 Ideal     D    VVS1  61.7    56  2797 5.12 5.16 3.17
294  0.72 Ideal     G     VS2  61.9    58  2797 5.72 5.75 3.55
295  0.74 Ideal     H     VS1  61.8    58  2797 5.77 5.81 3.58
296  0.74 Ideal     H     VS1  61.6    56  2797 5.81 5.82 3.58
301  0.77 Ideal     I     VS1  61.5    59  2798 5.87 5.91 3.62
303  0.82 Ideal     F     SI2  62.4    54  2799 5.97 6.02 3.74
304  0.78 Ideal     D     SI1  61.9    57  2799 5.91 5.86 3.64
309  0.83 Ideal     G     SI1  62.3    57  2800 5.99 6.08 3.76
310  0.83 Ideal     G     SI1  61.8    57  2800 6.03 6.07 3.74
313  0.79 Ideal     I     VS1  61.8    59  2800 5.92 5.95 3.67
314  0.61 Ideal     G      IF  62.3    56  2800 5.43 5.45 3.39
316  0.96 Ideal     F      I1  60.7    55  2801 6.37 6.41 3.88
317  0.73 Ideal     F     VS2  62.5    55  2801 5.80 5.76 3.61
319  0.75 Ideal     H     SI1  60.4    57  2801 5.93 5.96 3.59
327  0.53 Ideal     F      IF  61.9    54  2802 5.22 5.25 3.24
332  0.71 Ideal     G     VS2  61.3    56  2803 5.75 5.71 3.51
333  0.73 Ideal     E     SI1  60.6    54  2803 5.84 5.89 3.55
342  0.91 Ideal     D     SI2  62.2    57  2803 6.21 6.15 3.85
347  0.72 Ideal     F     VS1  61.7    57  2804 5.74 5.77 3.55
349  0.82 Ideal     H     VS2  61.5    56  2804 6.01 6.08 3.72
350  0.70 Ideal     D     SI1  61.0    59  2804 5.68 5.70 3.47
351  0.72 Ideal     D     SI1  62.2    56  2804 5.74 5.77 3.58
352  0.72 Ideal     D     SI1  61.5    54  2804 5.77 5.80 3.56
356  0.73 Ideal     E     SI2  61.8    58  2805 5.77 5.81 3.58
359  0.72 Ideal     G     VS2  62.8    56  2805 5.74 5.70 3.59
364  0.70 Ideal     F     SI1  61.6    55  2806 5.72 5.74 3.53
372  0.58 Ideal     E    VVS2  60.9    56  2808 5.41 5.43 3.30
380  0.74 Ideal     D     SI2  61.7    55  2810 5.81 5.85 3.60
423  0.71 Ideal     D     SI1  62.4    57  2812 5.69 5.72 3.56
426  0.51 Ideal     F    VVS1  62.0    57  2812 5.15 5.11 3.18
431  0.76 Ideal     E     SI1  61.7    57  2814 5.88 5.85 3.62
436  0.70 Ideal     H     SI1  60.4    56  2815 5.75 5.81 3.49
 [ reached 'max' / getOption("max.print") -- omitted 9849 rows ]
> str(ss3)
'data.frame':	9949 obs. of  10 variables:
 $ carat  : num  0.7 0.7 0.74 0.8 0.75 0.74 0.81 0.59 0.8 0.74 ...
 $ cut    : chr  "Ideal" "Ideal" "Ideal" "Ideal" ...
 $ color  : chr  "E" "G" "G" "I" ...
 $ clarity: chr  "SI1" "VS2" "SI1" "VS1" ...
 $ depth  : num  62.5 61.6 61.6 62.9 62.2 62.3 58.8 62 61.4 62.2 ...
 $ table  : num  57 56 55 56 55 55 57 55 57 56 ...
 $ price  : int  2757 2757 2760 2760 2760 2761 2761 2761 2761 2761 ...
 $ x      : num  5.7 5.7 5.8 5.94 5.87 5.77 6.14 5.38 5.96 5.8 ...
 $ y      : num  5.72 5.67 5.85 5.87 5.8 5.81 6.11 5.43 6 5.84 ...
 $ z      : num  3.57 3.5 3.59 3.72 3.63 3.61 3.6 3.35 3.67 3.62 ...
