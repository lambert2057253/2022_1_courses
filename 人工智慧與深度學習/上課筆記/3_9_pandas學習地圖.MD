# pandas學習地圖
### pandas 參考書籍
- [經典:Python 資料分析, 2/e](https://www.tenlong.com.tw/products/9789864769254)
  - [GITHUB](https://github.com/wesm/pydata-book) 
  - [中譯](https://github.com/LearnXu/pydata-notebook/tree/master/)
- [Pandas 資料分析實戰：使用 Python 進行高效能資料處理及分析 (Learning pandas : High-performance data manipulation and analysis in Python, 2/e) Michael Heydt ](https://www.tenlong.com.tw/products/9789864343898)
  - [GITHUB](https://github.com/PacktPublishing/Learning-Pandas-Second-Edition) 
- [Python 資料分析必備套件！Pandas 資料清理、重塑、過濾、視覺化 (Pandas 1.x Cookbook, 2/e) Matt Harrison、Theodore Petrou](https://www.tenlong.com.tw/products/9789863126898?)
  - [GITHUB](https://github.com/PacktPublishing/Pandas-Cookbook-Second-Edition) 
- [深入淺出 Pandas：利用 Python 進行數據處理與分析 李慶輝　著](https://www.tenlong.com.tw/products/9787111685456)
## 序列Series
```
Chapter 3：用序列表示單變數資料
3.1 設定pandas
3.2 建立序列
3.3 .index及.values屬性
3.4 序列的大小及形狀
3.5 在序列建立時指定索引
3.6 頭、尾、選取
3.7 以索引標籤或位置提取序列值
3.8 把序列切割成子集合
3.9 利用索引標籤實現對齊
3.10 執行布林選擇
3.11 將序列重新索引
3.12 原地修改序列
```
## DataFrame 資料框
```
Chapter 4：用資料框表示表格及多變數資料
4.1 設定pandas
4.2 建立資料框物件
4.3 存取資料框的資料
4.4 利用布林選擇選取列
4.5 跨越行與列進行選取

Chapter 5：操控資料框結構
5.1 設定pandas
5.2 重新命名行
5.3 利用[]及.insert()增加新行
5.4 利用擴展增加新行
5.5 利用串連增加新行
5.6 改變行的順序
5.7 取代行的內容
5.8 刪除行
5.9 附加新列
5.10 列的串連
5.11 經由擴展增加及取代列
5.12 使用.drop()移除列
5.13 利用布林選擇移除列
5.14 使用切割移除列

Chapter 6：索引資料
6.1 設定pandas
6.2 索引的重要性
6.3 pandas 的索引型別
6.4 使用索引
6.5 階層式索引

Chapter 7：類別資料
7.1 設定pandas
7.2 建立類別物件
7.3 重新命名類別
7.4 附加新類別
7.5 移除類別
7.6 移除未使用的類別
7.7 設定類別
7.8 類別物件的敘述性資訊
7.9 學校成績轉換

Chapter 8：數值與統計方法
8.1 設定pandas
8.2 對pandas物件執行算術運算
8.3 在pandas物件上執行統計程序

Chapter 11：結合、關聯以及重塑資料
11.1 設定pandas
11.2 串連幾個物件的資料
11.3 合併與連結資料
11.4 資料值與索引的樞紐操作
11.5 堆疊與解堆疊
11.6 堆疊資料帶來的效能好處

Chapter 12：資料聚合
12.1 設定pandas
12.2 拆開、套用、結合（SAC）模式
12.3 範例資料
12.4 拆開資料
12.5 套用聚合函數、轉換以及過濾
12.6 轉換分組資料
12.7 過濾分組資料
```
### 資料匯入與清理(Data Cleaning)
```
Chapter 9：存取資料
9.1 設定pandas
9.2 處理CSV及文字/表格格式的資料
9.3 讀寫Excel格式資料
9.4 讀寫JSON檔案
9.5 從網站讀取HTML資料
9.6 讀寫HDF5格式檔案
9.7 存取網站上的CSV資料
9.8 讀寫SQL資料庫
9.9 從遠端資料服務讀取資料

Chapter 10：整理資料
10.1 設定pandas
10.2 資料整理的意涵
10.3 如何處理資料遺漏(Missing value)
10.4 處理重複資料
10.5 資料轉換
```

### Pandas 專論:時間序列分析與建模
- [Python 資料分析,2/e 第十一章 時間序列](https://www.tenlong.com.tw/products/9789864769254)
- [Pandas 資料分析實戰 Chapter 13：時間序列建模](https://www.tenlong.com.tw/products/9789864343898)
```
Chapter 13：時間序列建模
13.1 設定IPython筆記本
13.2 日期、時間、區間的表示方法
13.3 時間序列資料簡介
13.4 使用偏移值計算新日期
13.5 利用Period表示持續時間
13.6 處理日曆中的假日
13.7 利用時區正規化時間戳記
13.8 操控時間序列資料
13.9 時間序列的移動視窗運算
```
# 案例分析
## 案例分析:[Python 資料分析,2/e](https://www.tenlong.com.tw/products/9789864769254)
```
14.1 USA.gov Data from Bitly（USA.gov資料集）
2011年，短連結服務（URL shortening service）商Bitly和美國政府網站USA.gov合作，
提供了一份從用戶中收集來的匿名資料，
這些使用者使用了結尾為.gov或.mil的短連結。
在2011年，這些資料的動態資訊每小時都會保存一次，並可供下載。不過在2017年，這項服務被停掉了。
資料是每小時更新一次，檔中的每一行都用JOSN（JavaScript Object Notation）格式保存
```
```
14.2 MovieLens 1M Dataset（MovieLens 1M資料集）
這個資料集是電影評分資料：包括電影評分，電影中繼資料（風格類型，年代）以及
關於使用者的人口統計學資料（年齡，郵編，性別，職業等）。

MovieLens 1M資料集含有來自6000名用戶對4000部電影的100萬條評分資料。
分為三個表：評分，使用者資訊，電影資訊
```
```
14.3 US Baby Names 1880–2010（1880年至2010年美國嬰兒姓名）
這個資料是從1880年到2010年嬰兒名字頻率資料。

資料集可以用來做很多事，例如：
計算指定名字的年度比例
計算某個名字的相對排名
計算各年度最流行的名字，以及增長或減少最快的名字
分析名字趨勢：母音、輔音、長度、總體多樣性、拼寫變化、首尾字母等
分析外源性趨勢：聖經中的名字、名人、人口結構變化等
```
```
14.4 USDA Food Database（美國農業部食品資料庫）
這個資料是關於食物營養成分的。
存儲格式是JSON
每種食物都有一系列特徵，其中有兩個list，protions和nutrients。
我們必須把這樣的資料進行處理，方便之後的分析
```
```
14.5 2012 Federal Election Commission Database（2012聯邦選舉委員會資料庫）
這個選舉資料庫對於政治宣傳很有用。
裡面包含了支持者的名字，職業和雇主，地址，贊助金額。
一個有意思的資料集是關於2012年美國總統選舉的。
這個資料集有150MB，名稱為P00000001-ALL.csv。
```
## 案例分析:[Pandas 資料分析實戰](https://www.tenlong.com.tw/products/9789864343898)
```
Chapter 15：歷史股價分析
15.1 設定IPython筆記本
15.2 從Google取得與組織股票資料
15.3 繪製股價時間序列的圖
15.4 繪製成交量序列的圖
15.5 計算簡易的每日收盤價變化百分比
15.6 計算簡易的股票每日累積報酬率
15.7 將每日報酬率重新取樣為每月報酬率
15.8 分析報酬率分布
15.9 移動平均計算
15.10 比較股票之間的平均每日報酬率
15.11 依每日收盤價的變化百分比找出股票相關性
15.12 計算股票波動率
15.13 決定風險相對於期望報酬率的關係
```
