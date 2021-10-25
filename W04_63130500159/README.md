# R-Assignment 4

Created by Supapit Rattanataveesophon (ID : 63130500159)

Choose Dataset:
1. Top 270 Computer Science / Programing Books (Data from Thomas Konstantin, [Kaggle](https://www.kaggle.com/thomaskonstantin/top-270-rated-computer-science-programing-books)) >> [Using CSV](https://raw.githubusercontent.com/safesit23/INT214-Statistics/main/datasets/prog_book.csv)


### Outlines
1. Explore the dataset
2. Learning function from Tidyverse
3. Transform data with dplyr and finding insight the data
4. Visualization with GGplot2




## Part 1 : Explore the dataset

```
# Install packages (If you used to install packages before, you can over this step.)
    install.packages("tidyverse")
   install.packages("assertive")

# Listing packages
   library(tidyverse)
   library(assertive)

# Import the dataset
   books <- read_csv("https://raw.githubusercontent.com/safesit23/INT214-Statistics/main/datasets/prog_book.csv")

# View dataset
   View(books)
   # or
   glimpse(books)
```

### Dataset information
In this dataset has 271 rows and 7 columns.

#### Check by :
```
 glimpse(books)
```

Result :
```
Rows: 271
Columns: 7
$ Rating          <dbl> 4.17, 4.01, 3.33, 3.97, 4.06,…
$ Reviews         <dbl> 3829, 1406, 0, 1658, 1325, 11…
$ Book_title      <chr> "The Elements of Style", "The…
$ Description     <chr> "This style manual offers pra…
$ Number_Of_Pages <dbl> 105, 527, 50, 393, 305, 288, …
$ Type            <chr> "Hardcover", "Hardcover", "Ki…
$ Price           <dbl> 9.323529, 11.000000, 11.26764…
```

Explain :  
    In this dataset has 271 rows and 7 columns as follows
- Rating : The user rating for the book. the rating score ranges between 0 and 5. The data type is double.  
- Reviews : The number of reviews found on this book. The data type is double.
- Book_title : The name of the book. The data type is character.
- Description : A short description of the book. The data type is character.
- Number_Of_Pages : Number of pages in the book. The data type is double.
- Type : The type of the book meaning is it a hardcover book or an ebook or a kindle book etc. The data type is character.
- Price : The average price of the book in USD where the average is calculated according the 5 web sources. The data type is double.
---


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


## Part 3: Transform data with dplyr and finding insight the data

//Explain here

```
#Code here
```

Result:

```
#Copy Result from console to here
```
//Explain

- list 1
- list 2

## Part 4: Visualization with GGplot2
### 1.) Graph show relation between height and mass
```
scat_plot <- starwars %>% filter(mass<500) %>% ggplot(aes(x=height,y=mass))+
  geom_point(aes(color=gender))

scat_plot+geom_smooth()
```
Result:

![Graph 1](graph1.png)

**Guideline:
Embed Image by using this syntax in markdown file
````
![Name](imageFile)
````

