Case Study 2
================

``` r
library(gapminder)
```

    ## Warning: package 'gapminder' was built under R version 3.6.3

``` r
library(tidyverse)
```

    ## -- Attaching packages ----------------------------------------------------------------------------------------------------- tidyverse 1.2.1 --

    ## v ggplot2 3.2.1     v purrr   0.3.2
    ## v tibble  2.1.3     v dplyr   0.8.3
    ## v tidyr   1.0.0     v stringr 1.4.0
    ## v readr   1.3.1     v forcats 0.4.0

    ## -- Conflicts -------------------------------------------------------------------------------------------------------- tidyverse_conflicts() --
    ## x dplyr::filter() masks stats::filter()
    ## x dplyr::lag()    masks stats::lag()

``` r
#View(gapminder)

gapminder2 <- filter(gapminder, country != "Kuwait") %>%
  mutate(pop = pop/100000)

#View(gapminder2)

ggplot(data = gapminder2) +
  geom_point(mapping = aes(x = lifeExp, y = gdpPercap, size = pop, color = continent)) +
  scale_y_continuous(trans = "sqrt") +
  facet_wrap(~ year, nrow = 1) +
  labs(x = "Life Expectancy", y = "GDP per capita", size = "Population (100k)")
```

![](Case-Study-2_files/figure-gfm/unnamed-chunk-1-1.png)<!-- -->
