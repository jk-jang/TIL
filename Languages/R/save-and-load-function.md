# function 파일로 저장하고 불러오기
(save-and-load-function.md)
```r
#function 파일로 저장하고 불러오기
# +1 함수 생성
test <- function(x){
  x <- x+1
  return(x)
}

#test.R에 저장함
dput(test, 'function-test.R')

#저장한 함수 불러옴
test <- dget('test.R')
```
