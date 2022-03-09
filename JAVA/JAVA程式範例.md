# 第1章 Java概述
```java
/*
  * 我的第一個Java程式
 */
 package ex01;		//指定package 為ex01

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

# 第2章 資料型別與運算子
- 2-1程式範例說明
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


