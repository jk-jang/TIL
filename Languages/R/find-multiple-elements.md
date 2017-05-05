# 뽑고 싶은 단어 추출
(find-multiple-elements)
>_"`setosa` 와 `virginica` 범주를 가진 데이터를 가지고 오고 싶어"_ 

## 데이터 확인
```r
levels(iris$Species)
```
<pre><code>## [1] "setosa"     "versicolor" "virginica"</code></pre>
## 데이터 추출
```r
Dictionary = c("setosa", "virginica")
test = iris[iris$Species %in% Dictionary, ]
levels(test$Species)
```
<pre><code>## [1] "setosa"     "versicolor" "virginica"</code></pre>
#### 추가: `Species`의 Factor 레벨이 3단계이다. 더 깔끔하게 해주자
```r
test$Species = factor(test$Species)
levels(test$Species)
```
<pre><code>## [1] "setosa"    "virginica"</code></pre>
