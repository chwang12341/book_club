# Cupoy讀書會 - 公開課程讀書會筆記 - NumPy Array 數組切割 - NumPy copy & deep copy  帶大家了解使用=賦值和使用copy的差別在哪





哈囉，大家好!!由於小弟最近接到擔任舉辦讀書會的講師，而這個讀書會是根據莫凡Python公開課程所開設的，大家希望我可以帶他們看過莫凡Python的相關系列課程，所以讀書會這個系列主要是根據莫凡Python的公開系列課程講解和筆記，當然我也會額外找尋資料並補充給大家，也因為是根據公開課程的筆記，所以我都會明確記錄出處，如果有違反作者權力，麻煩告知，我會在第一時間立即刪除這系列的文章，感謝大家，當然也要特別感謝莫凡Python這麼厲害的公開課程，讓大家可以無痛初探Python的魔法世界!!



我是跟其他優秀的講師一起開設莫凡Python讀書會的，所以我不會每個章節都有筆記喔XD!!



## 1. NumPy Array 數組切割

課程資料來源: [9 numpy的 array分割 (教学教程)](https://www.youtube.com/watch?v=o1j-biEc1Pc&list=PLXO45tsB95cKKyC45gatc8wEc3Ue7BlI4&index=9)





### 創建數組

```Python
import numpy as np

## 創建數組
A = np.arange(20).reshape((5,4))
print(A)
```

**執行結果**

```
[[ 0  1  2  3]
 [ 4  5  6  7]
 [ 8  9 10 11]
 [12 13 14 15]
 [16 17 18 19]]
```





### 等量縱向切割 - np.split

```Python
## 縱向分割 - 切割成兩段
print(np.split(A, 2, axis = 1))
```

**執行結果**

```
[array([[ 0,  1],
       [ 4,  5],
       [ 8,  9],
       [12, 13],
       [16, 17]]), array([[ 2,  3],
       [ 6,  7],
       [10, 11],
       [14, 15],
       [18, 19]])]
```



### 等量橫向切割 - np.split

```Python
## 橫向切割 - 切成五段
print(np.split(A, 5, axis = 0))
```

**執行結果**

```
[array([[0, 1, 2, 3]]), array([[4, 5, 6, 7]]), array([[ 8,  9, 10, 11]]), array([[12, 13, 14, 15]]), array([[16, 17, 18, 19]])]
```



### 等量切割報錯狀況

```Python
## 當遇到不等量的切割時會報錯
print(np.split(A, 2, axis = 0))
## 因為5沒辦法等量切割成兩段
```

**執行結果**

```
ValueError: array split does not result in an equal division
```



報錯原因: 因為5沒辦法等量切割成兩段



### 不等量切割 - array_split

```Python
print(A)

## 不等量的切割
print(np.array_split(A, 2, axis = 1))
```

**執行結果**

```
[[ 0  1  2  3]
 [ 4  5  6  7]
 [ 8  9 10 11]
 [12 13 14 15]
 [16 17 18 19]]
[array([[ 0,  1],
       [ 4,  5],
       [ 8,  9],
       [12, 13],
       [16, 17]]), array([[ 2,  3],
       [ 6,  7],
       [10, 11],
       [14, 15],
       [18, 19]])]
```





### 更多切割方法 - np.hsplit、np.vsplit

```Python
print(A)

## 水平切割 等同於np.split(A, 5, axis = 0)
print(np.hsplit(A, 2))

## 垂直切割 等同於np.split(A, 2, axis = 1)
print(np.vsplit(A, 5))
```

**執行結果**

```
[[ 0  1  2  3]
 [ 4  5  6  7]
 [ 8  9 10 11]
 [12 13 14 15]
 [16 17 18 19]]
[array([[ 0,  1],
       [ 4,  5],
       [ 8,  9],
       [12, 13],
       [16, 17]]), array([[ 2,  3],
       [ 6,  7],
       [10, 11],
       [14, 15],
       [18, 19]])]
[array([[0, 1, 2, 3]]), array([[4, 5, 6, 7]]), array([[ 8,  9, 10, 11]]), array([[12, 13, 14, 15]]), array([[16, 17, 18, 19]])]
```





## 2. NumPy copy & deep copy 講解

課程資料來源: [10 numpy的 copy & deep copy (教学教程)](https://www.youtube.com/watch?v=lXmiDyktnCA&list=PLXO45tsB95cKKyC45gatc8wEc3Ue7BlI4&index=10)



### 創建數組

```Python
import numpy as np

a = np.arange(6)
print(a)
```

**執行結果**

```
[0 1 2 3 4 5]
```



### 使用 = 來創建一樣的數組

```Python
## 賦值
b = a
c = a
d = b
print(a, b, c, d)
```

**執行結果**

```
[0 1 2 3 4 5] [0 1 2 3 4 5] [0 1 2 3 4 5] [0 1 2 3 4 5]
```



### 更改A的時候會同時影響所有用=創建的數組

```Python
## 當改變a的時候，b、c、d都會跟著改變
a[0] = 11
print(a, b, c, d)

## 判斷b、c、d是否與a一樣
print(b is a)
print(c == a)
print(d is a)
```

**執行結果**

```
[11  1  2  3  4  5] [11  1  2  3  4  5] [11  1  2  3  4  5] [11  1  2  3  4  5]
True
[ True  True  True  True  True  True]
True
```



**更改D也同時會影響A、B、C**

```Python
## 更改d值，a、b、c也會更著改變
d[2:5] = [6,6,6]
print(a, b, c, d)
```

**執行結果**

```
[11  1  6  6  6  5] [11  1  6  6  6  5] [11  1  6  6  6  5] [11  1  6  6  6  5]
```



### 使用copy來構建複本，當A更改後就不會影響COPY所創建出來的複本

```Python
## 使用copy創建a的複本e，改變a的時候就不會影響b
e = a.copy()
print(e)
a[1] = 100
print(a)
print(e)
print(a is e)
```

**執行結果**

```
[ 11 100   6   6   6   5]
[ 11 100   6   6   6   5]
[ 11 100   6   6   6   5]
False
```

