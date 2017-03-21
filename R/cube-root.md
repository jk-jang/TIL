# 세제곱근 계산 함수
(a-cube-root)
### 사용자 함수
```r
sqrt3 <- function(x){
  direction <- ifelse(x>0,1,
                      ifelse(x<0, -1, 0))
  x <- abs(x)^(1/3)
  x <- x*direction
  return(x)
}
```
