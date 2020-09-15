# p8105_hw1_ll3452
Assignment 1

library(tidyverse)
library(ggplot2)
df = tibble(num = rnorm(10), log_vec = as.logical(num > 0) , char_vec = c('a','b','c','b','c','c','a','b','a','c'), fac_vec = factor(char_vec))
mean(df$num)
mean(df$log_vec)
mean(df$char_vec)
mean(df$fac_vec)

as.numeric(df$log_vec)
as.numeric(df$char_vec)
as.numeric(df$fac_vec)

### char_vec cannot be converted into numerical objects. So, taking the mean of 
### char_vec is impossible

numeric_log_vec = as.numeric(df$log_vec)
result1 = df$num * numeric_log_vec

fac_log_vec = factor(df$log_vec)
result2 = df$num * fac_log_vec

num_fac_log_vec = as.numeric(fac_log_vec)
result3 = df$num * num_fac_log_vec

### Problem 2
penguins_ds = palmerpenguins::penguins
new_flipper_length = na.omit(penguins_ds$flipper_length_mm)
mean(new_flipper_length)

ggplot(penguins_ds, aes(x = penguins_ds$bill_length_mm, y = penguins_ds$flipper_length_mm, color = 'species')) + geom_point()
