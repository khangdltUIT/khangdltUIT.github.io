---
layout: post
tittle: Linear Regression
categories: Machine
---

# &ensp; &ensp; Linear Regression with one variable
### Model and cost Function

Giả sử chúng ta có 1 tập dữ liệu về giá nhà đất tương tự như sau:

|Size in feet²(x) |&ensp; Price($) in 1000(y)|
|-----------------|:-------------------------|
|2104             |&ensp;460                 |
|1416             |&ensp;232                 |
|1534             |&ensp;315                 |
|852              |&ensp;178                 |

Trong đó:
* m = số lượng traning example
* x's = input / *feature*
* y's = output / *target* variable
* (x;y) → 1 training example
* (xᶦ;yᶦ) → i training example

Cách 1 thuật toán supervised learning làm việc tương tự như sau:

![alt](https://anujdutt9.github.io/assets/images/posts/2018/SL.png)
