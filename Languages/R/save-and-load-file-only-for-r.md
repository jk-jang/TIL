# R 파일로 저장하고 불러오기
(save-and-load-function.md)

> R에서만 읽고 쓰기 할 수 있음

> 교육때 파일 리드 문제 해결 가능

```r
save(iris,file='R만을 위한 데이터.RData')
```
파일이 생성됨</br>
![](assets/markdown-img-paste-2017080113444709.png)

```r
load("~/R만을 위한 데이터.RData")
```
