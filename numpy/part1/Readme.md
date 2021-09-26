# Cupoy讀書會 - 公開課程讀書會筆記 - NumPy介紹 - NumPy屬性 - 創建數組Array



哈囉，大家好!!由於小弟最近接到擔任舉辦讀書會的講師，而這個讀書會是根據莫凡Python公開課程所開設的，大家希望我可以帶他們看過莫凡Python的相關系列課程，所以讀書會這個系列主要是根據莫凡Python的公開系列課程講解和筆記，當然我也會額外找尋資料並補充給大家，也因為是根據公開課程的筆記，所以我都會明確記錄出處，如果有違反作者權力，麻煩告知，我會在第一時間立即刪除這系列的文章，感謝大家，當然也要特別感謝莫凡Python這麼厲害的公開課程，讓大家可以無痛初探Python的魔法世界!!



我是跟其他優秀的講師一起開設莫凡Python讀書會的，所以我不會每個章節都有筆記喔XD!!



## 1. NumPy與Pandas介紹

課程資料來源: [1 numpy & pandas 有什么用? (教学教程)](https://www.youtube.com/watch?v=To3YL92HZyc&list=PLXO45tsB95cKKyC45gatc8wEc3Ue7BlI4)



## 應用的地方

+ Data Analysis 數據分析
+ Machine Learning 機器學習
+ Deep Learning 深度學習

當然有相當多的實務應用上都會使用它們，像是數據前處理、數據視覺化等等，都會透過它們來將資料進行一個清理與計算



### 補充: **NumPy是什麼？** 

- **說明**：Numerical Python(數值Python)的縮寫，它提供了強大的接口，讓我們存儲和操作密集的數據緩衝區（dense data buffers）
- Python關聯：NumPy的數組像是Python內建的列表（list）型態，但是NumPy數組在儲存和操作大量數據時，提供了比Python本身更好的效能
- **重要性**：NumPy數組接近是整個Python數據科學領域工具鏈的核心，許多我們所使用的數據分析與處理套件都是以它為基礎構建的

###  

### 為什麼要使用NumPy和Pandas?

+ 它所消耗的電腦資源相當少: 因為它採用矩陣運算，所以會比Python原生自帶的字典Dictionary和列表快非常多
+ 運算速度非常快: 由於NumPy和Pandas都是採用C語言來撰寫的，而Pandas是基於NumPy所開發的，所以算是NumPy的升級版本



### 補充: **為什麼NumPy的數組進行計算操作時是非常快的?**

計算NumPy的數組可以是非常快,也可以是非常慢的,然而快的原因:

- 向量化的操作
- 都是透過 NumPy 的通用函式(ufuncs : Universal Functions)來實現的

例如: 我們今天要拿兩個矩陣進行計算，如果都用Python字典Dictionary或是列表一個一個相加就會比較慢，如果使用NumPy的向量化操作就會快非常多

![image1](images\image1.png)





## 2. NumPy屬性

課程資料來源: [3 numpy 属性 (教学教程)](https://www.youtube.com/watch?v=mf7ktBLwaJs&list=PLXO45tsB95cKKyC45gatc8wEc3Ue7BlI4&index=3)





### 導入NumPy套件

```Python
## 導入NumPy套件
import numpy as np
```



### 將列表轉換為矩陣

```Python
## 將列表轉化為矩陣
array = np.array([[2,4,6],
                  [3,7,9],
                  [1,3,8]])
array
```

**執行結果**

```
array([[2, 4, 6],
       [3, 7, 9],
       [1, 3, 8]])
```



### 數組的屬性 - 維度、形狀、大小

```Python
## 數組維度
print('number of dim: ', array.ndim)

## 數組的形狀 - 行數核列數
print('array shape: ', array.shape)

## 數組的大小 - 元素個數
print('size: ', array.size)
```

**執行結果**

```
number of dim:  2
array shape:  (3, 3)
size:  9
```



## 3. NumPy創建數組Array

課程資料來源: [4 numpy 的创建 array (教学教程)](https://www.youtube.com/watch?v=2TkMujKoDPI&list=PLXO45tsB95cKKyC45gatc8wEc3Ue7BlI4&index=4)



### 簡單創建一個數組

```Python
## 創建一個數組
a = np.array([2,6,8])
print(a)
```

**執行結果**

```
[2 6 8]
```



### 指定創建數組的數據類型

**整數**

```Python
## 指定創建數組的數據類型
a = np.array([2,6,8], dtype = np.int)
print(a.dtype)

a = np.array([2,6,8], dtype = np.int64)
print(a.dtype)
```

**執行結果**

```
int32
int64
```



**浮點數**

```Python
## 指定創建數組的數據類型
a = np.array([2,6,8], dtype = np.float)
print(a.dtype)

a = np.array([2,6,8], dtype = np.float32)
print(a.dtype)
```

**執行結果**

```
float64
float32
```



### 創建特定的數組



創建各類型數組的方法

+ array: 創建數組
+ dtype: 數據類型 
+ zeros: 創建全為0的數組
+ ones: 創建全為1的數組
+ empty: 創建接近0的數組
+ arange: 指定創建數組裡面的數據範圍值
+ linspace: 構建線段的數據值
+ reshape: 改變數組形狀



**array**

```Python
## 創建數組
a = np.array([[1,2,3],[4,5,6]])
print(a)
```

**執行結果**

```
[[1 2 3]
 [4 5 6]]
```



**zeros**

```Python
## 創建值全為0的5行6列數組
a = np.zeros((5,6))
print(a)
```

**執行結果**

```
[[0. 0. 0. 0. 0. 0.]
 [0. 0. 0. 0. 0. 0.]
 [0. 0. 0. 0. 0. 0.]
 [0. 0. 0. 0. 0. 0.]
 [0. 0. 0. 0. 0. 0.]]
```



**ones**

```Python
## 創建值全為1的5行6列數組
a = np.ones((5,6))
print(a)
```

**執行結果**

```
[[1. 1. 1. 1. 1. 1.]
 [1. 1. 1. 1. 1. 1.]
 [1. 1. 1. 1. 1. 1.]
 [1. 1. 1. 1. 1. 1.]
 [1. 1. 1. 1. 1. 1.]]
```



ones +　指定dtype

```Python
## 創建值全為1的5行6列數組，指定數據類型為int
a = np.ones((5,6), dtype = np.int)
print(a)
print(a.dtype)
```

**執行結果**

```
[[1 1 1 1 1 1]
 [1 1 1 1 1 1]
 [1 1 1 1 1 1]
 [1 1 1 1 1 1]
 [1 1 1 1 1 1]]
int32
```



**empty**

```Python
## 創建一個全空，但每個元素值都接近於0的數組
a = np.empty((4,5))
print(a)

## 創建一個全空，但每個元素值都接近於0的數組，並指定數據類型為int
b = np.empty((4,5), dtype = np.int)
print(b)
```

**執行結果**

```
[[6.23042070e-307 4.67296746e-307 1.69121096e-306 9.34609111e-307
  1.33511018e-306]
 [1.33511969e-306 6.23037996e-307 6.23053954e-307 9.34609790e-307
  8.45593934e-307]
 [9.34600963e-307 3.56036603e-307 1.37961641e-306 1.37961302e-306
  1.11259940e-306]
 [1.60219035e-306 1.11261570e-306 1.06811354e-306 8.34448533e-308
  1.21347091e+295]]
[[ -13901544        605         45          0          0]
 [         0          0          0          0 1819042080]
 [1634607739  975332717 1685353250  578057583 1702109740]
 [ 975336568 1869375010  875983969 1818652252  863265135]]
```



**arange**

```Python
## 創建一個指定範圍的數組: 0~60，中間隔5的值
a = np.arange(0,60,5)
print(a)
```

**執行結果**

```
[ 0  5 10 15 20 25 30 35 40 45 50 55]
```



**linspace**

```Python
## 創建線段行數據 - 1~20之間切10個點
a = np.linspace(1,20,10)
print(a)
```

**執行結果**

```
[ 1.          3.11111111  5.22222222  7.33333333  9.44444444 11.55555556
 13.66666667 15.77777778 17.88888889 20.        ]
```



**reshape**

```Python
## 改變數組形狀
a = np.linspace(1,20,10).reshape((5,2))
print(a)
```

**執行結果**

```
[[ 1.          3.11111111]
 [ 5.22222222  7.33333333]
 [ 9.44444444 11.55555556]
 [13.66666667 15.77777778]
 [17.88888889 20.        ]]
```





## 4. 補充閱讀

NumPy的屬性與操作

[NumPy 的各種用法 - 讀書筆記 - Python Data Science Handbook - Python數據科學 - NumPy Array的屬性與操作(串聯與切割 - Concatenate、hstack、vstack、split、vsplit、 hsplit) - NumPy Array的各種計算方法 - UFuncs - #6](https://matters.news/@CHWang/num-py-%E7%9A%84%E5%90%84%E7%A8%AE%E7%94%A8%E6%B3%95-%E8%AE%80%E6%9B%B8%E7%AD%86%E8%A8%98-python-data-science-handbook-python%E6%95%B8%E6%93%9A%E7%A7%91%E5%AD%B8-num-py-array%E7%9A%84%E5%B1%AC%E6%80%A7%E8%88%87%E6%93%8D%E4%BD%9C-%E4%B8%B2%E8%81%AF%E8%88%87%E5%88%87%E5%89%B2-concatenate-hstack-vstack-split-vsplit-hsplit-num-py-array%E7%9A%84%E5%90%84%E7%A8%AE%E8%A8%88%E7%AE%97%E6%96%B9%E6%B3%95-u-funcs-6-bafyreidaizcujqdrcqxeznz42op2jnbl2nhuzt7hujv47lhfpjtisw72qq)





