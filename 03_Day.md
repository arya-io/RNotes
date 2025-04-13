## Lab Exercises

### 1. Subset the dataset Orders in the folder datasets to create a dataset with only "Online" payment.

```r
setwd("C:/Datasets/")
orders = read.csv("Orders.csv")
names(orders)

ss_ord = subset(orders, Mode.of.Payment=="Online")
```

### Output:
```bash
> setwd("C:/Datasets/")
> orders = read.csv("Orders.csv")
> names(orders)
[1] "Order.ID"          "Order.Date"        "Place.of.Shipment" "Mode.of.Payment"  
> ss_ord = subset(orders, Mode.of.Payment=="Online")
> ss_ord
    Order.ID Order.Date Place.of.Shipment Mode.of.Payment
2  32 90 002  06-Jan-11             Nasik          Online
6  32 90 006  01-Mar-11          Buldhana          Online
7  32 90 007  04-Mar-11             Nasik          Online
8  32 90 008  15-Mar-11              Pune          Online
9  32 90 009  19-Mar-11            Mumbai          Online
10 32 90 010  29-Mar-11             Thane          Online
11 32 90 011  12-Apr-11         Ratnagiri          Online
12 32 90 012  14-Apr-11            Raigad          Online
18 32 90 018  14-Aug-11        Aurangabad          Online
22 32 90 022  28-Sep-11         Ratnagiri          Online
23 32 90 023  12-Oct-11            Raigad          Online
26 32 90 026  20-Nov-11             Dhule          Online
27 32 90 027  11-Dec-11              Pune          Online
28 32 90 028  14-Dec-11            Mumbai          Online
29 32 90 029  30-Dec-11        Aurangabad          Online
37 32 90 037  22-Apr-12               Goa          Online
38 32 90 038  14-May-12           Solapur          Online
39 32 90 039  15-May-12            Sangli          Online
40 32 90 040  19-Jun-12            Satara          Online
41 32 90 041  23-Jul-12        Aurangabad          Online
48 32 90 048  23-Nov-12             Nasik          Online
49 32 90 049  14-Dec-12        Ahmednagar          Online
50 32 90 050  19-Dec-12            Nanded          Online
51 32 90 051  23-Dec-12          Kolhapur          Online
59 32 90 059  14-Apr-13       Sindhudurga          Online
60 32 90 060  14-Apr-13               Goa          Online
61 32 90 061  24-Apr-13           Solapur          Online
62 32 90 062  13-May-13            Sangli          Online
68 32 90 068  02-Aug-13         Ratnagiri          Online
```

---

### 2. Consider the dataset mtcars. Output (write) the data in this data set into a csv file and name the csv file as mtcars.csv.
```r
data("mtcars")     
mtcars

write.csv(mtcars, "C:/Datasets/mtcars.csv")
```

### Output:
```bash
> data("mtcars")     
> mtcars
                     mpg cyl  disp  hp drat    wt  qsec vs am gear carb
Mazda RX4           21.0   6 160.0 110 3.90 2.620 16.46  0  1    4    4
Mazda RX4 Wag       21.0   6 160.0 110 3.90 2.875 17.02  0  1    4    4
Datsun 710          22.8   4 108.0  93 3.85 2.320 18.61  1  1    4    1
Hornet 4 Drive      21.4   6 258.0 110 3.08 3.215 19.44  1  0    3    1
Hornet Sportabout   18.7   8 360.0 175 3.15 3.440 17.02  0  0    3    2
Valiant             18.1   6 225.0 105 2.76 3.460 20.22  1  0    3    1
Duster 360          14.3   8 360.0 245 3.21 3.570 15.84  0  0    3    4
Merc 240D           24.4   4 146.7  62 3.69 3.190 20.00  1  0    4    2
Merc 230            22.8   4 140.8  95 3.92 3.150 22.90  1  0    4    2
Merc 280            19.2   6 167.6 123 3.92 3.440 18.30  1  0    4    4
Merc 280C           17.8   6 167.6 123 3.92 3.440 18.90  1  0    4    4
Merc 450SE          16.4   8 275.8 180 3.07 4.070 17.40  0  0    3    3
Merc 450SL          17.3   8 275.8 180 3.07 3.730 17.60  0  0    3    3
Merc 450SLC         15.2   8 275.8 180 3.07 3.780 18.00  0  0    3    3
Cadillac Fleetwood  10.4   8 472.0 205 2.93 5.250 17.98  0  0    3    4
Lincoln Continental 10.4   8 460.0 215 3.00 5.424 17.82  0  0    3    4
Chrysler Imperial   14.7   8 440.0 230 3.23 5.345 17.42  0  0    3    4
Fiat 128            32.4   4  78.7  66 4.08 2.200 19.47  1  1    4    1
Honda Civic         30.4   4  75.7  52 4.93 1.615 18.52  1  1    4    2
Toyota Corolla      33.9   4  71.1  65 4.22 1.835 19.90  1  1    4    1
Toyota Corona       21.5   4 120.1  97 3.70 2.465 20.01  1  0    3    1
Dodge Challenger    15.5   8 318.0 150 2.76 3.520 16.87  0  0    3    2
AMC Javelin         15.2   8 304.0 150 3.15 3.435 17.30  0  0    3    2
Camaro Z28          13.3   8 350.0 245 3.73 3.840 15.41  0  0    3    4
Pontiac Firebird    19.2   8 400.0 175 3.08 3.845 17.05  0  0    3    2
Fiat X1-9           27.3   4  79.0  66 4.08 1.935 18.90  1  1    4    1
Porsche 914-2       26.0   4 120.3  91 4.43 2.140 16.70  0  1    5    2
Lotus Europa        30.4   4  95.1 113 3.77 1.513 16.90  1  1    5    2
Ford Pantera L      15.8   8 351.0 264 4.22 3.170 14.50  0  1    5    4
Ferrari Dino        19.7   6 145.0 175 3.62 2.770 15.50  0  1    5    6
Maserati Bora       15.0   8 301.0 335 3.54 3.570 14.60  0  1    5    8
Volvo 142E          21.4   4 121.0 109 4.11 2.780 18.60  1  1    4    2
> write.csv(mtcars, "C:/Datasets/mtcars.csv")
```

---

### 3. Consider the dataset diamonds in the folder datasets. Subset the dataset with criteria as cut=Premium and color=J
```r
diamond <- read.csv("diamonds.csv")
diamond
names(diamond)
ss_diamond <- subset(diamond, cut == "Premium" & color == "J")
ss_diamond 
```

### Output:
```bash
> diamond <- read.csv("diamonds.csv")
> diamond
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
> names(diamond)
 [1] "carat"   "cut"     "color"   "clarity" "depth"   "table"   "price"   "x"       "y"      
[10] "z"      
> ss_diamond <- subset(diamond, cut == "Premium" & color == "J")
> ss_diamond 
     carat     cut color clarity depth table price    x    y    z
57    0.30 Premium     J     SI2  59.3    61   405 4.43 4.38 2.61
325   1.00 Premium     J     SI2  62.3    58  2801 6.45 6.34 3.98
367   0.93 Premium     J     SI2  61.9    57  2807 6.21 6.19 3.84
526   1.17 Premium     J      I1  60.2    61  2825 6.90 6.83 4.13
745   0.33 Premium     J     VS1  62.8    58   557 4.41 4.38 2.76
746   0.33 Premium     J     VS1  61.5    61   557 4.46 4.39 2.72
766   0.92 Premium     J     SI1  62.9    58  2858 6.22 6.18 3.90
814   0.91 Premium     J     SI1  59.5    62  2863 6.40 6.18 3.74
815   0.90 Premium     J     VS2  59.8    62  2863 6.24 6.21 3.72
861   0.90 Premium     J     SI1  62.8    59  2871 6.13 6.03 3.82
882   0.90 Premium     J     SI1  61.8    58  2873 6.16 6.13 3.80
886   0.90 Premium     J     SI1  60.9    61  2873 6.26 6.22 3.80
1000  1.12 Premium     J     SI2  60.6    59  2898 6.68 6.61 4.03
1039  0.91 Premium     J     SI1  62.8    59  2905 6.19 6.14 3.87
1361  0.90 Premium     J     VS1  62.1    62  2964 6.12 6.05 3.78
1511  1.24 Premium     J      I1  61.9    55  2994 6.92 6.85 4.26
1826  0.91 Premium     J     VS2  61.6    58  3058 6.28 6.23 3.85
1844  0.93 Premium     J     VS1  60.3    58  3062 6.37 6.31 3.82
1974  0.92 Premium     J     VS2  60.9    62  3091 6.31 6.26 3.83
2118  1.02 Premium     J     SI2  62.3    58  3119 6.42 6.37 3.98
2146  0.93 Premium     J     VS2  61.1    59  3125 6.34 6.32 3.87
2207  0.90 Premium     J     SI1  60.4    59  3141 6.27 6.24 3.78
2251  1.03 Premium     J     SI2  62.2    59  3149 6.42 6.40 3.99
2275  1.22 Premium     J     SI2  62.6    59  3156 6.79 4.24 3.76
2364  0.90 Premium     J     VS1  62.3    56  3175 6.23 6.19 3.87
2445  0.96 Premium     J     SI1  62.9    59  3187 6.30 6.22 3.94
2457  1.01 Premium     J     VS2  62.4    60  3190 6.45 6.35 3.99
2586  1.10 Premium     J     SI2  60.0    58  3216 6.77 6.66 4.03
2760  0.93 Premium     J     VS2  62.3    60  3250 6.30 6.23 3.90
2825  1.12 Premium     J     SI2  60.7    61  3266 6.71 6.64 4.05
2839  0.96 Premium     J     SI1  60.3    59  3269 6.40 6.36 3.85
2875  1.00 Premium     J     SI1  62.0    62  3276 6.27 6.22 3.87
2947  1.00 Premium     J     SI2  62.7    58  3293 6.32 6.28 3.95
2958  1.01 Premium     J     VS2  62.4    60  3296 6.45 6.35 3.99
3345  1.03 Premium     J     SI2  62.0    58  3378 6.47 6.52 4.03
3382  0.31 Premium     J     VS1  60.7    60   408 4.34 4.39 2.65
3387  0.31 Premium     J     VS1  61.8    59   408 4.31 4.33 2.67
3464  1.06 Premium     J     SI2  62.9    59  3391 6.43 6.39 4.03
3554  1.00 Premium     J     SI1  62.7    57  3416 6.40 6.33 3.99
3581  1.01 Premium     J     SI2  63.0    60  3421 6.38 6.31 4.00
3671  1.02 Premium     J     SI1  58.9    62  3444 6.51 6.43 3.81
3756  1.02 Premium     J     SI2  61.4    60  3455 6.50 6.44 3.97
3764  1.05 Premium     J     SI2  60.9    60  3457 6.59 6.51 3.99
3771  0.90 Premium     J    VVS2  62.5    61  3459 6.15 6.08 3.82
3919  1.02 Premium     J     SI1  61.2    57  3496 6.58 6.43 3.98
3931  1.01 Premium     J     SI2  61.7    58  3499 6.40 6.44 3.96
3932  1.01 Premium     J     SI2  61.8    60  3499 6.37 6.41 3.95
3987  1.02 Premium     J     VS2  61.6    58  3513 6.40 6.35 3.93
4028  1.11 Premium     J     SI1  59.5    58  3524 6.89 6.77 4.07
4039  1.00 Premium     J     SI1  61.9    62  3528 6.36 6.33 3.93
4101  1.01 Premium     J     VS2  59.8    61  3535 6.47 6.43 3.86
4199  1.01 Premium     J     SI2  62.5    62  3563 6.41 6.36 3.99
4201  1.01 Premium     J     SI2  61.7    58  3563 6.44 6.40 3.96
4202  1.01 Premium     J     SI2  61.8    60  3563 6.41 6.37 3.95
4309  1.05 Premium     J     VS2  59.4    62  3593 6.66 6.58 3.93
4332  1.02 Premium     J     SI2  62.6    60  3599 6.42 6.39 4.01
4356  1.04 Premium     J     SI2  62.0    59  3603 6.47 6.49 4.02
4442  0.90 Premium     J    VVS1  62.0    58  3617 6.19 6.11 3.81
4522  1.03 Premium     J     SI2  62.8    58  3634 6.48 6.41 4.05
4545  1.00 Premium     J     VS1  59.7    62  3640 6.52 6.46 3.87
4582  1.02 Premium     J     VS2  58.9    60  3651 6.57 6.53 3.86
4601  1.01 Premium     J     SI2  61.9    59  3658 6.38 6.34 3.94
4638  0.95 Premium     J    VVS2  62.6    59  3669 6.23 6.26 3.91
4643  1.04 Premium     J     SI2  62.0    59  3669 6.49 6.47 4.02
4677  1.06 Premium     J     SI2  61.3    60  3672 6.52 6.59 4.02
4751  1.00 Premium     J     VS2  62.0    62  3685 6.42 6.35 3.96
4752  1.00 Premium     J     VS2  60.7    61  3685 6.50 6.41 3.92
4783  1.21 Premium     J     VS2  59.0    60  3694 6.93 6.88 4.07
4794  1.10 Premium     J     VS2  61.2    57  3696 6.66 6.61 4.06
4803  1.31 Premium     J     SI2  59.7    59  3697 7.06 7.01 4.20
4862  1.00 Premium     J     SI1  60.8    58  3712 6.39 6.44 3.90
4900  1.01 Premium     J     VS2  61.0    61  3722 6.28 6.22 3.81
4923  1.10 Premium     J     SI2  59.6    59  3726 6.74 6.72 4.01
4955  1.01 Premium     J     SI2  61.2    59  3733 6.43 6.37 3.92
4991  1.06 Premium     J     SI2  61.3    60  3740 6.59 6.52 4.02
5036  1.03 Premium     J     SI1  61.1    61  3749 6.49 6.44 3.95
5079  1.25 Premium     J     VS2  59.8    58  3751 7.02 6.96 4.18
5207  1.00 Premium     J     SI1  62.8    59  3780 6.37 6.27 3.97
5213  1.00 Premium     J     SI1  60.8    58  3780 6.44 6.39 3.90
5221  1.20 Premium     J     SI2  61.7    57  3782 6.85 6.79 4.21
5249  1.01 Premium     J     VS1  63.0    55  3790 6.39 6.34 4.01
5251  1.00 Premium     J     VS2  60.3    58  3790 6.49 6.44 3.90
5258  1.14 Premium     J     SI1  62.4    59  3792 6.70 6.62 4.16
5376  0.34 Premium     J     VS1  61.7    58   574 4.47 4.41 2.74
5418  1.05 Premium     J     VS1  62.7    61  3822 6.58 6.49 4.09
5426  1.06 Premium     J     SI2  62.0    58  3823 6.53 6.45 4.04
5546  1.02 Premium     J     SI1  63.0    58  3856 6.44 6.39 4.04
5548  1.02 Premium     J     SI1  61.8    58  3856 6.50 6.44 4.00
5573  1.14 Premium     J     SI2  60.4    59  3861 6.80 6.74 4.09
5587  1.00 Premium     J    VVS2  59.6    61  3864 6.40 6.36 3.80
5626  1.00 Premium     J     VS2  60.7    58  3877 6.49 6.52 3.95
5764  1.01 Premium     J    VVS2  62.7    59  3897 6.46 6.39 4.03
5819  1.18 Premium     J     VS2  62.8    59  3913 6.78 6.69 4.23
5857  1.00 Premium     J     SI1  58.7    58  3920 6.55 6.51 3.83
5977  1.20 Premium     J     SI2  59.6    62  3951 6.95 6.90 4.13
5996  1.03 Premium     J     VS1  61.8    58  3957 6.51 6.41 3.99
6131  1.21 Premium     J     SI2  60.8    58  3984 6.93 6.88 4.19
6138  1.13 Premium     J     SI2  62.4    59  3987 6.68 6.62 4.15
6264  1.27 Premium     J     VS2  62.8    58  4011 6.96 6.92 4.36
6285  1.25 Premium     J     SI2  61.3    58  4018 6.98 6.95 4.27
 [ reached 'max' / getOption("max.print") -- omitted 708 rows ]
```

---

### 4. Consider the dataset diamonds in the folder datasets. Create a data frame object which stores just variable carat, color, depth and price.
```r
q4 <- diamond[, c(1, 3, 5, 7)]
q4
```

### Output:
```
> q4 <- diamond[, c(1, 3, 5, 7)]
> q4
    carat color depth price
1    0.23     E  61.5   326
2    0.21     E  59.8   326
3    0.23     E  56.9   327
4    0.29     I  62.4   334
5    0.31     J  63.3   335
6    0.24     J  62.8   336
7    0.24     I  62.3   336
8    0.26     H  61.9   337
9    0.22     E  65.1   337
10   0.23     H  59.4   338
11   0.30     J  64.0   339
12   0.23     J  62.8   340
13   0.22     F  60.4   342
14   0.31     J  62.2   344
15   0.20     E  60.2   345
16   0.32     E  60.9   345
17   0.30     I  62.0   348
18   0.30     J  63.4   351
19   0.30     J  63.8   351
20   0.30     J  62.7   351
21   0.30     I  63.3   351
22   0.23     E  63.8   352
23   0.23     H  61.0   353
24   0.31     J  59.4   353
25   0.31     J  58.1   353
26   0.23     G  60.4   354
27   0.24     I  62.5   355
28   0.30     J  62.2   357
29   0.23     D  60.5   357
30   0.23     F  60.9   357
31   0.23     F  60.0   402
32   0.23     F  59.8   402
33   0.23     E  60.7   402
34   0.23     E  59.5   402
35   0.23     D  61.9   402
36   0.23     F  58.2   402
37   0.23     E  64.1   402
38   0.31     H  64.0   402
39   0.26     D  60.8   403
40   0.33     I  61.8   403
41   0.33     I  61.2   403
42   0.33     J  61.1   403
43   0.26     D  65.2   403
44   0.26     D  58.4   403
45   0.32     H  63.1   403
46   0.29     F  62.4   403
47   0.32     H  61.8   403
48   0.32     H  63.8   403
49   0.25     E  63.3   404
50   0.29     H  60.7   404
51   0.24     F  60.9   404
52   0.23     G  61.9   404
53   0.32     I  60.9   404
54   0.22     E  61.6   404
55   0.22     D  59.3   404
56   0.30     I  61.0   405
57   0.30     J  59.3   405
58   0.30     I  62.6   405
59   0.30     I  63.0   405
60   0.30     I  63.2   405
61   0.35     I  60.9   552
62   0.30     D  62.6   552
63   0.30     D  62.5   552
64   0.30     D  62.1   552
65   0.42     I  61.5   552
66   0.28     G  61.4   553
67   0.32     I  62.0   553
68   0.31     G  63.3   553
69   0.31     G  61.8   553
70   0.24     E  60.7   553
71   0.24     D  61.5   553
72   0.30     H  63.1   554
73   0.30     H  62.9   554
74   0.30     H  62.5   554
75   0.30     H  63.7   554
76   0.26     F  59.2   554
77   0.26     E  59.9   554
78   0.26     D  62.4   554
79   0.26     D  62.8   554
80   0.26     E  62.6   554
81   0.26     E  63.4   554
82   0.26     D  62.1   554
83   0.26     E  62.9   554
84   0.38     I  61.6   554
85   0.26     E  57.9   554
86   0.24     G  62.3   554
87   0.24     H  61.2   554
88   0.24     H  60.8   554
89   0.24     H  60.7   554
90   0.32     I  62.9   554
91   0.70     E  62.5  2757
92   0.86     E  55.1  2757
93   0.70     G  61.6  2757
94   0.71     E  62.4  2759
95   0.78     G  63.8  2759
96   0.70     E  57.5  2759
97   0.70     F  59.4  2759
98   0.96     F  66.3  2759
99   0.73     E  61.6  2760
100  0.80     H  61.5  2760
101  0.75     D  63.2  2760
102  0.75     E  59.9  2760
103  0.74     G  61.6  2760
104  0.75     G  61.7  2760
105  0.80     I  62.9  2760
106  0.75     G  62.2  2760
107  0.80     G  63.0  2760
108  0.74     I  62.3  2761
109  0.81     F  58.8  2761
110  0.59     E  62.0  2761
111  0.80     F  61.4  2761
112  0.74     E  62.2  2761
113  0.90     I  63.0  2761
114  0.74     G  62.2  2762
115  0.73     F  62.6  2762
116  0.73     F  62.7  2762
117  0.80     F  61.7  2762
118  0.71     G  62.4  2762
119  0.70     E  60.7  2762
120  0.80     F  59.9  2762
121  0.71     D  62.3  2762
122  0.74     E  62.3  2762
123  0.70     F  61.7  2762
124  0.70     F  64.5  2762
125  0.70     F  65.3  2762
126  0.70     F  61.6  2762
127  0.91     H  61.4  2763
128  0.61     D  59.6  2763
129  0.91     H  64.4  2763
130  0.91     H  65.7  2763
131  0.77     H  62.0  2763
132  0.71     D  63.6  2764
133  0.71     D  61.9  2764
134  0.70     E  62.6  2765
135  0.77     H  61.3  2765
136  0.63     E  60.9  2765
137  0.71     F  60.1  2765
138  0.71     F  61.8  2765
139  0.76     H  61.2  2765
140  0.64     G  61.9  2766
141  0.71     G  60.9  2766
142  0.71     G  59.8  2766
143  0.70     D  61.8  2767
144  0.70     F  60.0  2767
145  0.71     D  61.6  2767
146  0.70     H  62.1  2767
147  0.71     G  63.3  2768
148  0.73     D  60.2  2768
149  0.70     D  61.1  2768
150  0.70     E  60.9  2768
151  0.71     D  61.7  2768
152  0.74     I  61.3  2769
153  0.71     D  62.5  2770
154  0.73     G  61.4  2770
155  0.76     F  62.9  2770
156  0.76     D  62.4  2770
157  0.71     F  60.7  2770
158  0.73     G  60.7  2770
159  0.73     G  61.5  2770
160  0.73     D  59.9  2770
161  0.73     G  59.2  2770
162  0.72     H  60.3  2771
163  0.73     F  61.7  2771
164  0.71     G  61.9  2771
165  0.79     F  61.9  2771
166  0.73     H  60.4  2772
167  0.80     F  61.0  2772
168  0.58     G  61.5  2772
169  0.58     F  61.7  2772
170  0.71     E  59.2  2772
171  0.75     D  61.3  2773
172  0.70     D  58.0  2773
173  1.17     J  60.2  2774
174  0.60     E  61.7  2774
175  0.70     E  62.7  2774
176  0.83     I  64.6  2774
177  0.74     F  61.3  2775
178  0.72     G  63.7  2776
179  0.71     E  62.7  2776
180  0.71     E  62.2  2776
181  0.54     E  61.6  2776
182  0.54     E  61.5  2776
183  0.72     G  61.8  2776
184  0.72     G  60.7  2776
185  0.72     G  59.7  2776
186  0.71     G  60.5  2776
187  0.70     D  62.7  2777
188  0.71     F  62.1  2777
189  0.71     F  62.8  2777
190  0.71     F  63.8  2777
191  0.71     F  57.8  2777
192  0.70     E  62.1  2777
193  0.70     E  61.1  2777
194  0.70     E  60.0  2777
195  0.70     E  61.2  2777
196  0.70     E  62.7  2777
197  0.70     E  61.0  2777
198  0.70     E  61.0  2777
199  0.70     E  61.4  2777
200  0.72     F  61.8  2777
201  0.70     E  59.9  2777
202  0.70     E  61.3  2777
203  0.70     E  60.5  2777
204  0.70     E  64.1  2777
205  0.98     H  67.9  2777
206  0.78     F  62.4  2777
207  0.70     E  63.2  2777
208  0.52     F  61.3  2778
209  0.73     H  60.8  2779
210  0.74     E  61.7  2779
211  0.70     F  63.6  2780
212  0.77     G  61.2  2780
213  0.71     F  62.1  2780
214  0.74     G  61.5  2780
215  0.70     G  61.4  2780
216  1.01     F  61.8  2781
217  0.77     H  62.2  2781
218  0.78     H  61.2  2781
219  0.72     H  60.6  2782
220  0.53     D  57.5  2782
221  0.76     G  61.3  2782
222  0.70     E  57.2  2782
223  0.70     E  62.9  2782
224  0.75     D  63.1  2782
225  0.72     D  60.8  2782
226  0.72     D  62.7  2782
227  0.70     D  62.8  2782
228  0.84     G  55.1  2782
229  0.75     F  61.4  2782
230  0.52     F  62.2  2783
231  0.72     F  63.0  2784
232  0.79     H  63.7  2784
233  0.72     F  63.6  2787
234  0.51     F  62.0  2787
235  0.64     D  61.5  2787
236  0.70     H  60.5  2788
237  0.83     I  61.1  2788
238  0.76     I  61.8  2788
239  0.71     D  63.3  2788
240  0.77     G  59.4  2788
241  0.71     F  62.5  2788
242  1.01     E  64.5  2788
243  1.01     H  62.7  2788
244  0.77     F  64.2  2789
245  0.76     E  63.7  2789
246  0.76     E  60.4  2789
247  0.76     E  61.8  2789
248  1.05     J  63.2  2789
249  0.81     G  61.6  2789
250  0.70     E  61.6  2789
 [ reached 'max' / getOption("max.print") -- omitted 53690 rows ]
```

### OR

```r
ss_diam3 = subset(diamond, select = c('carat', 'color', 'depth', 'price'))
ss_diam3
```

### Output as same above.

---

### 5. Consider the dataset mtcars. Choose the 2nd, 18th, 30th and 12th rows.
```r
q5 <- mtcars[c(2, 18, 30, 12), ]
q5
```

### Output:
```bash
> q5 <- mtcars[c(2, 18, 30, 12), ]
> q5
               mpg cyl  disp  hp drat    wt  qsec vs am gear carb
Mazda RX4 Wag 21.0   6 160.0 110 3.90 2.875 17.02  0  1    4    4
Fiat 128      32.4   4  78.7  66 4.08 2.200 19.47  1  1    4    1
Ferrari Dino  19.7   6 145.0 175 3.62 2.770 15.50  0  1    5    6
Merc 450SE    16.4   8 275.8 180 3.07 4.070 17.40  0  0    3    3
```

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
