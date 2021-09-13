# Cupoy讀書會 - 公開課程讀書會筆記 - Python文件讀寫



哈囉，大家好!!由於小弟最近接到擔任舉辦讀書會的講師，而這個讀書會是根據莫凡Python公開課程所開設的，大家希望我可以帶他們看過莫凡Python的相關系列課程，所以讀書會這個系列主要是根據莫凡Python的公開系列課程講解和筆記，當然我也會額外找尋資料並補充給大家，也因為是根據公開課程的筆記，所以我都會明確記錄出處，如果有違反作者權力，麻煩告知，我會在第一時間立即刪除這系列的文章，感謝大家，當然也要特別感謝莫凡Python這麼厲害的公開課程，讓大家可以無痛初探Python的魔法世界!!



我是跟其他優秀的講師一起開設莫凡Python讀書會的，所以我不會每個章節都有筆記喔XD!!



## 1. Python #15
讀書會內容來源: https://www.youtube.com/watch?v=hkMQaooXkgs&list=PLXO45tsB95cIRP5gCi8AlYwQ1uFO2aQBw&index=15



### 撰寫文件內容

+ 撰寫文件內容

```Python
## 撰寫內容
## \n空行
context = 'This is my first test.\nThis is next line.\nThis is last line'
print(context)
```

**執行結果**

```
This is my first test.
This is next line.
This is last line
```





### 補充 - 更多轉義字幅運用

+ \t tab鍵

```Python
context1 = 'This is my first test.\tThis is next line.\tThis is last line'
print(context1)
```

**執行結果**

```
This is my first test.	This is next line.	This is last line
```

轉義字符可以參考: https://blog.csdn.net/XuFangfang5206/article/details/80030300



### 寫進文件

```Python
## 打開文件(創建文件)
## w: write
## r: read
file = open('first_file.txt', 'w')
## 寫入文件
file.write(context)
## 關閉文件
file.close()
```

**執行結果**: 會產生一個first_file文件，打開後如下圖內容

![image1](images\image1.PNG)

### 補充

**不同模式的開啟文件**

https://www.runoob.com/python/python-func-open.html

```Python
## r+和w+一樣都是讀寫文件，但是如果檔案不存在r+會報錯，w+會創建文件
## 寫進檔案
f = open('test.txt', 'w+')
f.write('Hello Everyone')
## 寫進檔案
f = open('test.txt', 'r+')
f.write('Hi Everybody\n')
## 累加文件
f = open('test.txt', 'a+')
f.write('Welcome')
f.close()
```

**執行結果: 可以看到前面寫進文件的時候，第一次的寫入被第二次覆蓋掉了，第三次才會累加上去**

![image2](images\image2.PNG)

## 2. Python #16

讀書會內容來源: https://www.youtube.com/watch?v=TBemVnOITjk&list=PLXO45tsB95cIRP5gCi8AlYwQ1uFO2aQBw&index=16



### 追加文字

```Python
## 追加文字
append_context = '\nThis is appended file.'
## 追加方式打開文件
file = open('first_file.txt', 'a')
file.write(append_context)
file.close()
```

**執行結果**: 可以看到，我們在原本的first_file文件中添加了一行文字 - This is appended file.

![image3](images\image3.PNG)



## 3. Python 17
讀書會內容來源: https://www.youtube.com/watch?v=pz3I-9MgxGo&list=PLXO45tsB95cIRP5gCi8AlYwQ1uFO2aQBw&index=17



### 讀取文件 - 整個

```Python
## 讀取文件
file = open('first_file.txt', 'r')
## 全部讀取
content = file.read()
print(content)
file.close()
```

**執行結果**

```
This is my first test.
This is next line.
This is last line
This is appended file.
```



### 讀取文件 - 一行

```Python
file = open('first_file.txt', 'r')
## 讀取一行
content1 = file.readline()
print(content1)
file.close()
```

**執行結果**

```
This is my first test.
```



### 讀取文件 - 一行一行寫進Python List裡面

```Python
file = open('first_file.txt', 'r')
## 一行一行讀取
content1 = file.readlines()
print(content1)
file.close()
```

**執行結果: 會用list的型態，將一行一行的內容存成list傳回**

```
['This is my first test.\n', 'This is next line.\n', 'This is last line\n', 'This is appended file.']
```



## 補充: 使用list資料寫進檔案[¶](http://localhost:8888/notebooks/read_write_file_1.ipynb#補充:-使用list資料寫進檔案)

讀書會內容來源: https://shengyu7697.github.io/python-write-text-file/

```Python
context = ['Welcome\n', 'Hello\t', '123456789']
f = open('test1.txt', 'w')
f.writelines(context)
f.close()
```

**執行結果**

![image4](images\image4.PNG)



## 補充: 使用print()的方式寫進檔案

```Python
f = open('test2.txt', 'w')
print('Welcome', file = f)
print('Hello', file = f)
print('123456789', file = f)
f.close()
```

**執行結果**

![image5](images\image5.PNG)



## 補充: 使用open as的方法來讀寫文件

```Python
with open('test3.txt', 'a') as f:
    f.write('Welcome\n')
```

**執行結果**

![image6](images\image6.PNG)





## Reference

https://www.youtube.com/watch?v=hkMQaooXkgs&list=PLXO45tsB95cIRP5gCi8AlYwQ1uFO2aQBw&index=15

https://blog.csdn.net/XuFangfang5206/article/details/80030300

https://www.runoob.com/python/python-func-open.html

https://www.youtube.com/watch?v=TBemVnOITjk&list=PLXO45tsB95cIRP5gCi8AlYwQ1uFO2aQBw&index=16

https://www.youtube.com/watch?v=pz3I-9MgxGo&list=PLXO45tsB95cIRP5gCi8AlYwQ1uFO2aQBw&index=17

https://shengyu7697.github.io/python-write-text-file/

