# 第1章 Java概述
```java

 import java.util.Scanner;	  //import Scanner類別套件

 /** 這是主類別 Hi */
 public class Hi {
	 /**這是程式進入點 main 方法*/
	 public static void main(String[] args) {
		Scanner scn = new Scanner(System.in);	/*建立 Scanner 物件 scn*/
		System.out.print("請輸入姓名：");
		String strName = scn.next();   //字串變數strName儲存scn接受的字串
		System.out.println("Hi! "+strName + ", 歡迎來到Java世界！");
		scn.close();	//關閉scn物件
	 }

}
```

- 程式說明
  - [1] import ==> 載入套件
    - 要在鍵盤輸入需載入 java.util.Scanner套件
  - [2] public class Hi ==> 
    - public: 公開的(大家都可以存取) 
    - class : 類別
    - Hi : 檔案名稱Hi.java 須和public class `Hi` 一樣 (大小寫需都一模一樣)
  - [3] public static void main(String[] args)==> 
    - main(): ==> 程式開始執行的地方
    - public:公開的(大家都可以存取) ==> 修飾子
    - static:靜態的
    - String[] args ==> 存入函數的參數  ping -c 4 www.google.com
  - [4]Scanner scn = new Scanner(System.in);	==> 建立 Scanner 物件 scn | Scanner():建構子
    - 左邊 Scanner scn ==> 宣告scn變數是 Scanner類別的資料型態
    - 右邊 new Scanner(System.in) ==> new(建立物件)  
      - Java.lang.System 類別 ==> 系統輸入|輸出|錯誤 使用的類別
        - in: The “standard” input stream
        - out: The “standard” output stream 
        - err: The “standard” error output stream
  - [5]System.out.print("請輸入姓名：");==> 使用System.out的print()輸出到螢幕
  - [6]String strName = scn.next();   //使用scn.next()接收字串 ==> 再把scn接收的字串 儲存 在字串變數strName
  - [7]System.out.println("Hi! "+strName + ", 歡迎來到Java世界！"); ==> 使用System.out的println()輸出到螢幕
    -  println() 和print()的差異?
  - [8]scn.close();	//關閉scn物件
  - [9]總結:要在鍵盤輸入資料流程
    - 需載入 java.util.Scanner套件 ==> import java.util.Scanner
    - Scanner scn = new Scanner(System.in);	/*建立 Scanner 物件 scn*/
    - String strName = scn.next();   //使用scn.next()接收字串 ==> 再把scn接收的字串 儲存 在字串變數strName
    - 接收輸入的`字串` ==> 使用.next()方法
    - 接收輸入的`整數` ==> 使用nextInt()方法 ==>int i = scn.nextInt();
  - [10] [java.util套件](https://docs.oracle.com/javase/8/docs/api/java/util/package-summary.html)
    - [Scanner類別](https://docs.oracle.com/javase/8/docs/api/java/util/Scanner.html) 

### 進階範例
```java
     String input = "1 fish 2 fish red fish blue fish";
     Scanner s = new Scanner(input).useDelimiter("\\s*fish\\s*");
     System.out.println(s.nextInt());
     System.out.println(s.nextInt());
     System.out.println(s.next());
     System.out.println(s.next());
     s.close();
```
- [Java.util套件(package:把許多功能相似的類別統整在一起)](http://tw.gitbook.net/java/util/index.html)
- [java.util.Scanner類別](https://docs.oracle.com/javase/8/docs/api/java/util/Scanner.html)
- 有許多有用的方法|函式  [java.util.Scanner類別](http://tw.gitbook.net/java/util/java_util_scanner.html)
  - [Java Scanner useDelimiter() Method](https://www.javatpoint.com/post/java-scanner-usedelimiter-method)
  - scanner.nextLine()
  - [Java中next與nextLine方法的區別](https://www.itread01.com/content/1541418722.html)

# 第2章 資料型別與運算子
- 2-1程式範例說明
  - [1]0b11 ==> b== binary二進制
  - [2]011 ==> 0 代表八進制11
  - [3]0x ==>0x 代表十六進制
  - [4]
  - [5]

```java
public class Ex02_01 {
	public static void main(String[] args) {
		System.out.println("  十進制 11有多大 -> " + 11);    // 十進制11
		System.out.println("  二進制 11有多大 -> " + 0b11);  // 二進制11轉十進制
		System.out.println("  八進制 11有多大  -> " + 011);   // 八進制11轉十進制
		System.out.println("十六進制 11有多大  -> " + 0x11);  // 十六進制11轉十進制
	}
}
```
- 2-2程式範例說明
  - [1]
  - [2]
  - [3]
  - [4]
  - [5]
  - [6]
  - [7]
  - [8]
  - [9]
  - [10]
```java
public class Ex02_02 {
	public static void main(String[] args) {
		int money = 101_000;	    // 宣告money為整數變數，並指定初值
		double rate = .05;	           // 宣告rate為浮點數變數，並指定初值
		System.out.println("本金 " + money + " 元, 利率 " + rate +
							"，年利息為" + money * rate + "元");
	}
}
```
- 2-3程式範例說明
  - [1]
  - [2]
  - [3]
  - [4]
  - [5]
  - [6]
  - [7]
  - [8]
  - [9]
  - [10]
```java

```
- 2-3程式範例說明
  - [1]
  - [2]
  - [3]
  - [4]
  - [5]
  - [6]
  - [7]
  - [8]
  - [9]
  - [10]
```java

```
- 2-3程式範例說明
  - [1]
  - [2]
  - [3]
  - [4]
  - [5]
  - [6]
  - [7]
  - [8]
  - [9]
  - [10]
```java

```
- 2-3程式範例說明
  - [1]
  - [2]
  - [3]
  - [4]
  - [5]
  - [6]
  - [7]
  - [8]
  - [9]
  - [10]
```java

```
- 2-3程式範例說明
  - [1]
  - [2]
  - [3]
  - [4]
  - [5]
  - [6]
  - [7]
  - [8]
  - [9]
  - [10]
```java

```
- 2-3程式範例說明
  - [1]
  - [2]
  - [3]
  - [4]
  - [5]
  - [6]
  - [7]
  - [8]
  - [9]
  - [10]
```java

```
- 2-3程式範例說明
  - [1]
  - [2]
  - [3]
  - [4]
  - [5]
  - [6]
  - [7]
  - [8]
  - [9]
  - [10]
```java

```
- 2-3程式範例說明
  - [1]
  - [2]
  - [3]
  - [4]
  - [5]
  - [6]
  - [7]
  - [8]
  - [9]
  - [10]
```java

```
- 2-3程式範例說明
  - [1]
  - [2]
  - [3]
  - [4]
  - [5]
  - [6]
  - [7]
  - [8]
  - [9]
  - [10]
```java

```


