# path 의미

> 명령을 실행할 수 있는 경로

cmd에서 `echo %PATH%`를 입력해보자
![](assets/markdown-img-paste-20170629142802293.png)
-> 경로들이 ;로 구분되어있음

`hello`를 입력해보자
![](assets/markdown-img-paste-20170629143137759.png)
왜 안될까?

;로 분리된 경로 하나하나를 돌아다니면서 `hello`를 찾아다녔는데 hello가 없어서 저런 메세지가 출력된 것이다.
