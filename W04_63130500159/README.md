# R-Assignment 4

Created by Supapit Rattanataveesophon (ID : 63130500159)

Choose Dataset:
1. Top 270 Computer Science / Programing Books (Data from Thomas Konstantin, [Kaggle](https://www.kaggle.com/thomaskonstantin/top-270-rated-computer-science-programing-books)) >> [Using CSV](https://raw.githubusercontent.com/safesit23/INT214-Statistics/main/datasets/prog_book.csv)


### Outlines
1. Explore the dataset
2. Learning function from Tidyverse
3. Transform data with dplyr and finding insight the data
4. Visualization with GGplot2




## Part 1: Explore the dataset

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

In this dataset has : `271 rows and 7 columns`
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





## Part 2: Learning function from Tidyverse

- Function `select()` from package [dplyr](https://dplyr.tidyverse.org/articles/dplyr.html#select-columns-with-select)). It using for select columns

```
starwars %>% select(name,height)
```
** You can sepearate this part or combine in part of `Transform data with dplyr and finding insight the data`

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

