## Part 2: Learning function from Tidyverse 
Tidyverse is a collection of R packages for data manipulation, exploration and visualization that share a common design philosophy.   
1. Data Wrangling and Transformation
- Function `select()` from package [dplyr](https://dplyr.tidyverse.org/articles/dplyr.html#select-columns-with-select). : It's using for select columns from your dataset.

```
books %>% select(Book_title, Price)
```
Result :
```
# A tibble: 271 × 2
   Book_title                                              Price
   <chr>                                                   <dbl>
 1 The Elements of Style                                    9.32
 2 The Information: A History, a Theory, a Flood           11   
 3 Responsive Web Design Overview For Beginners            11.3 
 4 Ghost in the Wires: My Adventures as the World's Most … 12.9 
 5 How Google Works                                        13.2 
 6 The Meme Machine                                        14.2 
 7 Start with Why: How Great Leaders Inspire Everyone to … 14.2 
 8 Algorithms to Live By: The Computer Science of Human D… 14.4 
 9 Weapons of Math Destruction: How Big Data Increases In… 14.5 
10 ZX Spectrum Games Code Club: Twenty fun games to code … 14.6 
# … with 261 more rows
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

-  Function `arrange()` from package [dplyr](https://dplyr.tidyverse.org/articles/dplyr.html#select-columns-with-select). : It's using for Arrange your column data in ascending or descending order. 
```
books %>% arrange(desc(Rating))
```
Result :
```
# A tibble: 271 × 7
   Rating Reviews Book_title  Description  Number_Of_Pages Type 
    <dbl>   <dbl> <chr>       <chr>                  <dbl> <chr>
 1   5          0 Your First… "A tutorial…             317 ebook
 2   4.77       4 The Art of… "\"The bibl…            3168 Hard…
 3   4.72     362 Designing … "Want to kn…             616 Pape…
 4   4.67       1 Build Web … "This book …             372 Pape…
 5   4.67      78 Fluent Pyt… "Python's s…             792 Pape…
 6   4.62       0 ZX Spectru… "This book …             128 Pape…
 7   4.62      28 The Linux … "The Linux …            1506 Hard…
 8   4.58      58 CLR via C#… "Dig deep a…             863 Pape…
 9   4.54      52 The Elemen… "This book …             325 Hard…
10   4.54     171 Practical … "The Comple…             247 Pape…
# … with 261 more rows, and 1 more variable: Price <dbl>
```
---
### Next to : Transform data with dplyr and finding insight the data [Click Here!](https://github.com/punchsppt/INT214/blob/main/W04_63130500159/insight_data.md)
