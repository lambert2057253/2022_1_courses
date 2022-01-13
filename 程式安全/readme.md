# 從程式開發到程式安全  From coding to Security
- 程式安全(本課程) ==> 如何分析程式的漏洞與安全修補
  - 原始碼檢測
  - Fuzzer 
- 安全程式開發(Secure coding) ==> 如何開發具有安全的程式

# Topics
- C security
- C++ Security
- Python Security
- JAVA Security
- Ruby Security

# C 程式開發
- [Visual Studio code官方說明文獻](https://code.visualstudio.com/docs)
  - [Visual Studio Code Crash Course](https://www.youtube.com/watch?v=WPqXP_kLzpo) 
  - [Extensions for the Visual Studio family of products](https://marketplace.visualstudio.com/vscode)
    - Snyk Vulnerability Scanner 
  - [How to Install MinGW | GCC Toolset for C and C++ Programming | Setting Path variable on Windows 10](https://www.youtube.com/watch?v=guM4XS43m4I)
  - [How to set up VS Code for C++ and make your First Program? + How I use AI to help me code faster](https://www.youtube.com/watch?v=YgKnzIV4uME)
- 使用Windows版visual studio code開發 C程式
  - [How to Download and Install Visual Studio Code ( VS Code ) on Windows 10](https://www.youtube.com/watch?v=JGsyJI8XG0Y)
  - [How to Set up Visual Studio Code for C and C++ Programming](https://www.youtube.com/watch?v=77v-Poud_io)
  - [(微軟)Configure VS Code for Microsoft C++](https://code.visualstudio.com/docs/cpp/config-msvc)
  - [(微軟)Using GCC with MinGW](https://code.visualstudio.com/docs/cpp/config-mingw)
  - [(微軟)C/C++ for Visual Studio Code](https://code.visualstudio.com/docs/languages/cpp)
- 使用Linux版visual studio code開發 C程式
  - [Download Visual Studio Code](https://code.visualstudio.com/download) 
  - [Visual Studio Code on Linux](https://code.visualstudio.com/docs/setup/linux)
  - [How to install Visual Studio Code on Ubuntu Linux](https://www.youtube.com/watch?v=uYE0XrM-VZA)
- [Free eBook - Extreme C(2019)](https://www.packtpub.com/free-ebook/extreme-c/9781789343625)
  - [GITHUB](https://github.com/packtpublishing/extreme-c)
- [Learn C Programming](https://www.packtpub.com/product/learn-c-programming/9781789349917)
  - [GITHUB](https://github.com/PacktPublishing/Learn-C-Programming)
- [Practical C Programming(2020)](https://www.packtpub.com/product/practical-c-programming/9781838641108)
  - [GITHUB](https://github.com/packtpublishing/practical-c-programming)
- [C語言程序設計 : 現代方法, 2/e (修訂版)  C Programming: A Modern Approach, 2/e K. N. King 呂秀鋒，黃倩譯](https://www.tenlong.com.tw/products/9787115565198)
  - [程式下載](http://knking.com/books/c2/index.html)
- [Hands-On Network Programming with C(2019)](https://www.packtpub.com/product/hands-on-network-programming-with-c/9781789349863)
  - [GITHUB](https://github.com/packtpublishing/hands-on-network-programming-with-c)
- [Hands-On System Programming with Linux(2018)](https://www.packtpub.com/product/hands-on-system-programming-with-linux/9781788998475)
  - [GITHUB](https://github.com/PacktPublishing/Hands-on-System-Programming-with-Linux)
- [uhub/awesome-c](https://github.com/uhub/awesome-c)
- [oz123/awesome-c](https://github.com/oz123/awesome-c)
- 基本程式開發
- 系統程式(System programming)
- 網路程式(network Programming)
- 資料結構與演算法


## linux binary analysis and security
- [Advanced C and C++ Compiling (Paperback)](https://www.tenlong.com.tw/products/9781430266679)
- [Practical Binary Analysis](https://nostarch.com/binaryanalysis)
  - [教科書(簡中譯本)二進制分析實戰](https://www.tenlong.com.tw/products/9787115556936)
  - [官方網址](https://nostarch.com/binaryanalysis) 
  - [程式與VM下載](https://practicalbinaryanalysis.com/)
- [Binary Analysis Cookbook (2019)](https://www.packtpub.com/product/binary-analysis-cookbook/9781789807608)
  - [GITHUB](https://github.com/packtpublishing/binary-analysis-cookbook)

## 逆向工程(Reverse Engineering)
- [加密與解密, 4/e 加密与解密（第4版)段鋼](https://www.tenlong.com.tw/products/9787121336928)
- [Mastering Reverse Engineering: Re-engineer your ethical hacking skills(Reginald Wong,2018)]()
- [Ghidra Software Reverse Engineering for Beginners: Analyze, identify, and avoid malicious code and potential threats in your networks and systems(2021)]()
- [C++ 反彙編與逆向分析技術揭秘, 2/e](https://www.tenlong.com.tw/products/9787111689911)


## Malware Analysis 
- [Malware Analysis Techniques(2021)](https://www.packtpub.com/product/malware-analysis-techniques/9781839212277)
  - [GITHUB](https://github.com/PacktPublishing/Malware-Analysis-Techniques)
- [Mastering Malware Analysis(2019)](https://www.packtpub.com/product/mastering-malware-analysis/9781789610789)
  - [GITHUB](https://github.com/packtpublishing/mastering-malware-analysis)
- [Learning Malware Analysis(2018)](https://www.packtpub.com/product/learning-malware-analysis/9781788392501)
- [Windows Malware Analysis Essentials(2015)](https://www.packtpub.com/product/windows-malware-analysis-essentials/9781785281518)



#### Malware Analysis:Qiling
- Qiling is an advanced binary emulation framework written in python and based on Unicorn engine.
- It supports multiple platform (Windows, MacOS, Linux, BSD, UEFI) and multiple architectures (X86, X86_64, Arm, Arm64, MIPS).
- Qiling is designed as a higher level framework, that leverages Unicorn to emulate CPU instructions
- but Qiling understands OS as it has executable format loaders (for PE, MachO & ELF at the moment), dynamic linkers (so we can load & relocate shared libraries), syscall & IO handlers. 
- For this reason, Qiling can run executable binaries that normally runs in native OS.
- [Qiling Documentation](https://docs.qiling.io/en/latest/)
- [Qiling For Malware Analysis: Part 1](https://n1ght-w0lf.github.io/tutorials/qiling-for-malware-analysis-part-1/)
- [Qiling For Malware Analysis: Part 2](https://n1ght-w0lf.github.io/tutorials/qiling-for-malware-analysis-part-2/)

### Malware Analysis: 範例分析
- [Deep Analysis of RogueRobin Trojan (DarkHydrus APT)](https://n1ght-w0lf.github.io/malware%20analysis/roguerobin-trojan/)
- [Deep Analysis of Phobos Ransomware](https://n1ght-w0lf.github.io/malware%20analysis/phobos-ransomware/)
- [Deep Analysis of KSLØT Keylogger (Turla APT)](https://n1ght-w0lf.github.io/malware%20analysis/ksl0t-keylogger/)

## PWN
- [駭客們好自為之：CTF 大賽 PWN 奪旗技術大展(2021)](https://www.tenlong.com.tw/products/9789860776034)

## 安全程式開發 ==> 如何開發具有安全的程式

## C++
- [Modern C++ Programming Cookbook - Second Edition(2020)](https://www.packtpub.com/product/modern-c-programming-cookbook-second-edition/9781800208988)
  - [GITHUB](https://github.com/PacktPublishing/Modern-CPP-Programming-Cookbook-Second-Edition/)
- [The C++ Workshop(2020)](https://www.packtpub.com/product/the-c-workshop/9781839216626)
  - [GITHUB](https://github.com/PacktWorkshops/The-CPP-Workshop) 
- [經典 C++ Primer, 5/e (繁體中文版) Stanley B. Lippman等 黃銘偉 碁峰資訊](https://www.tenlong.com.tw/products/9789865021726)
- [Expert C++(2020)](https://www.packtpub.com/product/expert-c/9781838552657)
  - [GITHUB](https://github.com/PacktPublishing/Expert-CPP)
- [Advanced C++ Programming Cookbook(2020)](https://www.packtpub.com/product/advanced-c-programming-cookbook/9781838559915)
  - [GITHUB](https://github.com/packtpublishing/advanced-cpp-programming-cookbook) 
- [C 和 C++ 安全編碼(原書第2版) (Secure Coding in C and C++, 2/e) 华章程序员书库:C和C++安全编码(原书第2版) 塞克德 (Robert C.Seacord)](https://www.tenlong.com.tw/products/9787111442790)


### C++ 標準庫
- [C++ 標準庫－學習教本與參考工具, 2/e (精裝) (The C++ Standard Library: A Tutorial and Reference, 2/e) Nicolai M. Josuttis 著、侯捷 譯(2014)](https://www.tenlong.com.tw/products/9789863474395)
- [Mastering the C++17 STL(2017)](https://www.packtpub.com/product/mastering-the-c-17-stl/9781787126824)
  - [GITHUB](https://github.com/packtpublishing/mastering-the-cpp17-stl)

### C++資料結構與演算法

- [C++ Data Structures and Algorithms(2018)](https://www.packtpub.com/product/c-data-structures-and-algorithms/9781788835213)
  - [GITHUB](https://github.com/packtpublishing/-c-8-data-structures-and-algorithms)


### C++應用
- [C++ System Programming Cookbook(2020)](https://www.packtpub.com/product/c-system-programming-cookbook/9781838646554)
  - [GITHUB](https://github.com/packtpublishing/c-system-programming-cookbook)
- [Hands-On Machine Learning with C++(2020)](https://www.packtpub.com/product/hands-on-machine-learning-with-c/9781789955330)
  - [GITHUB](https://github.com/packtpublishing/hands-on-machine-learning-with-cpp)
  - Shogun library

- [高手才用 C語言：Windows C/C++ 加密解密實戰(朱晨冰、李建英)](https://www.tenlong.com.tw/products/9789860776348)

- [Building Computer Vision Projects with OpenCV 4 and C++(2019)](https://www.packtpub.com/product/building-computer-vision-projects-with-opencv-4-and-c/9781838644673)
  - [GITHUB](https://github.com/packtpublishing/hands-on-machine-learning-with-cpp)


## C#

- [Learn C# Programming(2020)](https://www.packtpub.com/product/learn-c-programming/9781789805864)
  - [GITHUB](https://github.com/PacktPublishing/Learn-C-Sharp-Programming)

## Julia
- [Julia platform](https://julialang.org/downloads/)
- [官方網址](https://julialang.org/)
- Online Julia Compiler
  - [Execute Julia Online (Julia v0.6.0)](https://www.tutorialspoint.com/execute_julia_online.php) 
  - [超強的replit Julia online editor, IDE, compiler, interpreter, and REPL](https://replit.com/languages/julia)
- [Learning Julia(2017)](https://www.packtpub.com/product/learning-julia/9781785883279) [GITHUB](https://github.com/packtpublishing/learning-julia)
- [Julia 1.0 Programming Complete Reference Guide(2019)](https://www.packtpub.com/product/julia-1-0-programming-complete-reference-guide/9781838822248) [GITHUB]()
  - This Learning Path includes content from the following Packt products:
  - Julia 1.0 Programming - Second Edition by Ivo Balbaert
  - Julia Programming Projects by Adrian Salceanu
- [Julia 1.0 Programming Cookbook(2018)](https://www.packtpub.com/product/julia-1-0-programming-cookbook/9781788998369)  [GITHUB](https://github.com/packtpublishing/julia-1.0-programming-cookbook)
- [Julia for Data Science(2016)](https://www.packtpub.com/product/julia-for-data-science/9781785289699) [GITHUB](https://github.com/packtpublishing/julia-for-data-science)
- [Hands-On Computer Vision with Julia(2018)](https://www.packtpub.com/product/hands-on-computer-vision-with-julia/9781788998796) [GITHUB](https://github.com/packtpublishing/hands-on-computer-vision-with-julia)
## GO
- [Download Go for Windows](https://go.dev/doc/install)
  - $ go version
  - go run arrays.go
- Online go Compiler
  - [Go Playground](https://go.dev/play/) 
  - [Execute GO Language Online (Go v1.8.3)](https://www.tutorialspoint.com/execute_golang_online.php)
  - [Online Go Lang Compiler](https://www.onlinegdb.com/online_go_compiler)
- [Documentation](https://go.dev/doc/)
- [Learn Data Structures and Algorithms with Golang(2019)](https://www.packtpub.com/product/learn-data-structures-and-algorithms-with-golang/9781789618501)
  - [GITHUB](https://github.com/packtpublishing/learn-data-structures-and-algorithms-with-golang)
- [Go 黑帽子 : 滲透測試編程之道 Tom Steele,Chris Patten,Dan Kottmann著 賈玉彬 朱錢杭 譯](https://www.tenlong.com.tw/products/9787302588245)

## Ruby on Rail ==> 開發 metasploit 模組
- Online go Compiler
  - [超強的OneCompiler](https://onecompiler.com/ruby)
    - 也可以學習MYSQL  [MongoDB](https://onecompiler.com/mongodb)  [Redis](https://onecompiler.com/redis)
  - [Online Ruby Compiler](https://www.onlinegdb.com/online_ruby_compiler)
  - [Execute Ruby Online (Ruby v2.4.1)](https://www.tutorialspoint.com/execute_ruby_online.php)
- [The Ruby Workshop(2019)](https://www.packtpub.com/product/the-ruby-workshop/9781838642365) 
- [Comprehensive Ruby Programming(2017)](https://www.packtpub.com/product/comprehensive-ruby-programming/9781787280649)  [GITHUB](https://github.com/packtpublishing/comprehensive-ruby-programming)
- [Polished Ruby Programming(2021)](https://www.packtpub.com/product/polished-ruby-programming/9781801072724) [GITHUB](https://github.com/PacktPublishing/Polished-Ruby-Programming)
- [Cloning Internet Applications with Ruby(2010)](https://www.packtpub.com/product/cloning-internet-applications-with-ruby/9781849511063)
- [Ruby on Rails應用開發最強教科書 (日)太田智彬//寺下翔太//手塚亮(2021)](https://www.tenlong.com.tw/products/9787515364155)
- [Build a Cryptocurrency News Site with Ruby on Rails Video(2019)](https://www.packtpub.com/product/build-a-cryptocurrency-news-site-with-ruby-on-rails-video/9781839212925)


# [RUST](https://www.rust-lang.org/)
- Rust is installed and managed by the `rustup` tool
- On Windows, download and run rustup-init.exe
- [下載與安裝](https://forge.rust-lang.org/infra/other-installation-methods.html)
- Online Rust Compiler
  - [Online Rust Compiler](https://www.onlinegdb.com/online_rust_compiler)
  - [Compile and Execute Rust Online (Rust v1.19.0)](https://www.tutorialspoint.com/compile_rust_online.php)
  - [Rust Playground](https://play.rust-lang.org/)
    - 可以顯示 LLVM IR 
- RUST學習資源
- [Rust for Absolute Beginners: Learn Rust in 4 Hours Video(2021)](https://www.packtpub.com/product/rust-for-absolute-beginners-learn-rust-in-4-hours-video/9781801818179)
  - [GITHUB](https://github.com/PacktPublishing/Rust-for-Beginners-Learn-Rust-in-4-Hours)
- [Rust 實戰：從入門到精通 (Beginning Rust: From Novice to Professional) Carlo Milanesi(2021)](https://www.tenlong.com.tw/products/9787111683674)
- [Mastering Rust - Second Edition(2019)](https://www.packtpub.com/product/mastering-rust-second-edition/9781789346572)
  - [GITHUB](https://github.com/packtpublishing/mastering-rust)
- [Rust Programming Cookbook(2019)](https://www.packtpub.com/product/rust-programming-cookbook/9781789530667)
  - [GITHUB](https://github.com/packtpublishing/rust-programming-cookbook)
- [Rust Programming By Example(2018)](https://www.packtpub.com/product/rust-programming-by-example/9781788390637)
  - [GITHUB](https://github.com/packtpublishing/rust-programming-by-example)
- [Network Programming with Rust(2018)](https://www.packtpub.com/product/network-programming-with-rust/9781788624893)
  - [GITHUB](https://github.com/packtpublishing/network-programming-with-rust)
- [Practical System Programming for Rust Developers(2020)](https://www.packtpub.com/product/practical-system-programming-for-rust-developers/9781800560963) 
  - [GITHUB](https://github.com/PacktPublishing/Practical-System-Programming-for-Rust-Developers) 
- [Hands-On Data Structures and Algorithms with Rust](https://www.packtpub.com/product/hands-on-data-structures-and-algorithms-with-rust/9781788995528)
  - [GITHUB](https://github.com/packtpublishing/hands-on-data-structures-and-algorithms-with-rust)
- RUSTseciruty
  - [CVE漏洞報告](https://www.cvedetails.com/vulnerability-list/vendor_id-19029/product_id-48677/Rust-lang-Rust.html)
  - [List of security-related projects](https://github.com/rust-secure-code/projects)
