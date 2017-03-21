# 패키지 설치와 불러오기 한 번에 하는 법
(install-and-load-packages-at-once)
> "패키지 설치와 불러오기 한 번에 하자"

## 함수 생성
```r
InsLoadPkg <- function(pkg){
  new.pkg <- pkg[!(pkg %in% installed.packages()[, "Package"])]
  if (length(new.pkg)) 
    install.packages(new.pkg, dependencies = TRUE)
  sapply(pkg, require, character.only = TRUE)
}
```
## 사용법 
```
packages <- c("dplyr", "forcats")
InsLoadPkg(packages)
```
### ref
https://gist.github.com/stevenworthington/3178163
