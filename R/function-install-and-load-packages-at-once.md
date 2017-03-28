# 패키지 설치와 불러오기 한 번에 하는 법
(install-and-load-packages-at-once)
> "패키지 설치와 불러오기 한 번에 하자"

## 사용자 함수 생성
```r
InsLoadPkg <- function(input){
  uninstalledPackage <- input[!input %in% installed.packages()[, "Package"]]
  if (length(uninstalledPackage)) 
    install.packages(uninstalledPackage, dependencies = TRUE)
  sapply(input, library, character.only = TRUE)
}
```
## 사용법 
```
packages <- c("dplyr", "forcats")
InsLoadPkg(packages)
```
### ref
https://gist.github.com/stevenworthington/3178163
