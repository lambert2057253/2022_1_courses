# 第3章 控制敘述

```
3.2 選擇敘述
  - if 若滿足就執行  不滿足就不執行   是非題
  - if-else  二選一(一定會執行某一個)  若滿足就執行 敘述區段1    不滿足就執行敘述區段2
  - if…else if…else 多選一 多重判斷式
  - 巢狀式if選擇結構
  - switch多重選擇敘述
3.3 重複敘述
  for迴圈
  while迴圈
  do~while迴圈
3.4 分支敘述
  break
  continue
```

## 選擇敘述
- if 若滿足就執行  不滿足就不執行   是非題
- if-else  二選一(一定會執行某一個)  若滿足就執行 敘述區段1    不滿足就執行敘述區段2
- if…else if…else 多選一 多重判斷式



### if選擇敘述
- 3-1程式範例說明
```
if(條件式)
{
  條件滿足時
  執行這些statements(敘述)
  敘述區段1
}
  敘述區段
```
```
條件式是由運算式構成，若條件式含有多個關係式時，可以使用適當的邏輯運算子(&& and 和)( || or 或)來連接。
if ((x > 0) && (x % 2 == 0))  
if (ch < '0' || ch > '9') 

若條件式的結果為true，執行 if敘述後 <敘述區段1>，再執行 <敘述區段2>。
若條件式結果為false，跳過if 內的 <敘述區段1> 不執行，直接執行 <敘述區段2>。

若 <敘述區段1> 有多行敘述時，必須用大括號括起來。若只有一行敘述，則可省略。
```
- 條件式的練習寫作 
  - if ((x > 0) && (x % 2 == 0))  
  - if (ch < '0' || ch > '9') 


```java
import java.util.Scanner;

public class If {
	public static void main(String[] args) {
		Scanner scn = new Scanner(System.in);
		System.out.print("請輸入消費金額：");
		int money = scn.nextInt();   
		if(money>1000) {			    
		   money = 1000 + (int)((money - 1000) * 0.9);	
		}
		System.out.printf("實付金額：%d 元%n", money);
		scn.close();
	}
}
```
- 回答下列問題:print() | printf() | println() 有何差別?
### if-else 選擇敘述
- if-else  二選一(一定會執行某一個)  若滿足就執行 敘述區段1    不滿足就執行敘述區段2
```
if(條件式)
{
  條件滿足時
  執行這些statements(敘述)
  敘述區段1
}else
{
  條件不滿足時
  執行這些statements(敘述)
  敘述區段2
}
  敘述區段3
```
- 3-2程式範例說明

```java
import java.util.Scanner;

public class ElseIf {
	public static void main(String[] args) {
		Scanner scn = new Scanner(System.in);
		String id, pass;
		System.out.print("請輸入帳號: ");
		id = scn.next();
		System.out.print("請輸入密碼: ");
		pass = scn.next();
		if (id.equals("Love") & pass.equals("2520")) {
		    System.out.println("帳號密碼正確!!");
			System.out.println("歡迎進入本系統!!");
		} else {
			System.out.println("帳號密碼錯誤!!");
			System.out.println("無法進入本系統!!");
		}
		scn.close();
	}
}
```
### if…else if…else 多選一 多重判斷式
```
if(條件式1)
{
  條件滿足時
  執行這些statements(敘述)
  敘述區段1
 }elseif(條件式2)
{
  條件不滿足時
  執行這些statements(敘述)
  敘述區段2
}elseif(條件式2)
{
  條件不滿足時
  執行這些statements(敘述)
  敘述區段2
}
}else
{
  上述所有條件都不滿足時
  執行這些statements(敘述)
  敘述區段4
}
  敘述區段5
```
```
if …else if…else多重判斷式，多了else if敘述來增加判斷的條件，不管有多少個條件，只要多加else if就可以處理。

只允許執行其中某一個敘述區段。

執行時會由上向下逐一檢查條件，一旦符合某條件就執行對應的敘述區段，接著跳離整個多重判斷式。

注意最後是else，可以處理以上條件都不滿足時的情形。
```
- 3-3程式範例說明
```java
public class Ex03_T01 {

	public static void main(String[] args) {
		String str = "null";
		if (str == null) {
			System.out.println("null");
			// } else (str.length() == 0) {
		} else if (str.length() == 0) {
			System.out.println("zero");
		} else {
			System.out.println("some");
		}
	}
}
```

## 
```java
import java.util.Scanner;
public class ElseIfElse {
	public static void main(String[] args) {
		Scanner scn = new Scanner(System.in);
		System.out.print("請輸入用水度數: ");
		int deg = scn.nextInt(); 
		
		double unit;   
		
		if (deg <= 10) {          
			unit = 7.35;           
		} else if (deg > 10 && deg <= 30) {    
			unit = 9.45;          
		} else if (deg > 30 && deg <= 50) {   
			unit = 11.55;          
		} else {                  
			unit = 12.075;         /
		}
		
		System.out.printf("每度: %6.3f 元%n", unit);
		System.out.printf("實付水費: %d 元", (int) (deg * unit));
		scn.close();
	}
}
```

## switch
```java
import java.util.Scanner;
public class Grade {
	//@SuppressWarnings("preview")
	public static void main(String[] args) {
		Scanner scn = new Scanner(System.in);
		char grade;
		System.out.print("請輸入考試分數: ");
		int score = scn.nextInt();
		//switch (score / 10) {
		//	case 10,9,8 -> grade = '甲';
		//	case 7 -> grade = '乙';
		//	case 6 -> grade = '丙';	
		//	default -> grade = '丁'; 
		//}
		switch (score / 10) {
			case 10: // 以下是屬於甲級的分數
			case 9:
			case 8:
				grade = '甲';	break;
			case 7: // 屬於乙級的分數
				grade = '乙';	break;
			case 6: // 屬於丙級的分數
				grade = '丙';	break;
			default:// 屬於丁級的分數
				grade = '丁'; 
		}
		System.out.println(score + "分是屬於" + grade + "級的成績。");
		scn.close();
	}
}
```
## nest-if
```java
import java.util.Scanner;
public class NestIf {
	public static void main(String[] args) {
		Scanner scn = new Scanner(System.in);
		int num1, num2, num3, max;
		System.out.print("請輸入三個數字(空白區隔):");

                num1 = scn.nextInt();
		num2 = scn.nextInt();
		num3 = scn.nextInt();

                if (num1 > num2) {        
			if (num1 > num3)
				max = num1;
			else
				max = num3;
		} else {
			if (num2 > num3)
				max = num2;
			else
				max = num3;
		}
		System.out.println("最大的數字是:" + max);
		scn.close();
	}
}

```
# 3.3 重複敘述

## for迴圈

```java
public class For {
	public static void main(String[] args) {
		int i;
		int sum = 0;
		
		for (i = 1; i <= 10; i++) {
		    sum += i;
		}
		
		System.out.println("從1加到10的總和是: " + sum);
		System.out.println("最後 i 值為: " + i);	
	}
}
```

```
  sum += i; == >sum = sum +i;
  i++ ==> i = i + 1;
```
## NestFor
```java
public class NestFor {
	public static void main(String[] args) {
		for (int y = 1; y <= 4; y++) {
			for (int x = 1; x <= 16; x++) {
				System.out.print("*");
			}
			System.out.println();	  // 換行
		}
	}
}
```
## while迴圈

```java
import java.util.Scanner;
public class Average {
	public static void main(String[] args) {
		Scanner scn = new Scanner(System.in);
		int score = 0;	// 輸入的分數預設為0
		int sum = 0;	// 累計的總和
		int num = 0;		   // 預設人數為0
		while (score != -1) {
			System.out.print("請輸入分數 (輸入-1結束):");
			score = scn.nextInt();	// 讀取分數
			if(score != -1) {
		    	sum += score;		// 將輸入分數的加到總和sum中
		    	num++;	// 人數加1        		
			}
		}
		System.out.printf("平均分數 = " + (double)((sum) / (num)));
		scn.close();
	}
}
```
```
80 90 55 == > 75
``` 

## do~while迴圈

```java
import java.util.Scanner;
public class DoWhile {
	public static void main(String[] args) {
		Scanner scn = new Scanner(System.in);
		int num, n, sum;
		do {
			System.out.print("請輸入1~15正整數來計算階乘值: ");
			num = scn.nextInt();
		} while (num < 1 || num > 15);
		n = num;
		sum = 1;
		do {
			sum *= n--;
		} while (n > 0);
		System.out.printf("%d! = %d %n", num, sum);
		scn.close();
	}
}
```
```

sum *= n--;
   == >  sum = sum*n;
         n = n-1;
```
# 3.4 分支敘述

## break

```java
import java.util.Scanner;
public class BreakFor {
	public static void main(String[] args) {
		Scanner scn = new Scanner(System.in);
		System.out.print("請輸入正整數：");
		int num= scn.nextInt();
		boolean prm = true;  	// 預設prm為true，表為質數
		for (int i = 2; i < num; i++) {
			if (num % i == 0) {
				prm = false;      // 設prm為false，表不是質數
				break;	// 離開for迴圈
			}
		}
		if (prm == true) 
			System.out.printf("%d 是質數", num);
		else
			System.out.printf("%d 不是質數", num);
		scn.close();
	}
}
```

## continue

```java
public class Continue {
	public static void main(String[] args) {
		for (int i = 0; i <= 10; i++) {
			if (i % 2 == 0)
				continue;
			System.out.print(i + ", ");
		}
	}
}
```


```java

```


```java

```


```java

```


```java

```


```java

```


```java

```


```java

```


```java

```


```java

```

- 3-1程式範例說明
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
