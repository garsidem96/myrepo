```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = TRUE)
```

```{r}
library(gapminder)
library(tidyverse)
```

```{r}
gapminder2 <- gapminder %>%
  mutate(pop = pop/100000) %>%
  filter(country != "Kuwait")
```

```{r}
Weighted_mean <- gapminder2 %>%
  group_by(continent, year) %>%
  summarise(wm = weighted.mean(gdpPercap, pop), pop=sum(pop))
Weighted_mean
```

```{r}
ggplot(data = gapminder2) +
  geom_point(mapping = aes(x = year, y = gdpPercap, color = continent, size = pop)) +
  geom_line(mapping = aes(x = year, y = gdpPercap, color = continent, group = country)) +
  geom_point(data = Weighted_mean, aes(y = wm, x=year, size = pop), color="black") +
  geom_line(data = Weighted_mean, aes(y = wm, x=year), color="black") +
  facet_wrap(~ continent, nrow = 1) +
  labs(x = "Year", y = "GDP per capita", size = "Population (100k)") +
  theme_bw()
``` 