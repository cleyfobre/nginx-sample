# Guide

### nginx.conf

- 최상위 conf 파일에 하위 conf 파일들을 including
  - include /etc/nginx/conf.d/*.conf;
  - /etc/nginx/conf.d 예하 모든 conf 파일을 읽는다. 

### test.conf

- line 1: upstream hello_myapp_com { server 127.0.0.1:8080; }
  - nginx에서 접속이 되었을 때 리다이렉팅할 서버는 upstream이라 하며
  - 이름은 hello_myapp_com과 같고
  - 서버의 주소는 127.0.0.1:8080 와 같다.
- line 9: server_name hello.myapp.com
  - 도메인 주소 hello.myapp.com로 접속이 되었을 때 리다이렉팅 한다.
- line 59: proxy_pass http://hello_myapp_com;
  - 이 nginx는 upstream에서 설정한 hello_myapp_com의 프록시 역할을 한다.