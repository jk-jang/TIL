Run tensorflow in R

# Step0. Requirements
 - anaconda
 - tensorflow

cf. [Install tensorflow in Anaconda](/platform/anaconda/install-tensorflow-in-anaconda.md)

# Step1. Run anaconda
```r
#install.packages("reticulate","tensorflow")
library(reticulate)

# 가상환경명 입력
use_condaenv("tf")

library(tensorflow)
```

# Step2. 확인
```r
py_config()
```
