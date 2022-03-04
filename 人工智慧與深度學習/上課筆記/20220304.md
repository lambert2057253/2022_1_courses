## `資料科學(Data Science)_常用套件`

- 資料科學  Data Science
  - numpy
  - pandas
  - scipy
  - statsmodels(統計分析)

- 科學計算  scientific calculation
  - sympy
  - scipy
- 電腦視覺
  - opencv
- 資料視覺化  Data Visulization
  - matplotlib
  - seaborn
  - plotly
  - .....

- 機器學習
  - scikit-learn (sklearn)  

- 機器學習與人工智慧
  - Tensorflow
  - Pytorch (torch)


## 作業 1: 確認開發環境的套件版本
- Google Colab ==> !pip list
- anaconda
  - [Anaconda介紹及安裝教學](https://medium.com/python4u/anaconda%E4%BB%8B%E7%B4%B9%E5%8F%8A%E5%AE%89%E8%A3%9D%E6%95%99%E5%AD%B8-f7dae6454ab6) 

## 作業 2:如何載入套件

- import pandas as pd
- import numpy as np 
- import tensorflow as tf 

## 作業 3:如何學習或是使用套件
```
import numpy as np

b = np.linspace(0, 2, 4)
b

# array([0.        , 0.66666667, 1.33333333, 2.        ])
```
```
c = np.linspace(0, 2, 4, endpoint=False) 
c

# array([0. , 0.5, 1. , 1.5])
```
- 學習函式(function) linspace()的使用
  - [官方說明 numpy.linspace](https://numpy.org/doc/stable/reference/generated/numpy.linspace.html)
  - [Python numpy linspace用法及代碼示例](https://vimsky.com/zh-tw/examples/usage/python-numpy.linspace.html)
```
numpy.linspace(
start, 
stop, 
num=50, == >
endpoint=True, 
retstep=False, 
dtype=None, 
axis=0)
```
- 學習重點:
  - 函式(function)參數有哪些個?
    - 那些參數有預設值?
    - 那些參數一定要填
  - 函式(function)回傳的資料
    - 回傳的資料型態
    - 可以有幾種接收值
- 範例: numpy.linspace()
  - 函式(function)參數有哪些個?
    - 共有多少個參數? 7 個 ==> start, stop, num,endpoint, retstep, dtype, axis
    - 那些參數有預設值?
      - num=50,  預設值=>50
      - endpoint=True, 預設值=>True
      - retstep=False, 預設值=>False
      - dtype=None, 預設值=>None
      - axis=0   預設值=>0
    - 那些參數一定要填
      - start, stop,
  - 函式(function)回傳的資料
    - 回傳的資料型態 ==> ndarray
    - 可以有幾種接收值 ===> ndarray
