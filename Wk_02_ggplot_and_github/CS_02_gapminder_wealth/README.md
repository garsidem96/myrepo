```{r}
library(gapminder)
library(tidyverse)
#View(gapminder)

gapminder2 <- filter(gapminder, country != "Kuwait") %>%
  mutate(pop = pop/100000)

#View(gapminder2)

wealth_graph <- ggplot(data = gapminder2) +
  geom_point(mapping = aes(x = lifeExp, y = gdpPercap, size = pop, color = continent)) +
  scale_y_continuous(trans = "sqrt") +
  facet_wrap(~ year, nrow = 1) +
  labs(x = "Life Expectancy", y = "GDP per capita", size = "Population (100k)")

Wealth_graph
  
ggsave(filename = "Wealth_graph.png", plot = last_plot())
```
