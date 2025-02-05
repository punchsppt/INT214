## Part 4: Visualization with GGplot2
### 1. Graph show the number of books for each types.
**Code :**
```
# bar chart
  barplot <- books %>% ggplot(aes(x = Type)) + geom_bar(width = 0.7) + 
             ggtitle("Number of books of each types") + 
             xlab("Type of books") + ylab("Number of books") +
             ggtitle("Graph show the number of books for each types")
  barplot
           
# pie chart
  pie <- num_of_books %>% ggplot(aes(x="", y=n, fill=Type)) + geom_col() + 
                          coord_polar(theta = "y") + geom_text(aes(label = n),
                          position = position_stack(vjust = 0.5)) + theme_void() +
                          ggtitle("Graph show the number of books for each types")
  pie
```
**Result :**
<p align="center">
<img src="bar2.png" width=700> 
<img src="pie3.png" width=700>
</p>

**Explain :**
Two of graphs show the number of books for each types as follows
- Boxed Set - Hardcover has 1 book. 
- ebook has 7 books. 
- Hardcover has 95 books. 
- Kindle Edition has 19 books. 
- Paperback has 156 books. 
- Unknown Blinding has 2 books.

---

### 2. Graph shows relation between rating and reviews which rating has more than 4.2 points.
**Code :**
```
# scatter plot
  scatter <- books%>% filter(Rating > 4.2) %>%
             ggplot(aes(x=Rating, y=Reviews)) + geom_point(aes(color=Type)) +
             ggtitle("Graph show relation between rating and reviews")
  scatter
```

**Result :**  
<p align="center">
<img src="scatter2.png" width=700>
</p>

**Explain :**
This graph shows relation between rating and reviews which rating has more than 4.2 points.

---  
### Let's see graphs and charts that create by BI tools : tablueau [click here !](https://public.tableau.com/views/chart_16352816996460/chart?:language=en-US&:display_count=n&:origin=viz_share_link)
