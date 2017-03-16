
## 식별자(Identifiers)
> 식별자(identifiers)안에는 밑줄 ( _ )이나 하이픈 ( - )을 사용하지마.

변수(variable) 이름으로 선호되는 형식은 모두 소문자이고 점으로 구분된 단어 (variable.name) 이지만, variableName 도 허용합니다
함수 이름 맨 앞글자는 대문자로 하고 점이 없이 (FunctionName) 과 같이 정합니다; 

```r
variable.name을 선호하지만, variableName 도 받아드립니다. 
GOOD: avg.clicks 
OK: avgClicks 
BAD: avg_Clicks
```

**함수 이름** 
```r
GOOD: CalculateAvgClicks 
BAD: calculate_avg_clicks , calculateAvgClicks 
함수의 이름은 동사로 만듭니다. 
```

---

## 공백 넣기(Spacing)
> 모든 이진 연산자 (=, +, -, <-, 등) 앞뒤에 공백을 넣 

```r
GOOD:
tab.prior <- table(df[df$days.from.opt < 0, "campaign.id"])
total <- sum(x[, 1])
total <- sum(x[1, ])
```

```r
BAD:
tab.prior <- table(df[df$days.from.opt<0, "campaign.id"])  # '<'주위에 공백이 필요합니다.
tab.prior <- table(df[df$days.from.opt < 0,"campaign.id"])  # 쉼표 뒤에 공백 한 칸를 넣으세요
tab.prior<- table(df[df$days.from.opt < 0, "campaign.id"])  #  <- 앞에 공백 한 칸를 넣으세요
tab.prior<-table(df[df$days.from.opt < 0, "campaign.id"])  #  <- 주위에 공백이 필요합니다
total <- sum(x[ ,1])  #  쉼표 앞이 아니라 뒤에 공백 한 칸를 넣으세요
```

---

## else를 괄호로 둘러싸기(Surround else with braces)
>else 명령문은 중괄호로 항상 같은 줄에서 둘러싸여야 합니다.

```r
GOOD:
if (condition) {
  one or more lines
} else {
  one or more lines
}

BAD:
if (condition) {
  one or more lines
}
else {
  one or more lines
}
```

### ref
[r style guide](http://dialektike.github.io/Rguide.xml#attach)
