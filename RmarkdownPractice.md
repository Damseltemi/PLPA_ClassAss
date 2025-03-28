# Example of R code in Rmarkdown

``` r
# this is R code
summary(mtcars)
```

    ##       mpg             cyl             disp             hp       
    ##  Min.   :10.40   Min.   :4.000   Min.   : 71.1   Min.   : 52.0  
    ##  1st Qu.:15.43   1st Qu.:4.000   1st Qu.:120.8   1st Qu.: 96.5  
    ##  Median :19.20   Median :6.000   Median :196.3   Median :123.0  
    ##  Mean   :20.09   Mean   :6.188   Mean   :230.7   Mean   :146.7  
    ##  3rd Qu.:22.80   3rd Qu.:8.000   3rd Qu.:326.0   3rd Qu.:180.0  
    ##  Max.   :33.90   Max.   :8.000   Max.   :472.0   Max.   :335.0  
    ##       drat             wt             qsec             vs        
    ##  Min.   :2.760   Min.   :1.513   Min.   :14.50   Min.   :0.0000  
    ##  1st Qu.:3.080   1st Qu.:2.581   1st Qu.:16.89   1st Qu.:0.0000  
    ##  Median :3.695   Median :3.325   Median :17.71   Median :0.0000  
    ##  Mean   :3.597   Mean   :3.217   Mean   :17.85   Mean   :0.4375  
    ##  3rd Qu.:3.920   3rd Qu.:3.610   3rd Qu.:18.90   3rd Qu.:1.0000  
    ##  Max.   :4.930   Max.   :5.424   Max.   :22.90   Max.   :1.0000  
    ##        am              gear            carb      
    ##  Min.   :0.0000   Min.   :3.000   Min.   :1.000  
    ##  1st Qu.:0.0000   1st Qu.:3.000   1st Qu.:2.000  
    ##  Median :0.0000   Median :4.000   Median :2.000  
    ##  Mean   :0.4062   Mean   :3.688   Mean   :2.812  
    ##  3rd Qu.:1.0000   3rd Qu.:4.000   3rd Qu.:4.000  
    ##  Max.   :1.0000   Max.   :5.000   Max.   :8.000

# Example of included figures

``` r
library(ggplot2)
```

    ## Warning: package 'ggplot2' was built under R version 4.3.2

``` r
library(knitr)
library(markdown)
data("mtcars")
ggplot(mtcars, aes(x=wt, y=mpg)) +
  geom_smooth(method = lm, se =FALSE) +
  geom_point(aes(color = wt)) +
  xlab("weight") +
  ylab ("Mile per gallon") +
  scale_color_gradient(low ="forestgreen", high ="black")
```

    ## `geom_smooth()` using formula = 'y ~ x'

![](RmarkdownPractice_files/figure-gfm/unnamed-chunk-1-1.png)<!-- -->

## R markdown formatting options and putting in chunks

``` markdown
# First-level header

## Second-level header

### Third-level header
```

## Styling header

# First level header

**this is a italics in bold**

## second level header

### Third level header

#### Fourth level header

### style and emphasis

``` markdown
`*Zonocerus*`
```

*Zonocerus*

``` markdown
`_Zonocerus_` 
```

*Zonocerus*

``` markdown
`**Zonocerus**` 
```

**Zonocerus**

``` markdown
`__Zonocerus__`
```

**Zonocerus**

``` markdown
> "I thoroughly enjoy this course.it will make me more efficient in R."
>
> --- Temitope
```

``` markdown
- one item
- one item
- one item
    - one more item
    - one more item
    - one more item
```

- one item
- another item
- one subitem
  - one item
  - second time
  - sub item

``` markdown
1. one item
2. two items
3. three items
  _ other item
  _ sub other item
```

## Name of important pest

*Zonocerus*

**Zonocerus**

## Inserting Links

[Link to my
github](https://github.com/Damseltemi/PLPA_ClassAss/blob/main/RmarkdownPractice.md)

## Insering Image

![ggplot example](Plot3.jpg)

### Formatted tables

``` r
library(knitr)
kable(head(mtcars, n = 5), digits = 3, format = "markdown")
```

|                   |  mpg | cyl | disp |  hp | drat |    wt |  qsec |  vs |  am | gear | carb |
|:------------------|-----:|----:|-----:|----:|-----:|------:|------:|----:|----:|-----:|-----:|
| Mazda RX4         | 21.0 |   6 |  160 | 110 | 3.90 | 2.620 | 16.46 |   0 |   1 |    4 |    4 |
| Mazda RX4 Wag     | 21.0 |   6 |  160 | 110 | 3.90 | 2.875 | 17.02 |   0 |   1 |    4 |    4 |
| Datsun 710        | 22.8 |   4 |  108 |  93 | 3.85 | 2.320 | 18.61 |   1 |   1 |    4 |    1 |
| Hornet 4 Drive    | 21.4 |   6 |  258 | 110 | 3.08 | 3.215 | 19.44 |   1 |   0 |    3 |    1 |
| Hornet Sportabout | 18.7 |   8 |  360 | 175 | 3.15 | 3.440 | 17.02 |   0 |   0 |    3 |    2 |
