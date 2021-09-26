# Cupoy讀書會 - 公開課程讀書會筆記 - NumPy索引 - NumPy Array 數組合併



哈囉，大家好!!由於小弟最近接到擔任舉辦讀書會的講師，而這個讀書會是根據莫凡Python公開課程所開設的，大家希望我可以帶他們看過莫凡Python的相關系列課程，所以讀書會這個系列主要是根據莫凡Python的公開系列課程講解和筆記，當然我也會額外找尋資料並補充給大家，也因為是根據公開課程的筆記，所以我都會明確記錄出處，如果有違反作者權力，麻煩告知，我會在第一時間立即刪除這系列的文章，感謝大家，當然也要特別感謝莫凡Python這麼厲害的公開課程，讓大家可以無痛初探Python的魔法世界!!



我是跟其他優秀的講師一起開設莫凡Python讀書會的，所以我不會每個章節都有筆記喔XD!!



## 1. NumPy 索引

課程資料來源: [7 numpy的索引 (教学教程)](https://www.youtube.com/watch?v=82Tva71Lm1E&list=PLXO45tsB95cKKyC45gatc8wEc3Ue7BlI4&index=8)





### 一維索引



**單個索引**

```Python
import numpy as np
## 創建一維數組
A = np.arange(2, 18)
print(A)
## 索引第七個元素
print(A[6])
```

**執行結果**

```
[ 2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17]
8
```



### 二維索引



#### 索引行

```Python
## 創建二維數組
A = np.arange(2, 18).reshape((4,4))
print(A)
## 索引第四行
print(A[3])
```

**執行結果**

```
[[ 2  3  4  5]
 [ 6  7  8  9]
 [10 11 12 13]
 [14 15 16 17]]
[14 15 16 17]
```





#### 單個索引

**第一種方法**

```Python
## 索引第二行第三列
print(A[1][2])
```

**執行結果**

```
8
```



**第二種方法**

```Python
## 索引第二行第三列
print(A[1, 2])
```

**執行結果**

```
8
```



#### 範圍索引

```Python
## 索引第二行的第二列到第三列
print(A[1, 1:3])
```

**執行結果**

```
[7 8]
```



#### 逐列進行列印

```Python
## 一行一行列印出來
for row in A:
    print(row)
```

**執行結果**

```
[2 3 4 5]
[6 7 8 9]
[10 11 12 13]
[14 15 16 17]
```



#### 逐行進行列印

```Python
## 一列一列印出來
for column in np.transpose(A):
    print(column)
```

**執行結果**

```
[ 2  6 10 14]
[ 3  7 11 15]
[ 4  8 12 16]
[ 5  9 13 17]
```



#### 將多維矩陣進行展開變成一行的數組

```Python
import numpy as np

A = np.arange(2,18).reshape((4,4))
print(A)

print('Flatten: ', A.flatten())
print('Flatten: ', A.flat)

for item in A.flat:
    print(item)
```

**執行結果**

```
[[ 2  3  4  5]
 [ 6  7  8  9]
 [10 11 12 13]
 [14 15 16 17]]
Flatten:  [ 2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17]
Flatten:  <numpy.flatiter object at 0x0000028C54D32730>
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
```





## 2. NumPy Array 合併

課程資料來源: [8 numpy的 array 合并 (教学教程)](https://www.youtube.com/watch?v=ttSUtDTjDyI&list=PLXO45tsB95cKKyC45gatc8wEc3Ue7BlI4&index=8)



### 垂直合併 - np.vstack()

```Python
import numpy as np
## 創建數組
A = np.array([1,2,3])
B = np.array([4,5,6])

## 垂直合併
C = np.vstack((A,B))
print(C)
```

**執行結果**

```
[[1 2 3]
 [4 5 6]]
```



**數組形狀**

```Python
## 列印出合併後的形狀
print(A.shape, B.shape, C.shape)
```

**執行結果**

```
(3,) (3,) (2, 3)
```



### 水平合併 - np.hstack()

```Python
## 水平合併
D = np.hstack((A,B))
print(D)
print(A.shape, D.shape)
```

**執行結果**

```
[1 2 3 4 5 6]
(3,) (6,)
```



### 轉置 - np.newaxis()

```Python
print(A)
print(A.shape)

## 水平轉置
print(A[np.newaxis, :])
print(A[np.newaxis, :].shape)

## 垂直轉置
print(A[:, np.newaxis])
print(A[:, np.newaxis].shape)
```

**執行結果**

```
[1 2 3]
(3,)
[[1 2 3]]
(1, 3)
[[1]
 [2]
 [3]]
(3, 1)
```





**將A、B先轉置，再進行垂直合併和水平合併**

```Python
import numpy as np
## 創建數組，並轉成垂直
A = np.array([1,2,3])[:, np.newaxis]
B = np.array([4,5,6])[:, np.newaxis]

## 垂直合併
C = np.vstack((A,B))
## 水平合併
D = np.hstack((A,B))

print('A:')
print(A)
print('B:')
print(B)
print('C:')
print(C)
print('D:')
print(D)

print(A.shape, B.shape, C.shape, D.shape)
```

**執行結果**

```
A:
[[1]
 [2]
 [3]]
B:
[[4]
 [5]
 [6]]
C:
[[1]
 [2]
 [3]
 [4]
 [5]
 [6]]
D:
[[1 4]
 [2 5]
 [3 6]]
(3, 1) (3, 1) (6, 1) (3, 2)
```





### 多個矩陣合併 - np.concatenate()

```Python
## 多個數組合併

## 垂直合併
E = np.concatenate((A, B, A, B), axis = 0)
print(E)

## 水平合併
F = np.concatenate((A, B, A, B), axis = 1)
print(F)
```

**執行結果**

```
[[1]
 [2]
 [3]
 [4]
 [5]
 [6]
 [1]
 [2]
 [3]
 [4]
 [5]
 [6]]
[[1 4 1 4]
 [2 5 2 5]
 [3 6 3 6]]
```





