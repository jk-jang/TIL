# factorial 함수
### 사용자 함수
```r
myfact <- function(i){
  k <- 1
  while(i>1){
    k <- k*i
    i <- i - 1
  }
  return(k)
}

myfact(3)
# [1] 6
```
참고
```r
factorial(3)
# [1] 6

```
