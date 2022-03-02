## BinarySecurityANDProtection

- Stack Canaries
- No eXecute |the NX bit | Data Execution Prevention(DEP) 
- Relocation Read-Only (RELRO)
- [Address space layout randomization(ASLR)|[ Linux PaX project 2001]](https://en.wikipedia.org/wiki/Address_space_layout_randomization)


- [駭客們好自為之：CTF 大賽 PWN 奪旗技術大展 吳石 審校，楊超 編著 深智數位](https://www.tenlong.com.tw/products/9789860776034?list_name=srh)
  - CH.04 Linux 安全機制
    - 4.1 Linux 基礎
    - 4.2 Stack Canaries
    - 4.3 No-eXecute 
    - 4.4 ASLR 和PIE
    - 4.5 FORTIFY_SOURCE
    - 4.6 RELRO

## Stack Canaries

- [Smashing the Stack for Fun and Profit (1996)](https://insecure.org/stf/smashstack.html)
  - Elias Levy (Aleph One). 1996. Smashing the Stack for Fun and Profit.Phrack 7, 19 (1996), 32 
- [Return-to-libc attack(1997)](https://en.wikipedia.org/wiki/Return-to-libc_attack)
  - [Getting around non-executable stack (and fix)|solar () FALSE COM (Solar Designer)(1997)](https://seclists.org/bugtraq/1997/Aug/63)

- [stack canary(1998) StackGuard]
  - A stack canary is a value placed on the stack such that a stack-buffer overflow will overwrite it before corrupting the return address. 
  - The buffer overflow can then be detected by verifying the integrity of the canary before performing the return.
  - Crispin Cowan et al. 1998. StackGuard: Automatic adaptive detection and prevention of buffer-overflow attacks. USENIX Security Symposium 98 (1998), 63–78. http://portal.acm.org/citation.cfm?id=1267554
  - Crispin Cowan et al. 1999. Protecting Systems from Stack Smashing Attacks with StackGuard. (1999), 11
  - [參看相關作法:Protecting the stack with PACed canaries(2019)](https://arxiv.org/pdf/1909.05747.pdf)
  - [David Litchfield.Defeating the Stack Based Buffer Overflow Preventation Mechnaism of Microsoft Windows 2003 Server(2003)](https://www.blackhat.com/presentations/bh-asia-03/bh-asia-03-litchfield.pdf)
  - gcc 編譯預設是啟動Canary的:DEFAULT (when buffer large enough)
  - gcc 編譯時不啟動Canary ==> 	gcc -fno-stack-protector XXXXX.c

### 範例測試[教科書4-20]
```c
#include<stdio.h>

void main(){

  char buf[10];
  scanf("%s", buf);
}
```
- 沒有保護的編譯
```c
gcc -fno-stack-protector test.c -o fno.out


root@kali:~/20211012/1014# python3 -c 'print("A"*30)' |./fno.out
Segmentation fault
```
- 有保護的編譯

```c
gcc -fstack-protector test.c -o f.out


root@kali:~/20211012/1014# python3 -c 'print("A"*30)' |./f.out
*** stack smashing detected ***: <unknown> terminated
Aborted

開啟Canaries 後，程式終止並拋出錯誤"stack smashing detected" ，表示檢測到了堆疊溢位。
```

```
gdb-gef f.out
Reading symbols from f.out...(no debugging symbols found)...done.
GEF for linux ready, type `gef' to start, `gef config' to configure
93 commands loaded for GDB 8.2.1 using Python engine 3.7
[*] 3 commands could not be loaded, run `gef missing` to know why.
gef➤  disas main
Dump of assembler code for function main:
   0x0000000000001145 <+0>:	push   rbp
   0x0000000000001146 <+1>:	mov    rbp,rsp
   0x0000000000001149 <+4>:	sub    rsp,0x20
   
   0x000000000000114d <+8>:	mov    rax,QWORD PTR fs:0x28    < ====在Linux 中 fs 暫存器被用於存放執行緒局部儲存(Thread Local Storage, TLS) 
                                                            TLS 主要是為了避免多個執行緒同時存取同一全域變數或靜態變數時所導致的衝突，尤其是多個執行緒同時需要修改這一變數時。
                                                            stack_guard
   0x0000000000001156 <+17>:	mov    QWORD PTR [rbp-0x8],rax
   
   0x000000000000115a <+21>:	xor    eax,eax
   0x000000000000115c <+23>:	lea    rax,[rbp-0x12]
   0x0000000000001160 <+27>:	mov    rsi,rax
   0x0000000000001163 <+30>:	lea    rdi,[rip+0xe9a]        # 0x2004
   0x000000000000116a <+37>:	mov    eax,0x0
   0x000000000000116f <+42>:	call   0x1040 <__isoc99_scanf@plt>
   0x0000000000001174 <+47>:	nop
   
   0x0000000000001175 <+48>:	mov    rax,QWORD PTR [rbp-0x8]
   0x0000000000001179 <+52>:	xor    rax,QWORD PTR fs:0x28 < ====在Linux 中 fs 暫存器被用於存放執行緒局部儲存(Thread Local Storage, TLS) 
   0x0000000000001182 <+61>:	je     0x1189 <main+68>
   0x0000000000001184 <+63>:	call   0x1030 <__stack_chk_fail@plt>
   
   0x0000000000001189 <+68>:	leave  
   0x000000000000118a <+69>:	ret    
End of assembler dump.
```

### 攻擊Stack Canaries [教科書4-20/4-33]

- 方法1:將Canaries 的值洩露出來，然後在堆疊溢位時覆蓋上去，使其保持不變
- 方法2:同時篡改TLS 和堆疊上的Canaries, 這樣在檢查的時候就能夠通過

## No eXecute |the NX bit | Data Execution Prevention(DEP) 
- No eXecute |[the NX bit](https://zh.wikipedia.org/wiki/NX%E4%BD%8D%E5%85%83) | Data Execution Prevention(DEP) 
  - 先硬體支援
    - 「NX」這個名稱最先在AMD的Athlon 64、Opteron等支援AMD64的處理器上使用，並成為這些技術的代名詞。
    - 2001年，英特爾在自家的Itanium處理器加入這種技術，但未有在Pentium、Celeron、Xeon等x86處理器上使用。
    - 在AMD把NX應用在AMD64之後，英特爾也為Prescott版本的Pentium 4處理器加入類似技術，並以「執行禁用位元」（eXecute Disable，XD）的名義推出市場。
    - 在功能上，AMD的「NX」和Intel的「XD」完全相同，只是名稱不同。
    - The ARM architecture refers to the feature, which was introduced in ARMv6, as XN (execute never)
  - 軟體支援:Microsoft在Windows XP Service Pack 2上開始提供此技術的軟體支援 [Data Execution Prevention(DEP) 資料執行防止](https://docs.microsoft.com/en-us/windows/win32/memory/data-execution-prevention)。
    - [Microsoft Memory Management (Memory Management)](https://docs.microsoft.com/en-us/windows/win32/memory/memory-management) 
  - [Executable space protection](https://en.wikipedia.org/wiki/Executable_space_protection) 
  - 
  - NX (No-Execute) / DEP (Data Execution Prevention)
  - 可以寫的地方不能執行

|NX / DEP	|gcc 編譯參數|	execstack|
|----|-----|------|
|Enable|	DEFAULT|	execstack -s code|
|Disable|	gcc -z execstack code.c|	execstack -c code|

### 範例測試[教科書4-20]
```c

#include <unistd.h>
void vuln_func() {
  char buf[128];
  read(STDIN_FILENO, buf, 256);
}

int main (int argc, char *argv[]){
  vuln_func();
  write(STDOUT_FILENO,"Hello world! \n", 13);
}
```

- 關閉NX, canary,ASLR
``` 
root@kali:~/20211012/1014# echo 0 > /proc/sys/kernel/randomize_va_space 
root@kali:~/20211012/1014# gcc -fno-stack-protector -z execstack test_NX.c -o test_NX
root@kali:~/20211012/1014# pwn checksec test_NX
[*] '/root/20211012/1014/test_NX'
    Arch:     amd64-64-little
    RELRO:    Partial RELRO
    Stack:    No canary found
    NX:       NX disabled
    PIE:      PIE enabled
    RWX:      Has RWX segments  <====有一個RWX可執行區段 <==shellcode注入執行
```
- 啟用NX,關閉 canary,ASLR
```
gcc -fno-stack-protector -z noexecstack test_NX.c -o test_NX2
```
```
oot@kali:~/20211012/1014# gcc -fno-stack-protector -z noexecstack test_NX.c -o test_NX2
root@kali:~/20211012/1014# pwn checksec test_NX2
[*] '/root/20211012/1014/test_NX2'
    Arch:     amd64-64-little
    RELRO:    Partial RELRO
    Stack:    No canary found
    NX:       NX enabled
    PIE:      PIE enabled
```
## Relocation Read-Only (RELRO)

- Relocation Read-Only (RELRO)
  - [Linux 程序保護機制](https://oalieno.github.io/2019/03/21/security/pwn/protection/)

|RELRO	|說明|	gcc 編譯參數|
| -----| -----|------|
|No |GOT writable, link_map writable|gcc -Wl,-z,norelro code.c|
|Partial|GOT writable, link_map readonly|DEFAULT|
|Full |GOT read only, no link_map and dl_resolver pointer|gcc -Wl,-z,relro,-z,now code.c|

## [Address space layout randomization(ASLR)|[ Linux PaX project 2001]](https://en.wikipedia.org/wiki/Address_space_layout_randomization)

- [Address space layout randomization(ASLR)|[ Linux PaX project 2001]](https://en.wikipedia.org/wiki/Address_space_layout_randomization)
  - 位址空間組態隨機載入(Address space layout randomization，縮寫ASLR，又稱位址空間組態隨機化、位址空間布局隨機化）是一種防範記憶體損壞漏洞被利用的電腦安全技術。
  - ASLR通過隨機放置行程關鍵資料區域的定址空間來防止攻擊者能可靠地跳轉到記憶體的特定位置來利用函式。現代作業系統一般都加設這一機制，以防範惡意程式對已知位址進行Return-to-libc攻擊
  - Linux在核心版本2.6.12中已添加ASLR
  - Windows Server 2008，Windows 7，Windows Vista，Windows Server 2008 R2，Windows 10 1809，預設情況下啟用ASLR,但它僅適用於動態連結庫和可執行檔。[WIKI說明](https://zh.wikipedia.org/wiki/%E4%BD%8D%E5%9D%80%E7%A9%BA%E9%96%93%E9%85%8D%E7%BD%AE%E9%9A%A8%E6%A9%9F%E8%BC%89%E5%85%A5)
  -  Shacham, H.; Page, M.; Pfaff, B.; Goh, E. J.; Modadugu, N.; Boneh, D. (October 2004). "On the Effectiveness of Address-space Randomization". Proceedings of the 11th ACM Conference on Computer and Communications Security (PDF). pp. 298–307. doi:10.1145/1030083.1030124. ISBN 1-58113-961-6
  - [Configuring ASLR with randomize_va_space](https://linux-audit.com/linux-aslr-and-kernelrandomize_va_space-setting/)
```
0 - 表示關閉進程地址空間隨機化。
1 - 表示 mmap, stack, vdso 隨機化。
2 - 表示比 1 多了 heap 隨機化。
```
```
sudo -s echo 0 > /proc/sys/kernel/randomize_va_space
sudo sysctl -w kernel.randomize_va_space=0
```
### 範例測試[教科書4-43/44]
```c
#include <stdio.h>
#include <stdlib.h>
#include <dlfcn.h>

int main(){
  int stack;
  int *heap = malloc (sizeof (int));
  void *handle = dlopen("libc.so.6", RTLD_NOW | RTLD_GLOBAL);
 
  printf("executable: %p\n", &main);
  printf("system@plt: %p\n", &system);
  printf("heap: %p\n", heap);
  printf("stack: %p\n", &stack);
  printf ("libc: %p\n", handle);
  free (heap);
  return 0;
}
```

```
gcc aslr.c  -no-pie -fno-pie -ldl
```

- 關閉aslr ==> 執行兩次答案都一樣
```c
root@kali:~/20211012/1014# echo 0 > /proc/sys/kernel/randomize_va_space 

root@kali:~/20211012/1014# ./a.out
executable: 0x401162
system@plt: 0x401040
heap: 0x405260
stack: 0x7fffffffe1cc
libc: 0x7ffff7fb0500

root@kali:~/20211012/1014# ./a.out
executable: 0x401162
system@plt: 0x401040
heap: 0x405260
stack: 0x7fffffffe1cc
libc: 0x7ffff7fb0500
```

- 部分開啟aslr ==> stack 和libc  不一樣

```c
root@kali:~/20211012/1014# echo 1 > /proc/sys/kernel/randomize_va_space 

root@kali:~/20211012/1014# ./a.out
executable: 0x401162
system@plt: 0x401040
heap: 0x405260
stack: 0x7ffddaf7629c
libc: 0x7fa2a289d500


root@kali:~/20211012/1014# ./a.out
executable: 0x401162
system@plt: 0x401040
heap: 0x405260
stack: 0x7ffc5a2b633c
libc: 0x7f7e51a3a500
```

- 全部開啟aslr ==>  heap ,stack 和libc  不一樣

```c
root@kali:~/20211012/1014# echo 2 > /proc/sys/kernel/randomize_va_space 

root@kali:~/20211012/1014# ./a.out
executable: 0x401162
system@plt: 0x401040
heap: 0x11b4260
stack: 0x7ffeadd5c90c
libc: 0x7fa128ad7500


root@kali:~/20211012/1014# ./a.out
executable: 0x401162
system@plt: 0x401040
heap: 0x619260
stack: 0x7fff2f51fffc
libc: 0x7fa0b39c6500

```

## PIE
- ASLR 是—種作業系統層面的技術，而二進位程式本身是不支援隨機化載入的
  - 存在攻擊ASLR(繞過方式):ret2plt 、GOT hijacking、位址爆破
  
- 2003 年引入了 位置無關可執行檔(Position-Independent Executable, PIE)
  - 在應用層的編譯器上實現，透過將程式編譯為位置無關程式(Position-Independent Code, PIC) 
  - 使程式可以被載入到任意位置，就像是一個特殊的共用函數庫
  - 在PIE 和ASLR 同時開啟的情況下，攻擊者將對程式的記憶體分配一無所知，大大增加了利用難度。
  - PIE —定程度上會影響性能，因此在大多數作業系統上PIE 僅用於一些對安全性要求比較高的程式。

- 全部開啟aslr + PIE  ==>  全都不一樣

```
gcc aslr.c  -pie -fpie -ldl -o aslr_pie
```
```
root@kali:~/20211012/1014# gcc aslr.c  -pie -fpie -ldl -o aslr_pie

root@kali:~/20211012/1014# echo 2 > /proc/sys/kernel/randomize_va_space 


root@kali:~/20211012/1014# ./aslr_pie 
executable: 0x55f9acf62165
system@plt: 0x7f205bff1c50
heap: 0x55f9ade13260
stack: 0x7fff56e118ac
libc: 0x7f205c173500

root@kali:~/20211012/1014# ./aslr_pie 
executable: 0x55c262ab6165
system@plt: 0x7f7f2a38ec50
heap: 0x55c264284260
stack: 0x7fffdb63052c
libc: 0x7f7f2a510500


root@kali:~/20211012/1014# pwn checksec aslr_pie 
[*] '/root/20211012/1014/aslr_pie'
    Arch:     amd64-64-little
    RELRO:    Partial RELRO
    Stack:    No canary found
    NX:       NX enabled
    PIE:      PIE enabled
```
