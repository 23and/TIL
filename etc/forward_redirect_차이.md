#forward, redirect 차이

- 페이지 이동
- forward
 - 페이지를 바꿔주는 주체는 웹 컨테이너(tomcat)
 - request, response 등 내장 객체들의 공유가 가능하다.
 - 브라우저 상에서 url이 변하지 않는다.
 - 브라우저는 페이지 이동을 알지 못한다.
- redirect
 - 페이지를 바꿔주는 주체는 웹 브라우저(Internet Explorer)
 - 현재 페이지의 url이 변경되어 페이지가 바뀌는 것을 클라이언트가 인지한다.
 - 내부적으로 브라우저에게 다른 페이지로 이동할 것을 알리는 형태이다.
