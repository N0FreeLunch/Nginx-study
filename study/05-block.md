## 지시어 블록 block
#### example
```
events {
  worker_connections 1024;
}
```
#### description
- events 모듈이 작동할 때 블록{} 안 지시어들이 세팅 됨
- 서버 전체로 세팅할 것은 어떤 블록에도 들어가지 않는 상태여야 함, 어떤 블록 안에도 들어 있지 않는 최상의 블록의 상태를 main 블록이라고 함
- 블록을 사용하는 지시어는 nginx에 정해져 있다.
#### 지시어 블록 중첩 example
```
http {
  server {
    listen 80;
    server_name example.com;
    access_log /var/log/nginx/example.com.log;
    location ^~ /admin/ {
      index index.php;
    }
  }
}
```


### http
#### Syntax
```
http {

}
```
#### description
- 서버의 웹 사이트를 구성할 때 사용하는 블록
- server 블록 등 다양한 지시어를 포함한다.

### server
https://nginx.org/en/docs/http/ngx_http_core_module.html#server
#### Syntax
```
server { ... }
```
Context:	http
#### description
- context는 대상이 어느 모듈 안에 포함되는지를 의미한다. http 모듈 블럭 안에서 작동한다는 의미
- 가상 서버를 설정한다. IP 베이스의 서버와 이름(도메인+서브도메인) 베이스의 서버를 가상 서버를 구성한다.


## 상속
```
http {
  server {
    listen 80;
    server_name example.com;
    access_log /var/log/nginx/example.com.log;
    location ^~ /admin/ {
      index index.php;
    }
  }
}
```
#### description
- server블록에 설정 된 access_log의 설정은 location 블락으로 설정 된 부분에도 적용 된다.
- [access_log](https://nginx.org/en/docs/http/ngx_http_log_module.html#access_log)의 context를 보면 'http, server, location, if in location, limit_except'으로 되어 있다. 하위 컨텍스트에 적용될 수 있는 지시어는 하위 컨텍스트에 상속 되어 적용 된다.
- 하위 컨텍스트에서 상위 지시자를 사용하지 않고 싶다면??


##
```
```

```
```
