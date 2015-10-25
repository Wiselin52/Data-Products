Dataproducts presentation
========================================================
author: Wiselin Dhas Mathuram
date: 10/25/2015

Regression Analysis
========================================================

What is Regrssion Analysis

- Statistical process for estimating the relationships among variables.

- Its focus is on the relationship between a dependent variable and one or more independent variables

- It is used for Predictive Analysis

Fittng a regressin Model Using R
========================================================


```r
# sets the working directory and Read data into R
setwd("C:/Users/wmathura/Documents")
mydata<-read.csv("Ozone_data.csv")
# Runs a Regression model and gives the summary output
summary(lm(Ozone ~ Temp+Wind, data = mydata))
```

```

Call:
lm(formula = Ozone ~ Temp + Wind, data = mydata)

Residuals:
    Min      1Q  Median      3Q     Max 
-42.156 -13.216  -3.123  10.598  98.492 

Coefficients:
            Estimate Std. Error t value Pr(>|t|)    
(Intercept) -67.3220    23.6210  -2.850  0.00524 ** 
Temp          1.8276     0.2506   7.294 5.29e-11 ***
Wind         -3.2948     0.6711  -4.909 3.26e-06 ***
---
Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1

Residual standard error: 21.73 on 108 degrees of freedom
Multiple R-squared:  0.5814,	Adjusted R-squared:  0.5736 
F-statistic: 74.99 on 2 and 108 DF,  p-value: < 2.2e-16
```

How to calculate Correlation in R
========================================================


```r
# draws a correlation plot
pairs(mydata)
```

![plot of chunk unnamed-chunk-2](Dataproducts presentation-figure/unnamed-chunk-2-1.png) 
Hypothesis Testing
========================================================
- Hypothesis testing is an essential procedure in statistics.
- A hypothesis test evaluates two mutually exclusive statements about a population to determine which statement is best supported by the sample data.

Hypothesis Testing in R
========================================================

Separating Ozone data from the data sheet and then applyting T Test

```r
newdata <- mydata[c(1)]
t.test(newdata,alternative = "less", mu= 50)
```

```

	One Sample t-test

data:  newdata
t = -2.5015, df = 110, p-value = 0.006919
alternative hypothesis: true mean is less than 50
95 percent confidence interval:
     -Inf 47.33835
sample estimates:
mean of x 
  42.0991 
```

