# TIL
>Today I Learned

작성 규칙은 GFM[(Github-Flavoured Markdown)](https://help.github.com/categories/writing-on-github)을 사용(확장자`.md`)
- 파일명은 영어(소문자)
- [contents name]참조명은(#소문자-소문자, *참조할 컨텐츠 이름이 대문자라 할지라도*)
- 그림 code example
```html
<p align="center">
 <img src="img/blahblah.png">
</p>
```
- 특수문자(/,etc) link code
```html
[link](#build/compile)

링크할 부분 위에 아래 코드 삽입
<a id='build/compile'></a>
```

- Keyboard Icons in Markdown
```html
<kbd>Alt</kbd>+<kbd>F2</kbd>
```
- [라텍스](http://latex.codecogs.com)
> can not render LaTex in GFM

- 테이블 형식
```
Month|Day
:---:|:---:
Mar|01
Apr|01
Apr|02
```

## Categories
- [Idea](#idea)
- [Languages](#languages)
- [Mathematics & Statistics](#mathematics&statistics)
- [Platform](#platform)
- [Software library](#software-library)
- [Collect and Read](#collect-and-read)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Algorism](#algorism)
- [Model Evaluation](#model-evaluation)
- [Visualization](#visualization)
- [ETC](#etc)

---

## Idea
- [Trade(KOTRA)](https://docs.google.com/document/d/1D6C8O8y15iZ3V6sgRImB8eWNcc-ExLQjCngb-9G-_u4)

## Languages
- 코드 작성법 - [R](Languages/R/R-code-style-guide.md)
- [R vs Python](Languages/python-vs-r.md)
- Tip [Python](Languages/Python/tip.ipynb)
- Variable [Python](Languages/Python/basic-01-variable.ipynb)
- Data Type
  - String [Python](Languages/Python/basic-02-datatype-string.ipynb)
- Data Structure
- Errors [Python](Languages/Python/errors.md)

## Mathematics & Statistics

## Platform

- Docker
  - [Install Docker for Window](Platforms/docker/install-docker-for-window.md)
  - [Install tensorflow in Docker](Platforms/docker/install-tensorflow-in-docker.md)
- Anaconda
  - [Install tensorflow in Anaconda](Platforms/anaconda/install-tensorflow-in-anaconda.md)

- Git
  - [Install Git and Setting](Platforms/git/install-git-and-setting.md)
  - [Use Git in Github](Platforms/git/use-git-in-github.md)
  - [Use Git by Atom](Platforms/git/use-git-in-atom.md)
  - [Use Git by Visual Studio Code](Platforms/git/use-git-in-vscode.md)
  - [Use Git in AWS CodeCommit](Platforms/git/use-git-in-aws-codecommit.md)

## Software Library

- Tensorflow

## Collect and Read

- 크롤러
  - 데이터 스토어 FILE DATA - [R](Languages/R/crawler-datastore.md)
  - [무역협회 실시간환율정보](Languages/Python/crawler-kita.md)
  - [실시간유가정보](Languages/Python/crawler-oil.md)
- [패키지 설치와 불러오기 한 번에 하는 법](Languages/R/function-install-and-load-packages-at-once.md)
- [데이터 저장](Languages/R/how-to-save.md)
- [function을 파일로 저장하고 불러오기](Languages/R/save-and-load-function.md)
- [Run tensorflow in R](Languages/R/run-tensorflow-in-r.md)
- [save and load file only for R](Languages/R/save-and-load-file-only-for-r.md)
## Exploratory Data Analysis / Pre-processing
- [finding mutiple elements in a vector](Languages/R/find-multiple-elements.md)
- [세제곱근 계산 함수 만들기](Languages/R/function-cube-root.md)
- [팩토리얼 함수 만들기](Languages/R/function-factorial.md)
- [When Stop 함수 만들기](Languages/R/function-whenstop.md)
- [범주명 바꾸기](Languages/R/recode-factor-name.md)
- Transform
  - [(Package-tidyr)wide form and long form](Languages/R/package-tidyr.md)
  - [wide form and long form](Languages/R/wide-form-and-long-form.md)
- Feature
- Dimension reduction
  - [Theory](Theory/dimension-reduction.md)

## Algorithm
- Supervised Learning
- Unsupervised Learning
  - Clustering
    - K-means
- Deep Learning
- Reinforcement Learning

## Model Evaluation
- 적절한 군집 개수 찾기 - [R](Languages/R/total_within_cluster_sum_of_squares.md)


## Visualization
- Put comma in graph - [R](Languages/R/visualization-tips.md)

## ETC

- [IT dictionary](ETC/IT-dictionary.md)
- [Install Window 10 via USB on Samsung laptop](ETC/install-window10-via-usb-on-samsung.md)
- [PATH](ETC/path.md)
- [Greek](ETC/greek.md)

##### Other TIL Collections

Inspired by

- [@channprj](https://github.com/channprj/TIL)
- [@milooy](https://github.com/milooy/TIL)
