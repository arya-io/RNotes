# 1. Males who have never smoked

> library(dplyr)
> setwd("C:/Datasets/")
> survey <- read.csv("survey.csv", stringsAsFactors = T)
> MaleNonSmokers <- survey |>
+   select(Sex, Wr.Hnd, NW.Hnd, W.Hnd, Fold, Pulse, Clap, Exer, Smoke, Height, M.I, Age) |>
+   filter(Smoke == "Never")
> MaleNonSmokers
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

# 2. Students whose pulse rate is greater than 80

> PulseGT80 <- filter(select(survey, Sex, Exer, Smoke, Pulse), Pulse > 80)
> PulseGT80
      Sex Exer Smoke Pulse
1  Female Some Never    92
2    Male None Regul   104
3    Male None Occas    87
4    Male Freq Never    83
5    Male Some Never    90
6  Female Freq Never    89
7    Male Some Never    90
8    Male Some Never    90
9    Male Freq Regul    84
10   Male None Never    96
11 Female Some Never    88
12 Female Freq Never    98
13   Male Freq Never    90
14 Female Some Never    92
15 Female Freq Never    85
16   Male Some Heavy    83
17 Female Some Never   100
18   Male Freq Heavy   100
19 Female Freq Never    92
20 Female Some Never    90
21   Male Freq Never    86
22 Female Some Never    86
23   Male Some Never    85
24   Male Some Regul    90
25 Female Some Never    84
26   Male Some Never    96
27 Female Freq Never    92
28 Female Some Regul    92
29   Male Freq Regul    84
30 Female Some Never    81
31 Female Freq Never   104
32 Female Freq Never    84
33 Female Freq Occas    87
34   Male Some Never    90
35   Male Some Never    92
36 Female None Never    86
37 Female Freq Occas    83
38   Male Some Never    84
39   Male None Never    97
40 Female Some Never    83
41   Male Freq Never    88
42 Female Some Never    88
43 Female Some Never    96
44 Female Some Never    85
45 Female Some Never    88
46   Male Some Never    90
47 Female Freq Never    85

# 3. Create a variable of ratio of variables Wr.Hnd / NW.Hnd as Ratio_Hnd

> RtHand <- survey %>%
+   mutate(Ratio_Hnd = Wr.Hnd / NW.Hnd) %>%
+   select(Ratio_Hnd, Clap, Age)
> RtHand
    Ratio_Hnd    Clap    Age
1   1.0277778    Left 18.250
2   0.9512195    Left 17.583
3   1.3533835 Neither 16.917
4   0.9947090 Neither 20.333
5   1.0000000   Right 23.667
6   1.0169492   Right 21.000
7   1.0000000   Right 18.833
8   0.9826590   Right 35.833
9   1.0256410   Right 19.000
10  1.0000000   Right 22.333
11  0.9883721   Right 28.500
12  1.0000000    Left 18.250
13  1.0000000   Right 18.750
14  0.9653465 Neither 17.500
15  1.0322581   Right 17.167
16  1.0294118   Right 17.167
17  1.0000000 Neither 19.333
18  1.0104167   Right 18.333
19  1.0000000    Left 19.750
20  1.0047847   Right 17.917
21  0.9772727    Left 17.917
22  0.9710145   Right 18.167
23  1.0277778   Right 17.833
24  1.0141509   Right 18.250
25  0.9714286    Left 19.167
26  1.0000000 Neither 17.583
27  1.0144928   Right 17.500
28  0.9719626 Neither 18.083
29  1.0000000 Neither 21.917
30  1.0000000   Right 19.250
31  1.0277778   Right 41.583
32  1.0329670   Right 17.500
33  0.9771429   Right 39.750
34  1.0050000   Right 17.167
35  0.9473684 Neither 17.750
36  1.0571429   Right 18.000
37  0.9696970   Right 19.000
38  1.0486486 Neither 17.917
39  1.0000000   Right 35.500
40  1.0000000 Neither 19.917
41  1.0937500   Right 17.500
42  0.9888889   Right 17.083
43         NA    <NA> 28.583
44  0.9950495   Right 17.500
45  1.0000000    Left 17.417
46  0.9714286 Neither 18.500
47  1.0220264    Left 18.917
48  0.9782609   Right 19.417
49  1.0227273   Right 18.417
50  1.0055866    Left 30.750
51  1.0232558    Left 18.500
52  1.0250000   Right 17.500
53  0.9444444    Left 18.333
54  1.0512821   Right 17.417
55  1.0000000   Right 20.000
56  1.0000000 Neither 18.333
57  1.0064935 Neither 17.167
58  0.9898477   Right 17.417
59  1.0263158   Right 17.667
60  0.9809524    Left 18.417
61  0.9827586 Neither 20.333
62  1.0164835 Neither 17.333
63  0.9949239   Right 17.500
64  1.0388889    Left 19.833
65  0.9611111 Neither 18.583
66  0.9848485   Right 18.000
67  0.9947644 Neither 30.667
68  1.0277778   Right 16.917
69  1.0000000   Right 19.917
70  1.0769231    Left 18.333
71  1.0285714    Left 17.583
72  0.9948718   Right 17.833
73  1.0240964   Right 17.667
74  0.9705882    Left 17.417
75  0.9873418    Left 17.750
76  1.0000000   Right 20.667
77  0.9659091   Right 23.583
78  1.0333333 Neither 17.167
79  0.9891892 Neither 17.083
80  0.9756098   Right 18.750
81  1.0000000    Left 16.750
82  1.0158730   Right 20.167
83  1.0000000    Left 17.667
84  0.9770115 Neither 17.167
85  0.9787234   Right 17.167
86  1.0411765   Right 17.250
87  1.0111111   Right 18.000
88  0.9891892    Left 18.750
89  1.0000000   Right 21.583
90  1.0169492    Left 17.583
91  1.0250000    Left 19.667
92  0.9722222   Right 18.000
93  1.0400000   Right 19.667
94  0.9837838   Right 17.083
95  1.0240385   Right 22.833
96  1.0106383   Right 17.083
97  1.0256410 Neither 19.417
98  1.0000000   Right 23.250
99  1.0051546   Right 18.083
100 0.9897959 Neither 19.083
101 0.9864865   Right 18.917
102 0.9895288 Neither 17.750
103 1.0000000   Right 20.833
104 1.0115607   Right 20.167
105 1.0294118    Left 17.667
106 1.0540541   Right 18.250
107 0.9878049   Right 17.000
108 1.0691824   Right 18.500
109 1.0000000 Neither 18.583
110 0.9800995    Left 17.750
111 1.0000000    Left 24.167
112 0.9795918   Right 18.167
113 1.0299401   Right 21.167
114 0.9761905   Right 17.917
115 1.0322581    Left 17.417
116 1.0562500   Right 20.500
117 1.0179641   Right 22.917
118 1.0454545    Left 18.917
119 1.0277778 Neither 18.917
120 1.0294118   Right 20.083
121 1.0000000 Neither 17.500
122 1.0000000   Right 18.250
123 1.0277778   Right 17.500
124 0.9900000   Right 17.417
125 1.0220994    Left 21.000
126 0.9948454   Right 19.833
127 1.0000000   Right 17.667
128 0.9842932 Neither 18.083
129 1.0294118   Right 18.000
130 0.9939394   Right 18.333
131 1.0232558   Right 20.000
132 0.9743590   Right 18.750
133 0.9450000   Right 19.083
134 0.9390244    Left 18.500
135 1.0056180    Left 18.417
136 1.0266667   Right 19.167
137 1.0421053 Neither 21.500
138 1.0000000   Right 19.333
139 1.0256410   Right 21.417
140 1.0540541   Right 18.667
141 0.9677419   Right 17.500
142 0.9631579   Right 21.083
143 1.0106383   Right 17.250
144 1.0190476 Neither 19.000
145 1.0256410 Neither 19.167
146 1.0000000 Neither 19.000
147 0.9955752   Right 23.000
148 0.9653465 Neither 32.667
149 1.0000000 Neither 20.000
150 0.9729730 Neither 20.167
151 0.9775785    Left 25.500
152 1.0400000   Right 18.167
153 1.0061728   Right 23.500
154 0.9953704   Right 70.417
155 0.9895288   Right 43.833
156 1.0250000   Right 23.583
157 0.9032258 Neither 21.083
158 0.9843750   Right 44.250
159 0.9756098   Right 19.667
160 0.9736842   Right 17.917
161 1.0233918    Left 18.417
162 0.9945055   Right 21.167
163 0.9950739 Neither 17.500
164 0.9763314 Neither 29.083
165 1.0000000   Right 19.917
166 1.0232558    Left 18.500
167 1.0156250   Right 18.167
168 1.1000000   Right 32.750
169 1.0270270 Neither 17.417
170 1.0270270   Right 17.333
171 0.9705882   Right 73.000
172 1.0512821   Right 18.667
173 1.0000000   Right 18.500
174 1.0285714 Neither 18.667
175 0.9722222 Neither 17.750
176 1.0270270    Left 17.250
177 1.0000000   Right 36.583
178 0.9823529    Left 23.083
179 1.0000000    Left 19.250
180 1.0303030   Right 17.167
181 0.9743590   Right 23.417
182 1.0370370 Neither 17.083
183 0.9943182   Right 17.250
184 0.9736842    Left 23.833
185 0.9729730   Right 18.750
186 0.9903382   Right 21.167
187 1.0000000   Right 24.667
188 1.0000000   Right 18.500
189 0.9729730   Right 20.333
190 1.0277778 Neither 20.083
191 1.0256410   Right 18.917
192 0.9777778   Right 27.333
193 0.9728261    Left 18.917
194 0.9887640    Left 17.250
195 1.1059603   Right 18.167
196 0.9659091   Right 26.500
197 1.1538462 Neither 17.000
198 1.0322581   Right 17.167
199 1.0052632   Right 19.167
200 1.0606061 Neither 17.500
201 1.0253165   Right 19.250
202 1.0000000 Neither 21.333
203 1.0561798   Right 18.583
204 1.0277778   Right 20.167
205 0.9714286   Right 18.667
206 1.0294118 Neither 17.083
207 0.9943182   Right 17.417
208 0.9943182   Right 18.583
209 1.0294118 Neither 19.500
210 1.0048309 Neither 18.500
211 1.0000000   Right 17.167
212 1.0000000 Neither 17.250
213 0.9729730   Right 17.500
214 0.9714286   Right 20.417
215 1.0112360   Right 17.083
216 0.9750000   Right 21.250
217 1.0061728   Right 19.250
218 0.9191919   Right 19.333
219 0.9826590 Neither 19.167
220 1.0000000   Right 18.917
221 0.9957082   Right 20.917
222 0.9636364   Right 17.333
223 0.9510870   Right 18.167
224 0.9943182   Right 20.750
225 1.0232558   Right 19.917
226 0.9831461   Right 18.667
227 1.0273224   Right 18.417
228 1.0101010   Right 17.417
229 0.9893617   Right 20.333
230 0.9489796   Right 19.333
231 1.0162162   Right 18.167
232 1.1250000   Right 20.750
233 1.0000000   Right 17.667
234 1.0277778   Right 16.917
235 1.0606061   Right 18.583
236 0.9767442   Right 17.167
237 1.0173410   Right 17.750

# 4. Calculate the mean and standard deviation for the variable Age

> DescStats <- survey %>%
+   summarise(avg_age = mean(Age, na.rm = T),
+             sd_age = sd(Age, na.rm = T))
> DescStats
   avg_age   sd_age
1 20.37451 6.474335

# 5. Calculate the mean and standard deviation for the variable Age grouped by Sex

> DescGrp <- survey %>%
+   group_by(Sex) %>%
+   summarise(avg_age = mean(Age, na.rm = T),
+             sd_age = sd(Age, na.rm = T))
> DescGrp
# A tibble: 3 × 3

# Inner Join

> courses <- read.csv("Courses.csv")
> courses
  CourseID                       Course Duration_hours   Fee
1        1                R Programming             20 10000
2        2  Machine Learning Algorithms             20 10000
3        3          Data Science with R             75 30000
4        4   Clinical Statistics with R             30 15000
5        5              SAS Programming             80 30000
6        6 Clinical Statistics with SAS             30 25000
> courseSchedule <- read.csv("CourseSchedule.csv")
> courseSchedule
   Sno CourseCode  BeginDate    EndDate            Venue                  Course.name Duration
1    1          1 23-11-2014 13-12-2015        Hinjewadi                R Programming       20
2    2          1 24-11-2014 15-12-2014       Vimannagar                R Programming       20
3    3          2 13-04-2014 13-05-2014        Hinjewadi  Machine Learning Algorithms       20
4    4          2 14-09-2014 12-12-2014       Magarpatta  Machine Learning Algorithms       20
5    5          3 04-05-2014 09-06-2014        Hinjewadi          Data Science with R       75
6    6          3 06-09-2014 07-10-2014       Vimannagar          Data Science with R       75
7    7          3 18-08-2014 23-10-2014       Magarpatta          Data Science with R       75
8    8          4 12-09-2014 13-10-2014       Vimannagar   Clinical Statistics with R       30
9    9          4 14-07-2014 14-08-2014       Magarpatta   Clinical Statistics with R       30
10  10          5 12-11-2014 31-12-2014        Hinjewadi              SAS Programming       80
11  11          6 14-12-2014 03-01-2015 Sakinaka, Mumbai Clinical Statistics with SAS       30
12  12          6 12-01-2015 03-02-2015       Magarpatta Clinical Statistics with SAS       30
13  13          6 12-02-2015 03-03-2015       Vimannagar Clinical Statistics with SAS       30
> crs_info <- courses %>%
+   rename(CourseCode = CourseID) %>%
+   inner_join(courseSchedule, by = "CourseCode")
> crs_info
   CourseCode                       Course Duration_hours   Fee Sno  BeginDate    EndDate            Venue                  Course.name Duration
1           1                R Programming             20 10000   1 23-11-2014 13-12-2015        Hinjewadi                R Programming       20
2           1                R Programming             20 10000   2 24-11-2014 15-12-2014       Vimannagar                R Programming       20
3           2  Machine Learning Algorithms             20 10000   3 13-04-2014 13-05-2014        Hinjewadi  Machine Learning Algorithms       20
4           2  Machine Learning Algorithms             20 10000   4 14-09-2014 12-12-2014       Magarpatta  Machine Learning Algorithms       20
5           3          Data Science with R             75 30000   5 04-05-2014 09-06-2014        Hinjewadi          Data Science with R       75
6           3          Data Science with R             75 30000   6 06-09-2014 07-10-2014       Vimannagar          Data Science with R       75
7           3          Data Science with R             75 30000   7 18-08-2014 23-10-2014       Magarpatta          Data Science with R       75
8           4   Clinical Statistics with R             30 15000   8 12-09-2014 13-10-2014       Vimannagar   Clinical Statistics with R       30
9           4   Clinical Statistics with R             30 15000   9 14-07-2014 14-08-2014       Magarpatta   Clinical Statistics with R       30
10          5              SAS Programming             80 30000  10 12-11-2014 31-12-2014        Hinjewadi              SAS Programming       80
11          6 Clinical Statistics with SAS             30 25000  11 14-12-2014 03-01-2015 Sakinaka, Mumbai Clinical Statistics with SAS       30
12          6 Clinical Statistics with SAS             30 25000  12 12-01-2015 03-02-2015       Magarpatta Clinical Statistics with SAS       30
13          6 Clinical Statistics with SAS             30 25000  13 12-02-2015 03-03-2015       Vimannagar Clinical Statistics with SAS       30

1 Female    20.4   6.91
2 Male      20.3   6.07
3 NA        21.5  NA  
