# 범주명 바꾸기
(recode-factor-name)

> "`tesion`카테고리에 '*H*' 카테고리명을 '*High*'로 바꾸고 싶어"

### 데이터 설명
```r
str(warpbreaks)
## 'data.frame':    54 obs. of  3 variables:
##  $ breaks : num  26 30 54 25 70 52 51 26 67 18 ...
##  $ wool   : Factor w/ 2 levels "A","B": 1 1 1 1 1 1 1 1 1 1 ...
##  $ tension: Factor w/ 3 levels "L","M","H": 1 1 1 1 1 1 1 1 1 2 ...
```
데이터셋 warpbreaks(The Number of Breaks in Yarn during Weaving)은 wool과 tension에 따른 break를 나타냄

잘 모르겠으나 높은 질을 가진 wool이 break를 많이 내는데 tension에 따라 그게 조금씩 달라짐

### 패키지 이용
`forcats`, 범주형 변수처리 라이브러리 이용
(헤들리만듦)

### 패키지 설치
[패키지 설치와 불러오기 한 번에 하는 법](install-and-load-packages-at-once.md)
```r
InsLoadPkg <- function(input){
  uninstalledPackage <- input[!(input %in% installed.packages()[, "Package"])]
  if (length(uninstalledPackage)) 
    install.packages(uninstalledPackage, dependencies = TRUE)
  sapply(input, require, character.only = TRUE)
}
packages <- c("dplyr", "forcats")
InsLoadPkg(packages)
```
### 범수명 바꾸기
```r

warpbreaks <- warpbreaks%>%
  mutate(tension = fct_recode(tension,
                              "ToChaneTheName" = "H"))
levels(warpbreaks$tension)
## [1] "L"              "M"              "ToChaneTheName"
```
