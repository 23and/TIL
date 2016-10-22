#spring x-frame-options deny

- spring x-frame-options deny iframe 접근 x
- 스프링시큐리티가 X-Frame-Options 헤더를 보안 이슈 해결을 위해 추가
- 해결
````
http.headers().frameOptions().disable()
````
- response.setHeader("X-Frame-Options","DENY")를 하지 말라는 뜻