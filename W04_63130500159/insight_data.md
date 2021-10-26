## Part 3: Transform data with dplyr and finding insight the data

### 1. จำนวนหนังสือทั้งหมดโดยแยกตามประเภทของหนังสือ

```
num_of_books <- books %>% group_by(Type) %>% count()
num_of_books
```

Result:

```
# A tibble: 6 × 2
# Groups:   Type [6]
  Type                      n
  <chr>                 <int>
1 Boxed Set - Hardcover     1
2 ebook                     7
3 Hardcover                95
4 Kindle Edition           10
5 Paperback               156
6 Unknown Binding           2
```
//Explain

- list 1
- list 2

---
//Explain here

```
num_of_books <- books %>% group_by(Type) %>% count()
num_of_books
```

Result:

```
# A tibble: 6 × 2
# Groups:   Type [6]
  Type                      n
  <chr>                 <int>
1 Boxed Set - Hardcover     1
2 ebook                     7
3 Hardcover                95
4 Kindle Edition           10
5 Paperback               156
6 Unknown Binding           2
```
//Explain

- list 1
- list 2
