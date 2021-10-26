## Part 2 : Learning function from Tidyverse
Tidyverse is a collection of R packages for data manipulation, exploration and visualization that share a common design philosophy.   
### Data Wrangling and Transformation
- Function `filter()` from package [dplyr](https://dplyr.tidyverse.org/reference/filter.html#details). : It's using for filter out certain rows that meet your criteria(s).
- Function `str_detect()` from package [stringr](https://stringr.tidyverse.org/#usage). : It's using for detect the presence or absence of a pattern in a character string which would return TRUE or FALSE. 

For example :
```
# Show book that has "Art" in the title of book.
   books %>% filter(Book_title %>% str_detect("Art"))
```
Result :
```
# A tibble: 8 × 7
  Rating Reviews Book_title      Description     Number_Of_Pages Type   Price
   <dbl>   <dbl> <chr>           <chr>                     <dbl> <chr>  <dbl>
1   3.87     593 The Art of the… "A new product…             240 Hardc…  15.9
2   3.75     370 Our Final Inve… "In as little …             336 Hardc…  16.9
3   4.25      41 The Sciences o… "Continuing hi…             248 Paper…  45.8
4   4.37      44 The Art of Com… "The bible of …             672 Hardc…  93.5
5   4.18     130 Artificial Int… "For one or tw…            1132 Hardc… 116. 
6   4.26       5 Numerical Reci… "Co-authored b…            1235 Hardc… 176. 
7   4.49      36 The Art of Com… "Knuth's class…             896 Boxed… 220. 
8   4.77       4 The Art of Com… "\"The bible o…            3168 Hardc… 220.
```

- Function `filter()` from package [dplyr](https://dplyr.tidyverse.org/articles/dplyr.html#select-columns-with-select). : It's using for filter out certain rows that meet your criteria(s).
```
books %>% filter(Type %in% "Hardcover" & Rating > 4.4) # show data which type is Hardcover
```
Result :
```
# A tibble: 6 × 7
  Rating Reviews Book_title   Description  Number_Of_Pages Type 
   <dbl>   <dbl> <chr>        <chr>                  <dbl> <chr>
1   4.54      52 The Element… "This book …             325 Hard…
2   4.62      28 The Linux P… "The Linux …            1506 Hard…
3   4.46     164 Structure a… "There are …             657 Hard…
4   4.41      48 Algorithms   "This fourt…             976 Hard…
5   4.42      38 Computer Sy… "For Comput…             978 Hard…
6   4.77       4 The Art of … "\"The bibl…            3168 Hard…
# … with 1 more variable: Price <dbl>
```
---
### Next to : Transform data with dplyr and finding insight the data [Click Here!](https://github.com/punchsppt/INT214/blob/main/W04_63130500159/insight_data.md)
