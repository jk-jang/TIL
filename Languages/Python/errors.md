TOC

에러명|해결방법|상세보기
:---:|:---:|:---:
build/compile|python window binary|[link](#build/compile)
Encode(latin-1)|?charset=utf8|[link](#UnicodeEncodeError(latin-1))


<a id='build/compile'></a>
### build/compile

- 에러

![](img/2017-09-01-09-20-19.png)

> 이런거 나오면 다 빌드에러

- 원인

라이브러리를 compile/build 한후에 올리는 경우랑 하지않은채로 올리는 경우에 저러한 에러남, 리눅스같은 경우는 알아서 처리해주는데 윈도우는 처리 잘 안됨

> 사실 제대로 모르겠음

- 해결방법

1. `python windows binary` 검색

2. `Index by date`에서 원하는 라이브러리 찾기
![](img/2017-09-01-09-26-58.png)

3. python version + 윈도우 버전 확인 후 다운로드
![](img/2017-09-01-09-29-05.png)

4. 다운로드 경로에서 `pip install mysqlclient-1.3.10-cp36-cp36m-win_amd64.whl` 입력

<a id='UnicodeEncodeError(latin-1)'></a>
### UnicodeEncodeError(latin-1)
- 에러
![](img/2017-09-01-13-33-12.png)

- 원인

한글... 

- 해결방법

디비명 뒤에 ?charset=utf8붙여줌
```python
from sqlalchemy import create_engine
engine = create_engine("mysql+mysqldb://user:password@host/db_name?charset=utf8")
```