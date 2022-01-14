## Julia
- [Julia platform](https://julialang.org/downloads/)
- [官方網址](https://julialang.org/)
- Online Julia Compiler
  - [Execute Julia Online (Julia v0.6.0)](https://www.tutorialspoint.com/execute_julia_online.php) 
  - [超強的replit Julia online editor, IDE, compiler, interpreter, and REPL](https://replit.com/languages/julia)

## 參考書籍
- [Learning Julia(2017)](https://www.packtpub.com/product/learning-julia/9781785883279) [GITHUB](https://github.com/packtpublishing/learning-julia)
- [Julia 1.0 Programming Complete Reference Guide(2019)](https://www.packtpub.com/product/julia-1-0-programming-complete-reference-guide/9781838822248) [GITHUB]()
  - This Learning Path includes content from the following Packt products:
  - Julia 1.0 Programming - Second Edition by Ivo Balbaert
  - Julia Programming Projects by Adrian Salceanu
- [Julia 1.0 Programming Cookbook(2018)](https://www.packtpub.com/product/julia-1-0-programming-cookbook/9781788998369)  [GITHUB](https://github.com/packtpublishing/julia-1.0-programming-cookbook)
- [Julia for Data Science(2016)](https://www.packtpub.com/product/julia-for-data-science/9781785289699) [GITHUB](https://github.com/packtpublishing/julia-for-data-science)
- [Hands-On Computer Vision with Julia(2018)](https://www.packtpub.com/product/hands-on-computer-vision-with-julia/9781788998796) [GITHUB](https://github.com/packtpublishing/hands-on-computer-vision-with-julia)

## Hands-On-Computer-Vision-with-Julia/Chapter01/7_rotating_images.jl
```julia
using Images, CoordinateTransformations, ImageView

img = load("sample-images/cats-3061372_640.jpg");
tfm = LinearMap(RotMatrix(-pi/3)) # rotate by -60 degrees 
img = warp(img, tfm)
imshow(img)
```
