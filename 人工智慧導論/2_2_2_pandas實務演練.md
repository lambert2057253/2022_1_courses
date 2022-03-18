## 3_pandas的各種索引技術
- [Pandas 資料分析實戰：使用 Python 進行高效能資料處理及分析 (Learning pandas : High-performance data manipulation and analysis in Python, 2/e) Michael Heydt ](https://www.tenlong.com.tw/products/9789864343898)
  - [GITHUBChapter 6](https://github.com/PacktPublishing/Learning-Pandas-Second-Edition/tree/master/Chapter06) 
  - Chapter 6：索引資料
    - 6.1 設定pandas
    - 6.2 索引的重要性
    - 6.3 pandas 的索引型別
    - 6.4 使用索引
    - 6.5 階層式索引

## 4_pandas_20220311 pandas資料匯入與資料清理(Data cleaning)
- [經典:Python 資料分析, 2/e](https://www.tenlong.com.tw/products/9789864769254)
  - [GITHUB](https://github.com/wesm/pydata-book) 
  - [中譯](https://github.com/LearnXu/pydata-notebook/tree/master/)
  - 第六章 資料載入、儲存和檔案格式
  - 第七章 資料整理和前處理
- [Pandas 資料分析實戰：使用 Python 進行高效能資料處理及分析 (Learning pandas : High-performance data manipulation and analysis in Python, 2/e) Michael Heydt ](https://www.tenlong.com.tw/products/9789864343898)
  - [GITHUB](https://github.com/PacktPublishing/Learning-Pandas-Second-Edition) 
  - [Ch9](https://github.com/PacktPublishing/Learning-Pandas-Second-Edition/blob/master/Chapter09/09_Accessing_Data.ipynb)
  - Chapter 9：存取資料
  - 9.1 設定pandas
  - 9.2 處理CSV及文字/表格格式的資料
  - 9.3 讀寫Excel格式資料
  - 9.4 讀寫JSON檔案
  - 9.5 從網站讀取HTML資料
  - 9.6 讀寫HDF5格式檔案
  - 9.7 存取網站上的CSV資料
  - 9.8 讀寫SQL資料庫
  - 9.9 從遠端資料服務讀取資料

## 1_讀寫CSV檔案 
- see 9.2 處理CSV及文字/表格格式的資料 
- [pandas.read_table](https://pandas.pydata.org/docs/reference/api/pandas.read_table.html)
- 讀取CSV [pandas.read_csv()](https://pandas.pydata.org/docs/reference/api/pandas.read_csv.html)
  - 熟悉各種讀取參數用法
  - index_col
  - nrows：僅讀取⼀定的⾏數
  - skiprows：跳過⼀定的⾏數
  - skipfooter：尾部有固定的⾏數永不讀取
  - skip_blank_lines：空⾏跳過
- 寫入CSV [pandas.DataFrame.to_csv()](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.to_csv.html#pandas-dataframe-to-csv)

#### 先下載遠端資料到Google Colab 
```
!wget https://raw.githubusercontent.com/PacktPublishing/Learning-Pandas-Second-Edition/master/data/msft.csv
```
#### 檢視資料
```
!head -n 5 msft.csv 
```
#### Reading a CSV into a DataFrame
```
msft = pd.read_csv("./msft.csv")
msft[:5]
```

#### Specifying the index column when reading a CSV file
```python
# use column 0 as the index
msft = pd.read_csv("./msft.csv", index_col=0)
msft[:5]
```


```python

```
#### 寫入CSV Saving a DataFrame to a CSV ==> [pandas.DataFrame.to_csv()](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.to_csv.html#pandas-dataframe-to-csv)
```PYTHON
# read in data only in the Date and Close columns
# and index by the Date column
df2 = pd.read_csv("./msft.csv", 
                  usecols=['Date', 'Close'], 
                  index_col=['Date'])
df2[:5]
```
```python
# save df2 to a new csv file
# also specify naming the index as date
df2.to_csv("./msft_A999168.csv", index_label='date')
```
```
# view the start of the file just saved
!head -n 5 ./msft_A999168.csv
```

```python

```

### 2_讀寫excel檔案
```python

```


```python

```

```python

```


```python

```


```python

```
