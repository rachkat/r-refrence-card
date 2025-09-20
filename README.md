![R](https://img.shields.io/badge/R-276DC3?logo=r&logoColor=white)
![Type](https://img.shields.io/badge/Type-Reference--Card-blue)
![License](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey)

# R Reference Card

A one-pager of R/RStudio basics, data wrangling, modeling, and plotting compiled from course notes.

- 📄 **View/Download the PDF:** [`r-reference-card.pdf`](./r-refrence-card.pdf)

## Preview (pages)
<p>
  <img src="assets/r_reference_card_page_1.png" width="900" alt="R Reference Card page 1">
  <img src="assets/r_reference_card_page_2.png" width="900" alt="R Reference Card page 2">
  <img src="assets/r_reference_card_page_3.png" width="900" alt="R Reference Card page 3">
  <img src="assets/r_reference_card_page_4.png" width="900" alt="R Reference Card page 4">
  <img src="assets/r_reference_card_page_5.png" width="900" alt="R Reference Card page 5">
  <img src="assets/r_reference_card_page_6.png" width="900" alt="R Reference Card page 6">
  <img src="assets/r_reference_card_page_7.png" width="900" alt="R Reference Card page 7">
</p>

---

## Quick commands (searchable)
```r
# Packages
install.packages("dplyr", dependencies = TRUE); library(dplyr)

# Read CSV + inspect
df <- read.csv("path/to/data.csv", stringsAsFactors = TRUE)
head(df); str(df); summary(df)

# Wrangle (dplyr)
library(dplyr)
df2 <- df |>
  filter(!is.na(x)) |>
  mutate(rate = x / y) |>
  group_by(group) |>
  summarise(n = n(), avg = mean(rate, na.rm = TRUE)) |>
  arrange(desc(avg))

# Model (linear)
m <- lm(mpg ~ wt + hp, data = mtcars)
summary(m); plot(resid(m))

# Plot (ggplot2)
library(ggplot2)
ggplot(df, aes(group, value, fill = group)) +
  geom_col() + labs(x = NULL, y = "Value") + theme_minimal()
