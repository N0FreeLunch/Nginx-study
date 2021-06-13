# nginx.conf

## module
https://nginx.org/en/docs/
- Nginx 도큐먼트를 보면 modules가 있다.
- 모듈 그룹, 도메인별 modules를 모아 두었으므로 필요한 module을 각 도메인에서 확인하자.

## ngx_core_module
http://nginx.org/en/docs/ngx_core_module.html
- 내용을 다루었다.

### user
http://nginx.org/en/docs/ngx_core_module.html#user
#### Syntax
```
user user [group];
```
Context:	main
#### example
```
user nobody;
```
```
user nobody nobody;
```
#### description
- 엔진엑스를 실행할 수 있는 리눅스 유저 또는 유저 그룹
- 리눅스 유저 및 유저 그룹에 정의된 대상을 적어 주면 된다.
- nobody는 리눅스의 어느 유저라도 실행할 수 있다는 권한을 부여한 것
- default는 nobody


### worker_process
http://nginx.org/en/docs/ngx_core_module.html#worker_processes
#### Syntax
```
worker_processes number | auto;
```
Context:	main
#### example
```
worker_process 1;
```
```
worker_process auto;
```
#### description
- 사용할 프로세스를 설정한다.
- CPU 코어 뿐만 아니라, 디스크 사용량 및 로드에 따라 달라지기 때문에 모니터링 하면서 최적 값을 찾아야 한다.
- auto : 자동적 감지, 비교적 신 버전 부터 지원


### include
http://nginx.org/en/docs/ngx_core_module.html#include
#### Syntax
```
include file | mask;
```
Context:	any
### example
```
include mime.types;
```
```
include other_setting.conf
```
```
include mime.types;
include vhosts/*.conf;
```
#### description
- 지정 된 파일을 include한다.
- Nginx config 파일만 인클루드 가능하다.
- 마스크는 파일 권한 777 755 같은 것을 의미하는 것으로 보임 777(111 111 111) 755(111 100 100) 이 부분에 대해서 정확한 정보를 찾으면 업데이트
- 와일드 카드 표기를 허용한다. *
```
include sites/*.conf;
```
