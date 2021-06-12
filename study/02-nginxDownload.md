1. 사용하고 있는 OS에 맞는 Nginx를 다운 받는다.

2. 우분투에서 태스트를 하기 때문에 우분투 버전을 받는다.
https://docs.nginx.com/nginx/admin-guide/installing-nginx/installing-nginx-open-source/#installing-prebuilt-ubuntu-packages

3. installing
```
sudo apt-get update
```

```
sudo apt-get install nginx
```

```
sudo nginx -v
```
> nginx version: nginx/1.18.0 (Ubuntu)

```
sudo wget https://nginx.org/keys/nginx_signing.key
```

```
sudo apt-key add nginx_signing.key
```
