Data visualisation
================
Alina Ismagilova
2021-22-09

``` r
library(ggplot2)
library(dplyr)
```

    ## 
    ## Attaching package: 'dplyr'

    ## The following objects are masked from 'package:stats':
    ## 
    ##     filter, lag

    ## The following objects are masked from 'package:base':
    ## 
    ##     intersect, setdiff, setequal, union

``` r
library(rmarkdown)
```

``` r
url <- "https://raw.githubusercontent.com/lukaseamus/marine-microplastic/main/STOTEN/fragments.csv"
download.file(url, destfile = basename(url)) 
```


    ```r
    fragments <- read.csv("fragments.csv")

``` r
ggplot(data = fragments, aes(x = polymer, y = fragments, fill = use)) +
  geom_col(color = 'black',  size = 0.3, width = 0.5, position = 'dodge') +
  facet_wrap(~diameter) +
  ylab(expression("Abraded microplastic fragments (m"^-1*")"))
```

![](Homework_files/figure-gfm/unnamed-chunk-4-1.png)<!-- -->

``` r
ggsave(file="graph1.png")
```

    ## Saving 7 x 5 in image

``` r
ggplot(data = fragments, aes(x = polymer, y = mass, fill = use)) +
  geom_col(color = 'black',  size = 0.3, width = 0.5, position = 'dodge') +
  facet_wrap(~diameter) +
  ylab(expression("Abraded microplastic mass ("*mu*"g m"^-1*")"))
```

![](Homework_files/figure-gfm/unnamed-chunk-5-1.png)<!-- -->

``` r
ggsave(file="graph2.png")
```

    ## Saving 7 x 5 in image

``` r
ggplot(data = fragments, aes(x = polymer, y = density, fill = use)) +
  geom_col(color = 'black',  size = 0.3, width = 0.5, position = 'dodge') +
  facet_wrap(~diameter)
```

![](Homework_files/figure-gfm/unnamed-chunk-6-1.png)<!-- -->

``` r
ggsave(file="graph3.png")
```

    ## Saving 7 x 5 in image

``` r
ggplot(data = fragments, aes(x = polymer, y = fragment.volume, fill = use)) +
  geom_col(color = 'black',  size = 0.3, width = 0.5, position = 'dodge') +
  facet_wrap(~diameter)
```

![](Homework_files/figure-gfm/unnamed-chunk-7-1.png)<!-- -->

``` r
ggsave(file="graph4.png")
```

    ## Saving 7 x 5 in image
