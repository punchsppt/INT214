## Part 4: Visualization with GGplot2
### 1. Graph show the number of books for each types.
```
# bar chart
barplot <- books %>% ggplot(aes(x = Type)) + geom_bar(width = 0.7) + 
           ggtitle("Number of books of each types") + 
           xlab("Type of books") + ylab("Number of books")
           
# pie chart
pie <- num_of_books %>% ggplot(aes(x="", y=n, fill=Type)) + geom_col() + 
                 coord_polar(theta = "y") + geom_text(aes(label = n),
                 position = position_stack(vjust = 0.5)) + theme_void()
```
Result:

<img src="bar.png">
<img src="pie.png">

### 2. Graph show relation between rating and reviews which rating has more than equal 4.2.
```
scatter <- books%>% filter(Rating > 4.2) %>%
           ggplot(aes(x=Rating, y=Reviews)) + geom_point(aes(color=Type)) +
           ggtitle("Relation between rating and reviews")

```
Result:

<img src="scatter.png">
