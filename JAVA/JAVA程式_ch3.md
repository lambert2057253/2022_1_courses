# 第3章 控制敘述

```
3.2 選擇敘述
  - if 若滿足就執行  不滿足就不執行   是非題
  - if-else  二選一(一定會執行某一個)  若滿足就執行 敘述區段1    不滿足就執行敘述區段2
  - if…else if…else 多選一 多重判斷式
  - 巢狀式if選擇結構
  - switch多重選擇敘述

3.3 重複敘述

3.4 分支敘述

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
