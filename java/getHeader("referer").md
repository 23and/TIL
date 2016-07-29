#request method getHeader("headerName")

- 이전 페이지를 가져오는 방법을 검색해보다 getHeader("headerName")를 알게되었다. 하지만 a 태그, form action값에 의한 이동이 아닌 경우에는 referer이 전달되지 않기 때문에 null을 반환한다. javascript의 location.href를 통한 이동도 null을 반환한다.
- return type
 - String
- HTTP 요청 header에 headerName으로 지정된 이름으로 할당된 값을 리턴한다.
 - 지정된 이름이 없는 경우 null
````java
request.getHeader("referer");
````
````java
String referer= request.getHeader("referer");
response.sendRedirect(referer);
````
- 이전 페이지의 링크 url 정보를 반환한다.