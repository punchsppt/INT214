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


### 2. หนังสือประเภท Paperback ที่มีราคาต่ำกว่า 20 โชว์ข้อมูลเฉพาะชื่อหนังสือ  ประเภทและราคา
```
books %>% select(Book_title, Type, Price) %>% filter(Type %in% "Paperback" & Price < 20)
```

Result:

```
# A tibble: 10 × 3
   Book_title                          Type    Price
   <chr>                               <chr>   <dbl>
 1 The Meme Machine                    Paperb…  14.2
 2 ZX Spectrum Games Code Club: Twent… Paperb…  14.6
 3 Ship It!                            Paperb…  15.3
 4 The Quark and the Jaguar: Adventur… Paperb…  16.4
 5 Linked: How Everything Is Connecte… Paperb…  16.9
 6 Debugging: The 9 Indispensable Rul… Paperb…  17.5
 7 Help Your Kids with Computer Coding Paperb…  18.9
 8 The Code Book: The Science of Secr… Paperb…  19.1
 9 Game Programming Golden Rules       Paperb…  19.2
10 The Architecture of Open Source Ap… Paperb…  19.2
```
//Explain

- list 1
- list 2
---



### 3. หนังสือที่มีจำนวนหน้าน้อยที่สุด คือเรื่องอะไร ประเภทไหนและมีราคาเท่าไร 
```
books %>% select(Book_title, Type, Number_Of_Pages ,Price) %>% filter(Number_Of_Pages == min(Number_Of_Pages))
```

Result:

```
# A tibble: 1 × 4
  Book_title           Type    Number_Of_Pages Price
  <chr>                <chr>             <dbl> <dbl>
1 Responsive Web Desi… Kindle…              50  11.3
```
//Explain

- list 1
- list 2
---


### 4. หาค่าเฉลี่ยของ rating ของหนังสือแต่ละประเภท
```
books %>% group_by(Type) %>% summarise(Rating_mean = mean(Rating))
```

Result:

```
# A tibble: 6 × 2
  Type                  Rating_mean
  <chr>                       <dbl>
1 Boxed Set - Hardcover        4.49
2 ebook                        4.29
3 Hardcover                    4.06
4 Kindle Edition               4.01
5 Paperback                    4.06
6 Unknown Binding              3.99
```
//Explain

- list 1
- list 2
---



### 5. หนังสือที่ไม่มี review เลยคือเรื่องใด
```
books %>% select(Book_title, Reviews) %>% filter(Reviews == 0) %>% print(n = 20)
```

Result:

```
# A tibble: 22 × 2
   Book_title                                Reviews
   <chr>                                       <dbl>
 1 Responsive Web Design Overview For Begin…       0
 2 ZX Spectrum Games Code Club: Twenty fun …       0
 3 Game Programming Golden Rules                   0
 4 Beginners Guide On PHP Programming: Quic…       0
 5 Python Programming Books Set: Python Pro…       0
 6 Your First App: Node.js                         0
 7 Python Programming For Beginners: Quick …       0
 8 Building an FPS Game with Unity                 0
 9 Advanced Game Programming: A Gamedev.Net…       0
10 Basic Proof Theory                              0
11 Cross-Platform Game Programming (Game De…       0
12 Lambda-Calculus, Combinators and Functio…       0
13 The Calculus of Computation: Decision Pr…       0
14 Communication Networks: Fundamental Conc…       0
15 Genetic Programming II: Automatic Discov…       0
16 Game Programming Gems 2                         0
17 Game Programming Gems 5                         0
18 A First Course in Logic: An Introduction…       0
19 Game Programming Gems 6                         0
20 Game Programming Gems 4                         0
# … with 2 more rows
```
//Explain

- list 1
- list 2
---



### 6. หนังสือที่มีจำนวนหน้าอยู่ระหว่าง 550-600 และมีราคาไม่เกิน 70 มีเรื่องใดบ้าง
```
books %>% select(Book_title, Number_Of_Pages, Price) %>% filter(Number_Of_Pages >= 550 & Number_Of_Pages <= 600 & Price <= 70)
```

Result:

```
# A tibble: 8 × 3
  Book_title                   Number_Of_Pages Price
  <chr>                                  <dbl> <dbl>
1 Agile Web Development with …             558  24.5
2 Python Crash Course: A Hand…             560  26.3
3 Best of Game Programming Ge…             576  33.5
4 CSS: The Missing Manual                  560  35.1
5 C# in Depth                              554  44.4
6 The Boost C++ Libraries                  570  50.5
7 Dependency Injection in .NET             584  61.9
8 Domain-Specific Languages                597  64.4
> 
```
//Explain

- list 1
- list 2
