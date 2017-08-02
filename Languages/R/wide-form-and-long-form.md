> 네트워크 분석에 썻던 거 같은데...

![](assets/markdown-img-paste-20170802101224324.png)

```r
data = c('a','b')
data
t(t(rep(unlist(strsplit(data,',')),each=2)))
```
