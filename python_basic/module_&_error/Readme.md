# Cupoy讀書會 - 公開課程讀書會筆記 - Python模塊安裝、刪除、搜尋、更新、導入 - 如何撰寫模塊? - 如何導入自己撰寫的模塊? - 例外處理Try Except



哈囉，大家好!!由於小弟最近接到擔任舉辦讀書會的講師，而這個讀書會是根據莫凡Python公開課程所開設的，大家希望我可以帶他們看過莫凡Python的相關系列課程，所以讀書會這個系列主要是根據莫凡Python的公開系列課程講解和筆記，當然我也會額外找尋資料並補充給大家，也因為是根據公開課程的筆記，所以我都會明確記錄出處，如果有違反作者權力，麻煩告知，我會在第一時間立即刪除這系列的文章，感謝大家，當然也要特別感謝莫凡Python這麼厲害的公開課程，讓大家可以無痛初探Python的魔法世界!!



我是跟其他優秀的講師一起開設莫凡Python讀書會的，所以我不會每個章節都有筆記喔XD!!





## 1. 安裝、刪除，搜尋模塊

讀書會課程內容來源: https://www.youtube.com/watch?v=D0-8urP2b5Y&list=PLXO45tsB95cIRP5gCi8AlYwQ1uFO2aQBw&index=14

這邊我們以Pandas為例



### 安裝模塊

使用pip來安裝

筆記: 如果使用Python3以上的版本，已經擁有pip，而Python3以下的版本，需要另行安裝pip

+ pip: 預設為使用Python2安裝

+ pip3: 預設為使用Python3安裝

```Python
(base) C:\Users\user\Desktop\book_club\python_basic\module>pip3 install pandas
Collecting pandas
  Downloading pandas-1.3.3-cp37-cp37m-win_amd64.whl (10.0 MB)
     |████████████████████████████████| 10.0 MB 3.3 MB/s
Requirement already satisfied: python-dateutil>=2.7.3 in c:\users\user\anaconda3\lib\site-packages (from pandas) (2.8.1)
Requirement already satisfied: pytz>=2017.3 in c:\users\user\anaconda3\lib\site-packages (from pandas) (2019.3)
Requirement already satisfied: numpy>=1.17.3 in c:\users\user\anaconda3\lib\site-packages (from pandas) (1.18.1)
Requirement already satisfied: six>=1.5 in c:\users\user\anaconda3\lib\site-packages (from python-dateutil>=2.7.3->pandas) (1.14.0)
Installing collected packages: pandas
ERROR: pip's dependency resolver does not currently take into account all the packages that are installed. This behaviour is the source of the following dependency conflicts.
phik 0.11.2 requires scipy>=1.5.2, but you have scipy 1.4.1 which is incompatible.
Successfully installed pandas-1.3.3
```

預設的情況它會安裝最新的版本

我們也可以透過指定版本的方式來進行安裝，我可以從這邊看有哪些版本可以安裝:https://pandas.pydata.org/

+ 我們來安裝pandas1.2.5

```Python
(base) C:\Users\user\Desktop\book_club\python_basic\module>pip3 install pandas==1.2.5
Collecting pandas==1.2.5
  Downloading pandas-1.2.5-cp37-cp37m-win_amd64.whl (9.1 MB)
     |████████████████████████████████| 9.1 MB 6.4 MB/s
Requirement already satisfied: numpy>=1.16.5 in c:\users\user\anaconda3\lib\site-packages (from pandas==1.2.5) (1.18.1)
Requirement already satisfied: pytz>=2017.3 in c:\users\user\anaconda3\lib\site-packages (from pandas==1.2.5) (2019.3)
Requirement already satisfied: python-dateutil>=2.7.3 in c:\users\user\anaconda3\lib\site-packages (from pandas==1.2.5) (2.8.1)
Requirement already satisfied: six>=1.5 in c:\users\user\anaconda3\lib\site-packages (from python-dateutil>=2.7.3->pandas==1.2.5) (1.14.0)
Installing collected packages: pandas
ERROR: pip's dependency resolver does not currently take into account all the packages that are installed. This behaviour is the source of the following dependency conflicts.
phik 0.11.2 requires scipy>=1.5.2, but you have scipy 1.4.1 which is incompatible.
Successfully installed pandas-1.2.5
```

結果: 就會看到成功安裝Pandas 1.2.5版本







### 刪除模塊

+ pip3 uninstall `Package Name`

```Python
(base) C:\Users\user\Desktop\book_club\python_basic\module>pip3 uninstall pandas
Found existing installation: pandas 1.3.3
Uninstalling pandas-1.3.3:
  Would remove:
    c:\users\user\anaconda3\lib\site-packages\pandas-1.3.3.dist-info\*
    c:\users\user\anaconda3\lib\site-packages\pandas\*
Proceed (Y/n)? y
  Successfully uninstalled pandas-1.3.3
```





### 搜尋模塊

這邊大家可能會發現pip search `Package Name`已經不能用了，那我們要用什麼來搜尋模塊呢?

我這邊提供pip show `Package Name`的方法給大家

```Python
(base) C:\Users\user\Desktop\book_club\python_basic\module>pip3 show pandas
Name: pandas
Version: 1.3.3
Summary: Powerful data structures for data analysis, time series, and statistics
Home-page: https://pandas.pydata.org
Author: The Pandas Development Team
Author-email: pandas-dev@python.org
License: BSD-3-Clause
Location: c:\users\user\anaconda3\lib\site-packages
Requires: python-dateutil, numpy, pytz
Required-by: visions, statsmodels, seaborn, phik, pandas-profiling, mlxtend
```

**結果: 它會印出numpy的所有資訊，像是版本、License、作者等等**

超好用對吧!!



### 更新模塊

pip3 install -U `Package Name`

```Python
(base) C:\Users\user\Desktop\book_club\python_basic\module>pip3 install -U pandas
Requirement already satisfied: pandas in c:\users\user\anaconda3\lib\site-packages (1.2.5)
Collecting pandas
  Using cached pandas-1.3.3-cp37-cp37m-win_amd64.whl (10.0 MB)
Requirement already satisfied: python-dateutil>=2.7.3 in c:\users\user\anaconda3\lib\site-packages (from pandas) (2.8.1)
Requirement already satisfied: numpy>=1.17.3 in c:\users\user\anaconda3\lib\site-packages (from pandas) (1.18.1)
Requirement already satisfied: pytz>=2017.3 in c:\users\user\anaconda3\lib\site-packages (from pandas) (2019.3)
Requirement already satisfied: six>=1.5 in c:\users\user\anaconda3\lib\site-packages (from python-dateutil>=2.7.3->pandas) (1.14.0)
Installing collected packages: pandas
  Attempting uninstall: pandas
    Found existing installation: pandas 1.2.5
    Uninstalling pandas-1.2.5:
      Successfully uninstalled pandas-1.2.5
ERROR: pip's dependency resolver does not currently take into account all the packages that are installed. This behaviour is the source of the following dependency conflicts.
phik 0.11.2 requires scipy>=1.5.2, but you have scipy 1.4.1 which is incompatible.
Successfully installed pandas-1.3.3
```

**結果: 它就會將我們原本安裝的版本移除掉，然後安裝最新的模塊版本**



### 補充: 如果把模塊刪掉了，還可以使用更新的方式下載最新的模塊嗎?

答案: 可以!!

```Python
(base) C:\Users\user\Desktop\book_club\python_basic\module>pip3 uninstall pandas
Found existing installation: pandas 1.3.3
Uninstalling pandas-1.3.3:
  Would remove:
    c:\users\user\anaconda3\lib\site-packages\pandas-1.3.3.dist-info\*
    c:\users\user\anaconda3\lib\site-packages\pandas\*
Proceed (Y/n)? y
  Successfully uninstalled pandas-1.3.3

(base) C:\Users\user\Desktop\book_club\python_basic\module>pip3 install -U pandas
Collecting pandas
  Using cached pandas-1.3.3-cp37-cp37m-win_amd64.whl (10.0 MB)
Requirement already satisfied: numpy>=1.17.3 in c:\users\user\anaconda3\lib\site-packages (from pandas) (1.18.1)
Requirement already satisfied: python-dateutil>=2.7.3 in c:\users\user\anaconda3\lib\site-packages (from pandas) (2.8.1)
Requirement already satisfied: pytz>=2017.3 in c:\users\user\anaconda3\lib\site-packages (from pandas) (2019.3)
Requirement already satisfied: six>=1.5 in c:\users\user\anaconda3\lib\site-packages (from python-dateutil>=2.7.3->pandas) (1.14.0)
Installing collected packages: pandas
ERROR: pip's dependency resolver does not currently take into account all the packages that are installed. This behaviour is the source of the following dependency conflicts.
phik 0.11.2 requires scipy>=1.5.2, but you have scipy 1.4.1 which is incompatible.
Successfully installed pandas-1.3.3
```

我先刪除Pandas，再用更新指令來更新Pandas，發現它直接幫我下載最新版本的Pandas了



## 2. 導入模塊

讀書會課程內容來源: https://www.youtube.com/watch?v=K5azzbPxV5M&list=PLXO45tsB95cIRP5gCi8AlYwQ1uFO2aQBw&index=25





### 第一種方法

導入time模塊

```Python
## 導入time模塊
import time
print(time.localtime())
```

**執行結果**

```
time.struct_time(tm_year=2021, tm_mon=9, tm_mday=13, tm_hour=12, tm_min=2, tm_sec=56, tm_wday=0, tm_yday=256, tm_isdst=0)
```



### 第二種方法: 縮短應用模塊的名稱

```Python
## 導入time模塊，並使用t來替換time的名稱
import time as t
print(t.localtime())
```

**執行結果**

```
time.struct_time(tm_year=2021, tm_mon=9, tm_mday=13, tm_hour=12, tm_min=4, tm_sec=26, tm_wday=0, tm_yday=256, tm_isdst=0)
```



### 第三種方法: 只想導入模塊中的某些屬性功能，不用全部都導入

我們這邊只想導入time裡面的time跟localtime屬性功能

```Python
## 導入time模塊，並只想導入模塊中的某些屬性功能，不用全部都導入 - time、localtime
from time import time,localtime
print(localtime())  ## time.localtime()
print(time())  ## tiem.time()
```

**執行結果**

```
time.struct_time(tm_year=2021, tm_mon=9, tm_mday=13, tm_hour=12, tm_min=8, tm_sec=23, tm_wday=0, tm_yday=256, tm_isdst=0)
1631506103.717853
```



### 第四種方法: 導入所有模塊中的屬性功能

導入time模塊中的所有屬性功能

```Python
## 導入time模塊，並導入所有模塊中的屬性功能
from time import *
print(localtime())
print(time())
```

**執行結果**

```
time.struct_time(tm_year=2021, tm_mon=9, tm_mday=13, tm_hour=12, tm_min=10, tm_sec=38, tm_wday=0, tm_yday=256, tm_isdst=0)
1631506238.8118517
```



## 3. 創建自己的模塊(腳本)，並導入應用

讀書會課程內容來源: https://www.youtube.com/watch?v=oYheNUtZpFw&list=PLXO45tsB95cIRP5gCi8AlYwQ1uFO2aQBw&index=26



撰寫一個自己的Python Script - myscript.py

```Python
def print_text(content):
    print(content)
    
def add(a, b):
    return a + b

def greeting(person):
    print('Welcome ', person)
```



在其他Python檔中導入自己剛剛創建的模塊

```Python
## 導入自己的模塊 - myscript.py
import myscript as m
## 使用myscript中的add屬性功能
print(m.add(6, 8))
## 使用myscript中的print_text屬性功能
m.print_text('Hello!!')
## 用myscript中的Agreeting功能
m.greeting('Jack')
```

**執行結果**

```
14
Hello!!
Welcome  Jack
```





## 另一種載入自己模塊的方法

通常我們會將自己寫的模塊放在要使用它的Python檔案旁邊，一定要這樣放嗎?我們導入那麼多使用pip安裝的模塊也沒有放在旁邊啊，這時候我們可以把它放進Anaconda存放模塊的位置，這樣就一樣可以導入，而且不用放在旁邊囉



**檢查在電腦中Anaconda將Python模塊放在哪裡?**

這邊會有所有我在Anaconda中下載的所有Python模塊

![image1](images\image1.PNG)



把我們剛剛寫好的Python模塊放入，然後重新執行一次剛剛的Python

```Python
## 導入自己的模塊 - myscript.py
import myscript as m
## 使用myscript中的add屬性功能
print(m.add(6, 8))
## 使用myscript中的print_text屬性功能
m.print_text('Hello!!')
## 用myscript中的Agreeting功能
m.greeting('Jack')
```

**執行結果**

```
14
Hello!!
Welcome  Jack
```



發現一樣能夠導入我們自己創建的模塊!!



## 4. 例外處理 Try Except



讀書會課程內容來源: https://www.youtube.com/watch?v=hpQz-0q5uGY&list=PLXO45tsB95cIRP5gCi8AlYwQ1uFO2aQBw&index=28



### 當錯誤發生

**打開一個不存在的檔案**

```Python
## 打開一個不存在的檔案
file = open('aaa.txt', 'r')
```

執行結果: 會報錯說沒有這個檔案

```
---------------------------------------------------------------------------
FileNotFoundError                         Traceback (most recent call last)
<ipython-input-2-0082e98b9cac> in <module>
      1 ## 打開一個不存在的檔案
----> 2 file = open('aaa.txt', 'r')

FileNotFoundError: [Errno 2] No such file or directory: 'aaa.txt'
```





**使用錯誤處理來印出錯誤資訊**

```Python
## 使用錯誤處理來印出錯誤資訊
try:
    file = open('aaa.txt', 'r')
except Exception as e:
    print(e)
```

**執行結果**

```
[Errno 2] No such file or directory: 'aaa.txt'
```



那這邊因為我們知道錯誤的原因是文件根本不存在，所以為了讓使用者能夠更快了解錯誤原因，我們自己寫下錯誤原因，並在錯誤出現時印出給使用者看

```Python
## 使用錯誤處理來印出錯誤資訊
try:
    file = open('aaa.txt', 'r')
except Exception as e:
    print('Sorry We cannot find the file you set in your compuiter')
```

**執行結果**

```
Sorry We cannot find the file you set in your compuiter
```



這邊我們想設計一個方法是使用者知道自己沒有這個文件後，會詢問他是否要幫他自動創建這個文件

```Python
## 使用錯誤處理來印出錯誤資訊
file_name = 'aaa.txt'
try:
    file = open(file_name, 'r')
except Exception as e:
    print('Sorry We cannot find the file you set in your compuiter')
    r = input('Do you want to create a new file: (y/n)')
    if r == 'y':
        file = open(file_name, 'w')
        print(file_name +' has been created')
    else:
        pass
```

**執行結果**: 當我希望系統自動幫我創建

```Python
Sorry We cannot find the file you set in your compuiter
Do you want to create a new file: (y/n)y
aaa.txt has been created
```



### 當執行成功

現在的情況是當沒有錯誤發生時，我們希望執行的步驟

+　使用else

```Python
## 使用錯誤處理來印出錯誤資訊
file_name = 'aaa.txt'
try:
    file = open(file_name, 'r+')
except Exception as e:
    print('Sorry We cannot find the file you set in your compuiter')
    r = input('Do you want to create a new file: (y/n)')
    if r == 'y':
        file = open(file_name, 'w')
        print(file_name +' has been created')
    else:
        pass
else:
    file.write('Successful!!')
    print('Open Successfully')
file.close()
```

**執行結果**

```
Open Successfully
```

![image2](images\image2.PNG)







補充教材: https://chwang12341.medium.com/%E7%B5%A6%E8%87%AA%E5%B7%B1%E7%9A%84python%E5%B0%8F%E7%AD%86%E8%A8%98-debug%E8%88%87%E6%B8%AC%E8%A9%A6%E5%A5%BD%E5%B9%AB%E6%89%8B-%E5%98%97%E8%A9%A6try-except%E8%88%87%E4%B8%BB%E5%8B%95%E5%BC%95%E7%99%BCraise%E8%88%87assert-%E7%A8%8B%E5%BC%8F%E7%95%B0%E5%B8%B8%E8%99%95%E7%90%86-c2bc2e3e4e13









## Reference

https://www.youtube.com/watch?v=D0-8urP2b5Y&list=PLXO45tsB95cIRP5gCi8AlYwQ1uFO2aQBw&index=14

https://www.youtube.com/watch?v=K5azzbPxV5M&list=PLXO45tsB95cIRP5gCi8AlYwQ1uFO2aQBw&index=25

https://www.youtube.com/watch?v=oYheNUtZpFw&list=PLXO45tsB95cIRP5gCi8AlYwQ1uFO2aQBw&index=26

https://www.youtube.com/watch?v=hpQz-0q5uGY&list=PLXO45tsB95cIRP5gCi8AlYwQ1uFO2aQBw&index=28



















