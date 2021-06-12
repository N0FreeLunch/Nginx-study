# nginx.conf

### user
```
user nobody;
```

```
user arg1 arg2
```
arg1 :
arg2 :

### worker_process
http://nginx.org/en/docs/ngx_core_module.html#worker_processes
```
worker_process 1;
```
```
worker_process auto;
```
설정 가능 값으로는 : 숫자, auto
- 사용할 프로세스를 설정한다.
- CPU 코어 뿐만 아니라, 디스크 사용량 및 로드에 따라 달라지기 때문에 모니터링 하면서 최적 값을 찾아야 한다.
- auto : 자동적 감지
- 보통 auto를 사용한다.
