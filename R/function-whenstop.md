# WhenStop 함수
> 특정한 수가 나올 때 멈추고 순서 반환
### 사용자 함수
```r
WhenStop1 <- function(x) {
  for (i in 1:length(x)) {
    if (x[i] == 1) break
  }
  return(i)
}

(WhenStop1(c(5,3,4,2,1)))
# [1] 5
```
참고
```r
which(c(5,3,4,2,1) == 1)
# [1] 5
```
