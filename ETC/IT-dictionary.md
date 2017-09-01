용어|한 줄 설명|상세보기
:---:|:---:|:---:
컴파일(compile)|소스코드 파일을 기계어(binary)로 변환|[link](#컴파일)
빌드(build)|컴파일을 link하여 실행파일을 만드는 것|[link](#빌드)

## 컴파일
- `Compile is usually an action on a single file or group of files. The output of a compile step might be an executable or an object file or even a library of some sort.`
컴파일은 한 파일 또는 파일 그룹을 대상으로 행해진다. 컴파일의 산출물은 보통 실행파일이나 오브젝트 파일 또는 어떤 라이브러리가 될 수도 있다
- 컴파일은 소스코드 파일을 object 파일로 변환

## 빌드
- `Build usually means the entire process of getting a system ready for use.`
빌드는 보통 사용할 준비가 된 시스템으로 만드는 프로세스 전체를 뜻한다.
- 빌드는 관련된 모든 소스파일을 컴파일해서 object 파일을 만든 뒤, link를 해서 실행가능한 exe/bpl/bpk 등의 파일을 생성한다.
- 컴파일 vs 빌드
    - 컴파일 -> 링크 -> 빌드
    - 컴파일은 빌드의 부분집합

