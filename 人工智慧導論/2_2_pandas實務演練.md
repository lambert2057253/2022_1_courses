### pandas
- [經典:Python 資料分析, 2/e](https://www.tenlong.com.tw/products/9789864769254)
  - [GITHUB](https://github.com/wesm/pydata-book) 
  - [中譯](https://github.com/LearnXu/pydata-notebook/tree/master/)
- [Pandas 資料分析實戰：使用 Python 進行高效能資料處理及分析 (Learning pandas : High-performance data manipulation and analysis in Python, 2/e) Michael Heydt ](https://www.tenlong.com.tw/products/9789864343898)
  - [GITHUB](https://github.com/PacktPublishing/Learning-Pandas-Second-Edition) 
- [Python 資料分析必備套件！Pandas 資料清理、重塑、過濾、視覺化 (Pandas 1.x Cookbook, 2/e) Matt Harrison、Theodore Petrou](https://www.tenlong.com.tw/products/9789863126898?)
- [深入淺出 Pandas：利用 Python 進行數據處理與分析 李慶輝　著](https://www.tenlong.com.tw/products/9787111685456)

## 1_pandas Data Structures| pandas的資料結構 ==> series vs DataFrame


### 1_1_series的運算 see [CHAPTER 5 Getting Started with pandas](https://github.com/LearnXu/pydata-notebook/blob/master/Chapter-05/5.1%20Introduction%20to%20pandas%20Data%20Structures%EF%BC%88pandas%E7%9A%84%E6%95%B0%E6%8D%AE%E7%BB%93%E6%9E%84%EF%BC%89.ipynb)
- 建立series
  - 使用pandas.Series() 
  - 使用字典資料型態傳入pandas.Series() 
- 搜尋滿足條件的資料

### 1_2_DataFrame的運算 see [CHAPTER 5 Getting Started with pandas](https://github.com/LearnXu/pydata-notebook/blob/master/Chapter-05/5.1%20Introduction%20to%20pandas%20Data%20Structures%EF%BC%88pandas%E7%9A%84%E6%95%B0%E6%8D%AE%E7%BB%93%E6%9E%84%EF%BC%89.ipynb)
- 建立DataFrame
  - 使用pandas.Series() 
  - 使用字典資料型態傳入pandas.Series() 
- 搜尋滿足條件的資料

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
