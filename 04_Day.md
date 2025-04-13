ifelse():
• In a simple way, we can treat ifelse() as a functional
version of the if-else structure
Syntax : ifelse(condition, true-value, false-value)
• If the condition is TRUE then the function returns
true-value otherwise it returns false-value

> v <- c(23, 13, 9, 24, 09, 3, 14, 8, 18, 20)
> result <- ifelse(v > 10, "Pass", "Fail")
> result
 [1] "Pass" "Pass" "Fail"
 [4] "Pass" "Fail" "Fail"
 [7] "Pass" "Fail" "Pass"
[10] "Pass"

> # if (mtcars$mpg > 25){
> #   print("Good Mileage")
> # } else{
> #   print("OK Mileage")
> # }
> 
> # Above condition doesn't work
> 
> # Below syntax gives correct output
> 
> ifelse(mtcars$mpg > 25, "Good Mileage", "OK Mileage")
 [1] "OK Mileage"  
 [2] "OK Mileage"  
 [3] "OK Mileage"  
 [4] "OK Mileage"  
 [5] "OK Mileage"  
 [6] "OK Mileage"  
 [7] "OK Mileage"  
 [8] "OK Mileage"  
 [9] "OK Mileage"  
[10] "OK Mileage"  
[11] "OK Mileage"  
[12] "OK Mileage"  
[13] "OK Mileage"  
[14] "OK Mileage"  
[15] "OK Mileage"  
[16] "OK Mileage"  
[17] "OK Mileage"  
[18] "Good Mileage"
[19] "Good Mileage"
[20] "Good Mileage"
[21] "OK Mileage"  
[22] "OK Mileage"  
[23] "OK Mileage"  
[24] "OK Mileage"  
[25] "OK Mileage"  
[26] "Good Mileage"
[27] "Good Mileage"
[28] "Good Mileage"
[29] "OK Mileage"  
[30] "OK Mileage"  
[31] "OK Mileage"  
[32] "OK Mileage"

# Creating a new column which does not exist in the dataframe

> mtcars$mileage = ifelse(mtcars$mpg > 25, "Good Mileage", "OK Mileage")
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

Mean and Variance Functions:
• mean()
• sd()
• var()
• Each of the functions above have the syntax usage in the
following way: function-name(variable-name,na.rm)
– na.rm by default is FALSE. It should be set to TRUE if we want to
ignore the NA values while computing

> mean(mtcars$mpg, na.rm = T)
[1] 20.09062
> sd(mtcars$mpg, na.rm = T)
[1] 6.026948
> var(mtcars$mpg, na.rm = T)
[1] 36.3241
> sd(mtcars$mpg) # standard deviation
[1] 6.026948

> mean(airquality$Ozone, na.rm = T) # It will ignore the NA values
[1] 42.12931
> # useNA is argument of Table function

summary():
• For numerical variables, summary function outputs the
Minimum, Maximum, 1st Quartile, Median, 3rd Quartile and
Mean
20
• For categorical variables, summary function outputs
the frequency counts

summary()
• We have some few more functions in R like
predict(), plot() which behave according to the
class of the argument

> summary(mtcars$mpg)
   Min. 1st Qu.  Median 
  10.40   15.43   19.20 
   Mean 3rd Qu.    Max. 
  20.09   22.80   33.90 
> summary(iris$Species.Type)
Length  Class   Mode 
     0   NULL   NULL 
> 
> summary(mtcars)
      mpg             cyl             disp             hp             drat             wt             qsec             vs               am              gear            carb         mileage         
 Min.   :10.40   Min.   :4.000   Min.   : 71.1   Min.   : 52.0   Min.   :2.760   Min.   :1.513   Min.   :14.50   Min.   :0.0000   Min.   :0.0000   Min.   :3.000   Min.   :1.000   Length:32         
 1st Qu.:15.43   1st Qu.:4.000   1st Qu.:120.8   1st Qu.: 96.5   1st Qu.:3.080   1st Qu.:2.581   1st Qu.:16.89   1st Qu.:0.0000   1st Qu.:0.0000   1st Qu.:3.000   1st Qu.:2.000   Class :character  
 Median :19.20   Median :6.000   Median :196.3   Median :123.0   Median :3.695   Median :3.325   Median :17.71   Median :0.0000   Median :0.0000   Median :4.000   Median :2.000   Mode  :character  
 Mean   :20.09   Mean   :6.188   Mean   :230.7   Mean   :146.7   Mean   :3.597   Mean   :3.217   Mean   :17.85   Mean   :0.4375   Mean   :0.4062   Mean   :3.688   Mean   :2.812                     
 3rd Qu.:22.80   3rd Qu.:8.000   3rd Qu.:326.0   3rd Qu.:180.0   3rd Qu.:3.920   3rd Qu.:3.610   3rd Qu.:18.90   3rd Qu.:1.0000   3rd Qu.:1.0000   3rd Qu.:4.000   3rd Qu.:4.000                     
 Max.   :33.90   Max.   :8.000   Max.   :472.0   Max.   :335.0   Max.   :4.930   Max.   :5.424   Max.   :22.90   Max.   :1.0000   Max.   :1.0000   Max.   :5.000   Max.   :8.000

> summary(airquality$Ozone)
   Min. 1st Qu.  Median    Mean 3rd Qu.    Max.    NA's 
   1.00   18.00   31.50   42.13   63.25  168.00      37 
> # Gives summary of the data like min, quartile values, median, mean, max, NA's

> summary(airquality) # Gives summary for every column in the dataset
     Ozone           Solar.R           Wind             Temp           Month            Day      
 Min.   :  1.00   Min.   :  7.0   Min.   : 1.700   Min.   :56.00   Min.   :5.000   Min.   : 1.0  
 1st Qu.: 18.00   1st Qu.:115.8   1st Qu.: 7.400   1st Qu.:72.00   1st Qu.:6.000   1st Qu.: 8.0  
 Median : 31.50   Median :205.0   Median : 9.700   Median :79.00   Median :7.000   Median :16.0  
 Mean   : 42.13   Mean   :185.9   Mean   : 9.958   Mean   :77.88   Mean   :6.993   Mean   :15.8  
 3rd Qu.: 63.25   3rd Qu.:258.8   3rd Qu.:11.500   3rd Qu.:85.00   3rd Qu.:8.000   3rd Qu.:23.0  
 Max.   :168.00   Max.   :334.0   Max.   :20.700   Max.   :97.00   Max.   :9.000   Max.   :31.0  
 NA's   :37       NA's   :7 

> c2018 <- read.csv("C:/Datasets/cars2018.csv", stringsAsFactors = T)
> summary(c2018$Transmission) # counts frequency of categorical data
Automatic       CVT    Manual 
      760        85       299 

attach()
• The data is attached to the R search path with attach().
• Data is searched by R when evaluating a variable, so objects
in the data can be accessed by simply giving their names.
Syntax : attach(data)
22
Hence, instead of typing…
It can be simply typed as…

> table(mtcars$mpg.Type)
< table of extent 0 >
> mean(mtcars$mpg, na.rm = T)
[1] 20.09062
> attach(mtcars)
> mean(mpg)
[1] 20.09062

> attach(c2018) 
> 
> # After running this command, there is no need to mention dataframe name along with $
> 
> summary(Transmission)
Automatic       CVT    Manual 
      760        85       299 
> summary(MPG)
   Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
   11.0    19.0    23.0    23.2    26.0    58.0 
> 
> detach(c2018)
> 
> # This is the detach command, now we would need to mention dataframe name along with $
> 
> summary(MPG)
Error: object 'MPG' not found

Creating Functions
• Some tasks which may be repeated in different
situations can be coded as a function
• A function has inputs and outputs
• Functions play a very important role in interactive
graphics technologies like Tibco Spotfire and
Shiny
• We create user defined functions by the following
syntax:
Function-Name <- function(argument-list) {
statements
 }

Function Examples
> add <- function(a, b, c){
+   
+   a + b + c
+ }
> 
> add <- function(a, b, c){
+   
+   return(a + b + c)
+   
+ }
> 

descriptive <- function(input){
  
  df <- data.frame(Mean = mean(input, na.rm = T), SD = sd(input, na.rm = T))
  df
}

Calling the function:

> add(2, 4, 6)
[1] 12
> descriptive(mtcars$mpg)
      Mean       SD
1 20.09062 6.026948

> # Creating user defined functions
> 
> # Create a function to add two numbers
> 
> add <- function(a, b){
+   a+b
+ }
> 
> add(3, 4)
[1] 7
> 
> 
> 
> # Fahrenheit to Celsius
> 
> ftoC <- function(temp){
+   (temp - 32) * (5/9)
+ }
> 
> ftoC(100)
[1] 37.77778
> 
> 
> 
> #Celsius to Fahrenheit
> 
> ctoF <- function(temp){
+   (temp * (9/5)) + 32
+ }
> 
> ctoF(37.77778)
[1] 100
> 
> #_____________________________________________________________________________________
> 
> # To calculate cube of a number
> 
> cube <- function(num){
+   number <- num*num*num
+   return(number)
+ }
> 
> cube(5)
[1] 125
> 
> # To calculate Simple Interest
> 
> simple <- function(p,r,n){
+   si <- (p*r*n)/100
+   return(si)
+ }
> simple(10000,10,2)
[1] 2000
> 
> # To pass multiple values, use the following command:
> 
> principal <- c(10000, 20000, 30000, 40000, 50000)
> rate <- c(10, 8, 12, 15, 20)
> time <- c(2, 4, 5, 3, 7)
> 
> simple(principal, rate, time)
[1]  2000  6400 18000 18000 70000
> 
> # This works similar to and only in Numpy in Python

> install.packages("dplyr")
WARNING: Rtools is required to build R packages but is not currently installed. Please download and install the appropriate version of Rtools before proceeding:

https://cran.rstudio.com/bin/windows/Rtools/
Installing package into ‘C:/Users/dbda.STUDENTSDC/AppData/Local/R/win-library/4.4’
(as ‘lib’ is unspecified)
trying URL 'https://cran.rstudio.com/bin/windows/contrib/4.4/dplyr_1.1.4.zip'
Content type 'application/zip' length 1589499 bytes (1.5 MB)
downloaded 1.5 MB

package ‘dplyr’ successfully unpacked and MD5 sums checked

The downloaded binary packages are in
	C:\Users\dbda.STUDENTSDC\AppData\Local\Temp\RtmpYbqtPw\downloaded_packages
> library(dplyr)

Attaching package: ‘dplyr’

The following objects are masked from ‘package:stats’:

    filter, lag

The following objects are masked from ‘package:base’:

    intersect, setdiff, setequal, union

Warning message:
package ‘dplyr’ was built under R version 4.4.3 
> 
> class(mtcars)
[1] "data.frame"
> 
> tbl_cars = as_tibble(mtcars)
> class(tbl_cars)
[1] "tbl_df"     "tbl"        "data.frame"
> 
> # Returns three classes
> # "tbl_df"    <- extends  "tbl"    <- extends    "data.frame"
> 
> #_______________________________________________________________
> 
> ssl = arrange(mtcars,mpg)
> ssl
                     mpg cyl  disp  hp drat    wt  qsec vs am gear carb      mileage
Cadillac Fleetwood  10.4   8 472.0 205 2.93 5.250 17.98  0  0    3    4   OK Mileage
Lincoln Continental 10.4   8 460.0 215 3.00 5.424 17.82  0  0    3    4   OK Mileage
Camaro Z28          13.3   8 350.0 245 3.73 3.840 15.41  0  0    3    4   OK Mileage
Duster 360          14.3   8 360.0 245 3.21 3.570 15.84  0  0    3    4   OK Mileage
Chrysler Imperial   14.7   8 440.0 230 3.23 5.345 17.42  0  0    3    4   OK Mileage
Maserati Bora       15.0   8 301.0 335 3.54 3.570 14.60  0  1    5    8   OK Mileage
Merc 450SLC         15.2   8 275.8 180 3.07 3.780 18.00  0  0    3    3   OK Mileage
AMC Javelin         15.2   8 304.0 150 3.15 3.435 17.30  0  0    3    2   OK Mileage
Dodge Challenger    15.5   8 318.0 150 2.76 3.520 16.87  0  0    3    2   OK Mileage
Ford Pantera L      15.8   8 351.0 264 4.22 3.170 14.50  0  1    5    4   OK Mileage
Merc 450SE          16.4   8 275.8 180 3.07 4.070 17.40  0  0    3    3   OK Mileage
Merc 450SL          17.3   8 275.8 180 3.07 3.730 17.60  0  0    3    3   OK Mileage
Merc 280C           17.8   6 167.6 123 3.92 3.440 18.90  1  0    4    4   OK Mileage
Valiant             18.1   6 225.0 105 2.76 3.460 20.22  1  0    3    1   OK Mileage
Hornet Sportabout   18.7   8 360.0 175 3.15 3.440 17.02  0  0    3    2   OK Mileage
Merc 280            19.2   6 167.6 123 3.92 3.440 18.30  1  0    4    4   OK Mileage
Pontiac Firebird    19.2   8 400.0 175 3.08 3.845 17.05  0  0    3    2   OK Mileage
Ferrari Dino        19.7   6 145.0 175 3.62 2.770 15.50  0  1    5    6   OK Mileage
Mazda RX4           21.0   6 160.0 110 3.90 2.620 16.46  0  1    4    4   OK Mileage
Mazda RX4 Wag       21.0   6 160.0 110 3.90 2.875 17.02  0  1    4    4   OK Mileage
Hornet 4 Drive      21.4   6 258.0 110 3.08 3.215 19.44  1  0    3    1   OK Mileage
Volvo 142E          21.4   4 121.0 109 4.11 2.780 18.60  1  1    4    2   OK Mileage
Toyota Corona       21.5   4 120.1  97 3.70 2.465 20.01  1  0    3    1   OK Mileage
Datsun 710          22.8   4 108.0  93 3.85 2.320 18.61  1  1    4    1   OK Mileage
Merc 230            22.8   4 140.8  95 3.92 3.150 22.90  1  0    4    2   OK Mileage
Merc 240D           24.4   4 146.7  62 3.69 3.190 20.00  1  0    4    2   OK Mileage
Porsche 914-2       26.0   4 120.3  91 4.43 2.140 16.70  0  1    5    2 Good Mileage
Fiat X1-9           27.3   4  79.0  66 4.08 1.935 18.90  1  1    4    1 Good Mileage
Honda Civic         30.4   4  75.7  52 4.93 1.615 18.52  1  1    4    2 Good Mileage
Lotus Europa        30.4   4  95.1 113 3.77 1.513 16.90  1  1    5    2 Good Mileage
Fiat 128            32.4   4  78.7  66 4.08 2.200 19.47  1  1    4    1 Good Mileage
Toyota Corolla      33.9   4  71.1  65 4.22 1.835 19.90  1  1    4    1 Good Mileage
> 
> # Sorts data in ascending order, in this case 'mpg' column of 'mtcars'
> 
> #___________________________________________________________________
> 
> 
> ssl = arrange(mtcars,desc(mpg))
> ssl
                     mpg cyl  disp  hp drat    wt  qsec vs am gear carb      mileage
Toyota Corolla      33.9   4  71.1  65 4.22 1.835 19.90  1  1    4    1 Good Mileage
Fiat 128            32.4   4  78.7  66 4.08 2.200 19.47  1  1    4    1 Good Mileage
Honda Civic         30.4   4  75.7  52 4.93 1.615 18.52  1  1    4    2 Good Mileage
Lotus Europa        30.4   4  95.1 113 3.77 1.513 16.90  1  1    5    2 Good Mileage
Fiat X1-9           27.3   4  79.0  66 4.08 1.935 18.90  1  1    4    1 Good Mileage
Porsche 914-2       26.0   4 120.3  91 4.43 2.140 16.70  0  1    5    2 Good Mileage
Merc 240D           24.4   4 146.7  62 3.69 3.190 20.00  1  0    4    2   OK Mileage
Datsun 710          22.8   4 108.0  93 3.85 2.320 18.61  1  1    4    1   OK Mileage
Merc 230            22.8   4 140.8  95 3.92 3.150 22.90  1  0    4    2   OK Mileage
Toyota Corona       21.5   4 120.1  97 3.70 2.465 20.01  1  0    3    1   OK Mileage
Hornet 4 Drive      21.4   6 258.0 110 3.08 3.215 19.44  1  0    3    1   OK Mileage
Volvo 142E          21.4   4 121.0 109 4.11 2.780 18.60  1  1    4    2   OK Mileage
Mazda RX4           21.0   6 160.0 110 3.90 2.620 16.46  0  1    4    4   OK Mileage
Mazda RX4 Wag       21.0   6 160.0 110 3.90 2.875 17.02  0  1    4    4   OK Mileage
Ferrari Dino        19.7   6 145.0 175 3.62 2.770 15.50  0  1    5    6   OK Mileage
Merc 280            19.2   6 167.6 123 3.92 3.440 18.30  1  0    4    4   OK Mileage
Pontiac Firebird    19.2   8 400.0 175 3.08 3.845 17.05  0  0    3    2   OK Mileage
Hornet Sportabout   18.7   8 360.0 175 3.15 3.440 17.02  0  0    3    2   OK Mileage
Valiant             18.1   6 225.0 105 2.76 3.460 20.22  1  0    3    1   OK Mileage
Merc 280C           17.8   6 167.6 123 3.92 3.440 18.90  1  0    4    4   OK Mileage
Merc 450SL          17.3   8 275.8 180 3.07 3.730 17.60  0  0    3    3   OK Mileage
Merc 450SE          16.4   8 275.8 180 3.07 4.070 17.40  0  0    3    3   OK Mileage
Ford Pantera L      15.8   8 351.0 264 4.22 3.170 14.50  0  1    5    4   OK Mileage
Dodge Challenger    15.5   8 318.0 150 2.76 3.520 16.87  0  0    3    2   OK Mileage
Merc 450SLC         15.2   8 275.8 180 3.07 3.780 18.00  0  0    3    3   OK Mileage
AMC Javelin         15.2   8 304.0 150 3.15 3.435 17.30  0  0    3    2   OK Mileage
Maserati Bora       15.0   8 301.0 335 3.54 3.570 14.60  0  1    5    8   OK Mileage
Chrysler Imperial   14.7   8 440.0 230 3.23 5.345 17.42  0  0    3    4   OK Mileage
Duster 360          14.3   8 360.0 245 3.21 3.570 15.84  0  0    3    4   OK Mileage
Camaro Z28          13.3   8 350.0 245 3.73 3.840 15.41  0  0    3    4   OK Mileage
Cadillac Fleetwood  10.4   8 472.0 205 2.93 5.250 17.98  0  0    3    4   OK Mileage
Lincoln Continental 10.4   8 460.0 215 3.00 5.424 17.82  0  0    3    4   OK Mileage
> 
> # Sorts data in descending order
> 
> #______________________________________________________________________
> 
> ssl = arrange(mtcars,desc(mpg), cyl)
> ssl
                     mpg cyl  disp  hp drat    wt  qsec vs am gear carb      mileage
Toyota Corolla      33.9   4  71.1  65 4.22 1.835 19.90  1  1    4    1 Good Mileage
Fiat 128            32.4   4  78.7  66 4.08 2.200 19.47  1  1    4    1 Good Mileage
Honda Civic         30.4   4  75.7  52 4.93 1.615 18.52  1  1    4    2 Good Mileage
Lotus Europa        30.4   4  95.1 113 3.77 1.513 16.90  1  1    5    2 Good Mileage
Fiat X1-9           27.3   4  79.0  66 4.08 1.935 18.90  1  1    4    1 Good Mileage
Porsche 914-2       26.0   4 120.3  91 4.43 2.140 16.70  0  1    5    2 Good Mileage
Merc 240D           24.4   4 146.7  62 3.69 3.190 20.00  1  0    4    2   OK Mileage
Datsun 710          22.8   4 108.0  93 3.85 2.320 18.61  1  1    4    1   OK Mileage
Merc 230            22.8   4 140.8  95 3.92 3.150 22.90  1  0    4    2   OK Mileage
Toyota Corona       21.5   4 120.1  97 3.70 2.465 20.01  1  0    3    1   OK Mileage
Volvo 142E          21.4   4 121.0 109 4.11 2.780 18.60  1  1    4    2   OK Mileage
Hornet 4 Drive      21.4   6 258.0 110 3.08 3.215 19.44  1  0    3    1   OK Mileage
Mazda RX4           21.0   6 160.0 110 3.90 2.620 16.46  0  1    4    4   OK Mileage
Mazda RX4 Wag       21.0   6 160.0 110 3.90 2.875 17.02  0  1    4    4   OK Mileage
Ferrari Dino        19.7   6 145.0 175 3.62 2.770 15.50  0  1    5    6   OK Mileage
Merc 280            19.2   6 167.6 123 3.92 3.440 18.30  1  0    4    4   OK Mileage
Pontiac Firebird    19.2   8 400.0 175 3.08 3.845 17.05  0  0    3    2   OK Mileage
Hornet Sportabout   18.7   8 360.0 175 3.15 3.440 17.02  0  0    3    2   OK Mileage
Valiant             18.1   6 225.0 105 2.76 3.460 20.22  1  0    3    1   OK Mileage
Merc 280C           17.8   6 167.6 123 3.92 3.440 18.90  1  0    4    4   OK Mileage
Merc 450SL          17.3   8 275.8 180 3.07 3.730 17.60  0  0    3    3   OK Mileage
Merc 450SE          16.4   8 275.8 180 3.07 4.070 17.40  0  0    3    3   OK Mileage
Ford Pantera L      15.8   8 351.0 264 4.22 3.170 14.50  0  1    5    4   OK Mileage
Dodge Challenger    15.5   8 318.0 150 2.76 3.520 16.87  0  0    3    2   OK Mileage
Merc 450SLC         15.2   8 275.8 180 3.07 3.780 18.00  0  0    3    3   OK Mileage
AMC Javelin         15.2   8 304.0 150 3.15 3.435 17.30  0  0    3    2   OK Mileage
Maserati Bora       15.0   8 301.0 335 3.54 3.570 14.60  0  1    5    8   OK Mileage
Chrysler Imperial   14.7   8 440.0 230 3.23 5.345 17.42  0  0    3    4   OK Mileage
Duster 360          14.3   8 360.0 245 3.21 3.570 15.84  0  0    3    4   OK Mileage
Camaro Z28          13.3   8 350.0 245 3.73 3.840 15.41  0  0    3    4   OK Mileage
Cadillac Fleetwood  10.4   8 472.0 205 2.93 5.250 17.98  0  0    3    4   OK Mileage
Lincoln Continental 10.4   8 460.0 215 3.00 5.424 17.82  0  0    3    4   OK Mileage
> 
> # Works similar to ORDER BY of RDBMS SQL
> 
> #_____________________________________________________________________
> 
> select(mtcars, mpg, wt, am)
                     mpg    wt am
Mazda RX4           21.0 2.620  1
Mazda RX4 Wag       21.0 2.875  1
Datsun 710          22.8 2.320  1
Hornet 4 Drive      21.4 3.215  0
Hornet Sportabout   18.7 3.440  0
Valiant             18.1 3.460  0
Duster 360          14.3 3.570  0
Merc 240D           24.4 3.190  0
Merc 230            22.8 3.150  0
Merc 280            19.2 3.440  0
Merc 280C           17.8 3.440  0
Merc 450SE          16.4 4.070  0
Merc 450SL          17.3 3.730  0
Merc 450SLC         15.2 3.780  0
Cadillac Fleetwood  10.4 5.250  0
Lincoln Continental 10.4 5.424  0
Chrysler Imperial   14.7 5.345  0
Fiat 128            32.4 2.200  1
Honda Civic         30.4 1.615  1
Toyota Corolla      33.9 1.835  1
Toyota Corona       21.5 2.465  0
Dodge Challenger    15.5 3.520  0
AMC Javelin         15.2 3.435  0
Camaro Z28          13.3 3.840  0
Pontiac Firebird    19.2 3.845  0
Fiat X1-9           27.3 1.935  1
Porsche 914-2       26.0 2.140  1
Lotus Europa        30.4 1.513  1
Ford Pantera L      15.8 3.170  1
Ferrari Dino        19.7 2.770  1
Maserati Bora       15.0 3.570  1
Volvo 142E          21.4 2.780  1
> # displays columns mentioned in the parentheses
> 
> select(mtcars,, mpg:wt)
                     mpg cyl  disp  hp drat    wt
Mazda RX4           21.0   6 160.0 110 3.90 2.620
Mazda RX4 Wag       21.0   6 160.0 110 3.90 2.875
Datsun 710          22.8   4 108.0  93 3.85 2.320
Hornet 4 Drive      21.4   6 258.0 110 3.08 3.215
Hornet Sportabout   18.7   8 360.0 175 3.15 3.440
Valiant             18.1   6 225.0 105 2.76 3.460
Duster 360          14.3   8 360.0 245 3.21 3.570
Merc 240D           24.4   4 146.7  62 3.69 3.190
Merc 230            22.8   4 140.8  95 3.92 3.150
Merc 280            19.2   6 167.6 123 3.92 3.440
Merc 280C           17.8   6 167.6 123 3.92 3.440
Merc 450SE          16.4   8 275.8 180 3.07 4.070
Merc 450SL          17.3   8 275.8 180 3.07 3.730
Merc 450SLC         15.2   8 275.8 180 3.07 3.780
Cadillac Fleetwood  10.4   8 472.0 205 2.93 5.250
Lincoln Continental 10.4   8 460.0 215 3.00 5.424
Chrysler Imperial   14.7   8 440.0 230 3.23 5.345
Fiat 128            32.4   4  78.7  66 4.08 2.200
Honda Civic         30.4   4  75.7  52 4.93 1.615
Toyota Corolla      33.9   4  71.1  65 4.22 1.835
Toyota Corona       21.5   4 120.1  97 3.70 2.465
Dodge Challenger    15.5   8 318.0 150 2.76 3.520
AMC Javelin         15.2   8 304.0 150 3.15 3.435
Camaro Z28          13.3   8 350.0 245 3.73 3.840
Pontiac Firebird    19.2   8 400.0 175 3.08 3.845
Fiat X1-9           27.3   4  79.0  66 4.08 1.935
Porsche 914-2       26.0   4 120.3  91 4.43 2.140
Lotus Europa        30.4   4  95.1 113 3.77 1.513
Ford Pantera L      15.8   8 351.0 264 4.22 3.170
Ferrari Dino        19.7   6 145.0 175 3.62 2.770
Maserati Bora       15.0   8 301.0 335 3.54 3.570
Volvo 142E          21.4   4 121.0 109 4.11 2.780
> # displays columns in the range of columns
> 
> select(mtcars, starts_with("d"))
                     disp drat
Mazda RX4           160.0 3.90
Mazda RX4 Wag       160.0 3.90
Datsun 710          108.0 3.85
Hornet 4 Drive      258.0 3.08
Hornet Sportabout   360.0 3.15
Valiant             225.0 2.76
Duster 360          360.0 3.21
Merc 240D           146.7 3.69
Merc 230            140.8 3.92
Merc 280            167.6 3.92
Merc 280C           167.6 3.92
Merc 450SE          275.8 3.07
Merc 450SL          275.8 3.07
Merc 450SLC         275.8 3.07
Cadillac Fleetwood  472.0 2.93
Lincoln Continental 460.0 3.00
Chrysler Imperial   440.0 3.23
Fiat 128             78.7 4.08
Honda Civic          75.7 4.93
Toyota Corolla       71.1 4.22
Toyota Corona       120.1 3.70
Dodge Challenger    318.0 2.76
AMC Javelin         304.0 3.15
Camaro Z28          350.0 3.73
Pontiac Firebird    400.0 3.08
Fiat X1-9            79.0 4.08
Porsche 914-2       120.3 4.43
Lotus Europa         95.1 3.77
Ford Pantera L      351.0 4.22
Ferrari Dino        145.0 3.62
Maserati Bora       301.0 3.54
Volvo 142E          121.0 4.11
> # displays columns that starts with 'd' in their column name
> 
> select(mtcars, contains("t"))
                    drat    wt
Mazda RX4           3.90 2.620
Mazda RX4 Wag       3.90 2.875
Datsun 710          3.85 2.320
Hornet 4 Drive      3.08 3.215
Hornet Sportabout   3.15 3.440
Valiant             2.76 3.460
Duster 360          3.21 3.570
Merc 240D           3.69 3.190
Merc 230            3.92 3.150
Merc 280            3.92 3.440
Merc 280C           3.92 3.440
Merc 450SE          3.07 4.070
Merc 450SL          3.07 3.730
Merc 450SLC         3.07 3.780
Cadillac Fleetwood  2.93 5.250
Lincoln Continental 3.00 5.424
Chrysler Imperial   3.23 5.345
Fiat 128            4.08 2.200
Honda Civic         4.93 1.615
Toyota Corolla      4.22 1.835
Toyota Corona       3.70 2.465
Dodge Challenger    2.76 3.520
AMC Javelin         3.15 3.435
Camaro Z28          3.73 3.840
Pontiac Firebird    3.08 3.845
Fiat X1-9           4.08 1.935
Porsche 914-2       4.43 2.140
Lotus Europa        3.77 1.513
Ford Pantera L      4.22 3.170
Ferrari Dino        3.62 2.770
Maserati Bora       3.54 3.570
Volvo 142E          4.11 2.780
> # displays columns that contains 't' in their column name
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
