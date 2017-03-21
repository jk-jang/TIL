# factorial 함수
### 사용자 함수
```r
myfact <- function(x){
  fact <- 1
  i <- x
  while(i > 1){
    fact <- fact*i
    i <- i-1
  }
  return(fact)
}

myfact(3)
# [1] 6
```
참고
```r
factorial(3)
# [1] 6

```
