# save data for R users only
```r
#데이터 저장하는 방법(R용 데이터 저장)
#장점: csv 읽어왔을 때, 귀찮게 데이터 형식 변형안해줘도 된다.

save(iris,file='~/R만을 위한 데이터.RData')
load(file='R만을 위한 데이터.RData')
```
