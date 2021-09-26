# Cupoy讀書會 - 公開課程讀書會筆記  - Python資料視覺化 - Matplotlib基本用法 - 設定坐標軸





哈囉，大家好!!由於小弟最近接到擔任舉辦讀書會的講師，而這個讀書會是根據莫凡Python公開課程所開設的，大家希望我可以帶他們看過莫凡Python的相關系列課程，所以讀書會這個系列主要是根據莫凡Python的公開系列課程講解和筆記，當然我也會額外找尋資料並補充給大家，也因為是根據公開課程的筆記，所以我都會明確記錄出處，如果有違反作者權力，麻煩告知，我會在第一時間立即刪除這系列的文章，感謝大家，當然也要特別感謝莫凡Python這麼厲害的公開課程，讓大家可以無痛初探Python的魔法世界!!



我是跟其他優秀的講師一起開設莫凡Python讀書會的，所以我不會每個章節都有筆記喔XD!!





## 1. 基本用法

公開課程內容來源: https://www.youtube.com/watch?v=4Y7f0znUT6E&list=PLXO45tsB95cKiBRXYqNNCw8AUo6tYen3l&index=3





### 繪製一條線

```	Python
#### 導入套件
import matplotlib.pyplot as plt
import numpy as np

## 構建數據
## 從-1到1，取50個點，會等分切割點
x = np.linspace(-1, 1, 100)
print(x)
y = 2 * x + 1
print(y)
## 視覺化
## 畫第一條線
plt.plot(x, y)
## 顯示圖像
plt.show()
```

**執行結果**

![image1](images\image1.PNG)



### 繪製兩條線在同一個圖片裡

```Python
## 構建數據
## 從-1到1，取50個點，會等分切割點
x = np.linspace(-1, 1, 100)
y = 2 * x + 1
## 視覺化
## 畫第一條線
plt.plot(x, y)
## 畫第二條線
plt.plot(y, x)
## 顯示圖像
plt.show()
```

**執行結果**

![image2](images\image2.PNG)



### 繪製一條線在兩張圖片裡

```Python
## 構建數據
## 從-1到1，取50個點，會等分切割點
x = np.linspace(-1, 1, 100)
y = 2 * x + 1
## 視覺化
## 畫第一條線
plt.figure()
plt.plot(x, y)
## 畫第二條線
plt.figure()
plt.plot(y, x)
## 顯示圖像
plt.show()
```

**執行結果**

![image3](images\image3.PNG)



### 繪製一條曲線

```Python
#### 導入套件
import matplotlib.pyplot as plt
import numpy as np

## 構建數據
## 從-1到1，取50個點，會等分切割點
x = np.linspace(-1, 1, 100)
print(x)
y = x ** 2
## 視覺化
## 畫第一條線
plt.plot(x, y)
## 顯示圖像
plt.show()
```

**執行結果**

![image4](images\image4.PNG)



### 使用Python編譯器，可以直接提供大家一些功能來操作圖片

功能

大家可以看到圖片的上方有各種功能鍵來幫助我們操作圖片，像是可以縮放圖片、調整圖片大小，調整x軸y軸大小範圍，存檔等等

```Python
>>> import matplotlib.pyplot as plt
>>> import numpy as np
>>> x = np.linspace(-1, 1, 100)
>>> y = x ** 2
>>> plt.plot(x, y)
[<matplotlib.lines.Line2D object at 0x00000255D897FE88>]
>>> plt.plot(y, x)
[<matplotlib.lines.Line2D object at 0x00000255D8999288>]
>>> plt.show()
```

**執行結果**

![image5](images\image5.png)





## 2. 使用Figure來繪製不同圖片

公開課程內容來源: https://www.youtube.com/watch?v=5IuawGiZ7_0&list=PLXO45tsB95cKiBRXYqNNCw8AUo6tYen3l&index=4



為了方便帶大家看出差異，這邊使用Python編譯器來執行



### 繪製兩張不同的圖片

```Python
>>> import matplotlib.pyplot as plt
>>> import numpy as np
>>> x = np.linspace(-1, 1, 100)
>>> y1 = 2 * x + 1
>>> y2 = x ** 2
>>> plt.figure()
<Figure size 640x480 with 0 Axes>
>>> plt.plot(x, y1)
[<matplotlib.lines.Line2D object at 0x000001B13E843448>]
>>> plt.figure()
<Figure size 640x480 with 0 Axes>
>>> plt.plot(x, y2)
[<matplotlib.lines.Line2D object at 0x000001B140DA4848>]
>>> plt.show()
```

**執行結果**

![image6](images\image6.PNG)

### 定義圖片的名稱

![image7](images\image7.PNG)



**執行結果:** 可以看出上面的Figure後面的數字變了，變成我們指定的2跟3



### 定義不同圖片的大小

```Python
>>> import matplotlib.pyplot as plt
>>> import numpy as np
>>> x = np.linspace(-1, 1, 100)
>>> y1 = 2 * x + 1
>>> y2 = x ** 2
>>> plt.figure(num = 2, figsize = (10, 10))
<Figure size 1000x1000 with 0 Axes>
>>> plt.plot(x, y1)
[<matplotlib.lines.Line2D object at 0x000002D06984A348>]
>>> plt.figure(num = 3)
<Figure size 640x480 with 0 Axes>
>>> plt.plot(x, y2)
[<matplotlib.lines.Line2D object at 0x000002D069F2C348>]
>>> plt.show()
```

**執行結果**

![image8](images\image8.PNG)





### 在其中一張圖中繪製兩條線，並調整其顏色、線的寬度、線的種類



補充: 線的種類https://matplotlib.org/stable/gallery/lines_bars_and_markers/linestyles.html

```Python
>>> import matplotlib.pyplot as plt
>>> import numpy as np
>>> x = np.linspace(-1, 1, 100)
>>> y1 = 2 * x + 1
>>> y2 = x ** 2
>>> plt.figure(num = 2, figsize = (10, 10))
<Figure size 1000x1000 with 0 Axes>
>>> plt.plot(x, y1)
[<matplotlib.lines.Line2D object at 0x0000019653BF7888>]
>>> plt.figure(num = 3)
<Figure size 640x480 with 0 Axes>
>>> plt.plot(x, y2)
[<matplotlib.lines.Line2D object at 0x00000196542DB588>]
>>> plt.plot(x, y1, color = 'red', linewidth = 2.8, linestyle = '--')
[<matplotlib.lines.Line2D object at 0x00000196542F7F88>]
>>> plt.show()
```

**執行結果**

![image9](images\image9.PNG)



## 3. 設定坐標軸

公開課程內容來源: https://www.youtube.com/watch?v=46EsDY8V6lQ&list=PLXO45tsB95cKiBRXYqNNCw8AUo6tYen3l&index=5





### 限制x軸與y軸的範圍

```Python
## 構建數據
## 從-1到1，取50個點，會等分切割點
x = np.linspace(-1, 1, 100)
y1 = 2 * x + 1
y2 = x ** 2
## 視覺化
plt.figure()
plt.plot(x, y2)
## 線的種類: https://matplotlib.org/stable/gallery/lines_bars_and_markers/linestyles.html
plt.plot(x, y1, color = 'red', linewidth = 2.8, linestyle = '--')

## 設定x軸和y軸的範圍空間
plt.xlim((-1, 2.5))
plt.ylim((-1, 1))

## 顯示圖像
plt.show()
```

**執行結果**

![image10](images\image10.PNG)



### 設定x軸與y軸標籤名稱

```Python
## 構建數據
## 從-1到1，取50個點，會等分切割點
x = np.linspace(-1, 1, 100)
y1 = 2 * x + 1
y2 = x ** 2
## 視覺化
plt.figure()
plt.plot(x, y2)
## 線的種類: https://matplotlib.org/stable/gallery/lines_bars_and_markers/linestyles.html
plt.plot(x, y1, color = 'red', linewidth = 2.8, linestyle = '--')

## 設定x軸和y軸的範圍空間
plt.xlim((-1, 2.5))
plt.ylim((-1, 1))

## 設定x軸與y軸標籤名稱
plt.xlabel('Here is X')
plt.ylabel('Here is Y')


## 顯示圖像
plt.show()
```

**執行結果**

![image11](images\image11.PNG)

### 改變刻度的數量與名稱

```Python
## 構建數據
## 從-1到1，取50個點，會等分切割點
x = np.linspace(-1, 1, 100)
y1 = 2 * x + 1
y2 = x ** 2
## 視覺化
plt.figure()
plt.plot(x, y2)
plt.plot(x, y1, color = 'red', linewidth = 2.8, linestyle = '--')

## 設定x軸和y軸的範圍空間
plt.xlim((-1, 2.5))
plt.ylim((-1, 1))

## 設定x軸與y軸標籤名稱
plt.xlabel('Here is X')
plt.ylabel('Here is Y')

## 改店x軸刻度
new_xticks = np.linspace(-1, 2.5, 5)
print(new_xticks)
plt.xticks(new_xticks)
## 改變y軸刻度
plt.yticks([-1, 0, 0.5, 1, 1.5],
          ['really bad', 'bad', 'normal', 'good', 'really good'])


## 顯示圖像
plt.show()
```

**執行結果**

![image10](images\image12.PNG)



讓字體好看

```Python
## 構建數據
## 從-1到1，取50個點，會等分切割點
x = np.linspace(-1, 1, 100)
y1 = 2 * x + 1
y2 = x ** 2
## 視覺化
plt.figure()
plt.plot(x, y2)
plt.plot(x, y1, color = 'red', linewidth = 2.8, linestyle = '--')

## 設定x軸和y軸的範圍空間
plt.xlim((-1, 2.5))
plt.ylim((-1, 1))

## 設定x軸與y軸標籤名稱
plt.xlabel('Here is X')
plt.ylabel('Here is Y')

## 改店x軸刻度
new_xticks = np.linspace(-1, 2.5, 5)
plt.xticks(new_xticks)
## 改變y軸刻度
plt.yticks([-1, 0, 0.5, 1, 1.5],
          [r'$really\ bad$', r'$bad$', r'$normal$', r'$good$', r'$really\ good$'])


## 顯示圖像
plt.show()
```

**執行結果**

![image11](images\image13.PNG)



### 將特殊符號帶入標籤名稱

**將數學形式的Alpha放入刻度標籤名稱**

```Python
## 構建數據
## 從-1到1，取50個點，會等分切割點
x = np.linspace(-1, 1, 100)
y1 = 2 * x + 1
y2 = x ** 2
## 視覺化
plt.figure()
plt.plot(x, y2)
plt.plot(x, y1, color = 'red', linewidth = 2.8, linestyle = '--')

## 設定x軸和y軸的範圍空間
plt.xlim((-1, 2.5))
plt.ylim((-1, 1))

## 設定x軸與y軸標籤名稱
plt.xlabel('Here is X')
plt.ylabel('Here is Y')

## 改店x軸刻度
new_xticks = np.linspace(-1, 2.5, 5)
plt.xticks(new_xticks)
## 改變y軸刻度
plt.yticks([-1, 0, 0.5, 1, 1.5],
          [r'$really\ bad$', r'$bad$', r'$normal$', r'$good\ \alpha$', r'$really\ good$'])


## 顯示圖像
plt.show()
```

**執行結果**

![image14](images\image14.PNG)



公開課程內容來源: https://www.youtube.com/watch?v=w83mFG5tyW4&list=PLXO45tsB95cKiBRXYqNNCw8AUo6tYen3l&index=6



### 修改坐標軸的位置

使用gca - get current axis

```Python
## 構建數據
## 從-1到1，取50個點，會等分切割點
x = np.linspace(-1, 1, 100)
y1 = 2 * x + 1
y2 = x ** 2
## 視覺化
plt.figure()
plt.plot(x, y2)
plt.plot(x, y1, color = 'red', linewidth = 2.8, linestyle = '--')

## 設定x軸和y軸的範圍空間
plt.xlim((-1, 2.5))
plt.ylim((-1, 1))

## 設定x軸與y軸標籤名稱
plt.xlabel('Here is X')
plt.ylabel('Here is Y')

## 改店x軸刻度
new_xticks = np.linspace(-1, 2.5, 5)
plt.xticks(new_xticks)
## 改變y軸刻度
plt.yticks([-1, 0, 0.5, 1, 1.5],
          [r'$really\ bad$', r'$bad$', r'$normal$', r'$good\ \alpha$', r'$really\ good$'])

## 修改坐標軸位置
ax = plt.gca()
## 指定脊梁 - 就是原本圖軸的四個邊框
## 將右邊和上面的軸設置為不顯示
ax.spines['right'].set_color('none')
ax.spines['top'].set_color('none')

## 用下面的軸代替x的座標軸
ax.xaxis.set_ticks_position('bottom')
## 用左邊的軸代替y的座標軸
ax.yaxis.set_ticks_position('left')
## 移動x軸與y軸位置
## 設定橫坐標的位置會在縱座標y的0值位置
ax.spines['bottom'].set_position(('data', 0))
## 除了data也可以設定axes或outward來移動座標軸
## axes會用百分比的方式來移動，像是要移動的距離為y軸百分之幾的位置
## 設定縱坐標的位置會在橫座標y的0值位置
ax.spines['left'].set_position(('data', 0))

## 顯示圖像
plt.show()
```

**執行結果**

![image15](images\image15.PNG)





## Reference

https://www.youtube.com/watch?v=4Y7f0znUT6E&list=PLXO45tsB95cKiBRXYqNNCw8AUo6tYen3l&index=3

https://www.youtube.com/watch?v=5IuawGiZ7_0&list=PLXO45tsB95cKiBRXYqNNCw8AUo6tYen3l&index=4

https://matplotlib.org/stable/gallery/lines_bars_and_markers/linestyles.html





