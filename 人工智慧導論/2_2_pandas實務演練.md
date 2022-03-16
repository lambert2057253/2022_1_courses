### pandas
- [經典:Python 資料分析, 2/e](https://www.tenlong.com.tw/products/9789864769254)
  - [GITHUB](https://github.com/wesm/pydata-book) 
  - [中譯](https://github.com/LearnXu/pydata-notebook/tree/master/)
- [Pandas 資料分析實戰：使用 Python 進行高效能資料處理及分析 (Learning pandas : High-performance data manipulation and analysis in Python, 2/e) Michael Heydt ](https://www.tenlong.com.tw/products/9789864343898)
  - [GITHUB](https://github.com/PacktPublishing/Learning-Pandas-Second-Edition) 
  - 一定要教  Chapter 15：歷史股價分析
- [Python 資料分析必備套件！Pandas 資料清理、重塑、過濾、視覺化 (Pandas 1.x Cookbook, 2/e) Matt Harrison、Theodore Petrou](https://www.tenlong.com.tw/products/9789863126898?)
- [深入淺出 Pandas：利用 Python 進行數據處理與分析 李慶輝　著](https://www.tenlong.com.tw/products/9787111685456)

## 1_pandas Data Structures| pandas的資料結構 ==> series vs DataFrame


### 1_1_series的運算 see [CHAPTER 5 Getting Started with pandas](https://github.com/LearnXu/pydata-notebook/blob/master/Chapter-05/5.1%20Introduction%20to%20pandas%20Data%20Structures%EF%BC%88pandas%E7%9A%84%E6%95%B0%E6%8D%AE%E7%BB%93%E6%9E%84%EF%BC%89.ipynb)
- 建立series
  - 使用pandas.Series() 
  - 使用字典資料型態傳入pandas.Series() 
- 搜尋滿足條件的資料


#### (1)使用[pandas.Series()](https://pandas.pydata.org/docs/reference/api/pandas.Series.html) 建立Series
```python
obj = pd.Series([41, 27, -25, 13,21])
obj
```


```python
obj.values
```


```python
obj.index
```

#### (2)使用[pandas.Series()](https://pandas.pydata.org/docs/reference/api/pandas.Series.html) 建立Series
```python
obj2 = pd.Series([4, 7, -5, 3], index=['d', 'b', 'a', 'c'])
obj2
```
```python
obj2.values
```


```python
obj2.index
```

#### 透過index(索引)進行搜尋

```python
obj2['a']
```


```python
obj2[['c', 'a', 'd']]
```
#### 透過index(索引)進行設定

```python
obj2['d'] = 6
```


```python
obj2[['c', 'a', 'd']]
```
#### 更多運算
```python
obj2[obj2 > 0]
```


```python
obj2 * 2
```

```python
import numpy as np
np.exp(obj2)
```

#### 利用dict來創建series
```python
sdata = {'Ohio': 35000, 'Texas': 71000, 'Oregon':16000, 'Utah': 5000}

obj3 = pd.Series(sdata)
obj3
```


```python
states = ['California', 'Ohio', 'Oregon', 'Texas']

obj4 = pd.Series(sdata, index=states)
obj4
```
#### 使用pandas的isnull和notnull函數檢測MISSING Value(缺失資料)
```python
pd.isnull(obj4)
```


```python
pd.notnull(obj4)
```

```python
obj4.isnull()
```

#### Series自動排序(Data alignment features)
- Series自動按index label來排序


```python
obj3
```

```python
obj4
```


```python
obj3 + obj4
```

#### series  `name屬性`的運用
- series自身和它的index都有一個叫name的屬性

```python
obj4.name = 'population'

obj4.index.name = 'state'

obj4
```
#### 更改 series的index

```python
obj
obj.index = ['Bob', 'Steve', 'Jeff', 'Ryan']
obj

```
#### 加分作業:研讀底下參考資料並完成實務演練

[Pandas 資料分析實戰：使用 Python 進行高效能資料處理及分析 (Learning pandas : High-performance data manipulation and analysis in Python, 2/e) Michael Heydt ](https://www.tenlong.com.tw/products/9789864343898)
  - [GITHUB](https://github.com/PacktPublishing/Learning-Pandas-Second-Edition) 
  - Chapter 3：用序列表示單變數資料
    - 3.1 設定pandas
    - 3.2 建立序列
    - 3.3 .index及.values屬性
    - 3.4 序列的大小及形狀
    - 3.5 在序列建立時指定索引
    - 3.6 頭、尾、選取
    - 3.7 以索引標籤或位置提取序列值
    - 3.8 把序列切割成子集合
    - 3.9 利用索引標籤實現對齊
    - 3.10 執行布林選擇
    - 3.11 將序列重新索引
    - 3.12 原地修改序列


### 1_2_DataFrame的運算 see [CHAPTER 5 Getting Started with pandas](https://github.com/LearnXu/pydata-notebook/blob/master/Chapter-05/5.1%20Introduction%20to%20pandas%20Data%20Structures%EF%BC%88pandas%E7%9A%84%E6%95%B0%E6%8D%AE%E7%BB%93%E6%9E%84%EF%BC%89.ipynb)
- 建立DataFrame
  - 使用pandas.Series() 
  - 使用字典資料型態傳入pandas.Series() 
- 搜尋滿足條件的資料

```python

```


```python

```


```python

```
## 3_2_pandas_20220311 pandas資料匯入與資料清理(Data cleaning)

## [Ch9](https://github.com/PacktPublishing/Learning-Pandas-Second-Edition/blob/master/Chapter09/09_Accessing_Data.ipynb)
```
!wget https://raw.githubusercontent.com/PacktPublishing/Learning-Pandas-Second-Edition/master/data/msft.csv
```
```
!head -n 5 msft.csv 
```
```
msft = pd.read_csv("./msft.csv")
msft[:5]
```
