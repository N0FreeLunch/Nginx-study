## 구성 파일 표준의 부재
1. config 파일에는 특별하게 정해진 표준이 없다. apache, nginx, php의 ini등 config 파일을 만들기 위한 통합된 표준이 없기 때문에 nginx를 설정하기 위해서는 nginx만의 설정방식을 알아야 한다.

2. 다른 config 표준에 비해 엔진엑스 구성 방식의 표준은 단순하다.


### 엔진엑스의 주석
```
#
```


### nginx.conf
nginx를 패키지 관리자로 설치했을 때
```
/etc/nginx
```
만약 직접 빌드 했다면
```
/usr/local/nginx/conf/nginx.conf
```
를 사용한다.


## document 용어
- context : 어떤 모듈의 블록 안에서 설정 가능한지 설정
