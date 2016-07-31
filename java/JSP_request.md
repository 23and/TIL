#JSP request

- 사용자가 전송한 정보를 확인하고 데이터를 확인할수 있고 서버에 대한 정보를 제공하는 메서드

| method | return | explanation |
|-|-|-|
| getRemoteAddr()| String | 웹서버에 연결된 사용자의 IP주소정보를 제공 |
| getContentLength() | long | 사용자가 전송한 정보 길이 제공. 데이터 길이가 알수 없다면 -1리턴. |
| getCharacterEncoding() | String | 사용자가 전송한 정보의 캐릭터 인코딩 타입이 무엇인지 제공 |
| getContentType() | String | 사용자가 정보 전송시 사용한 컨텐트의 타입을 제공 |
| getProtocol() | String | 사용자가 요청한 프로토콜 정보 제공 |
| getMethod() | String | 브라우저 정보 전송시 사용한 방식에 대한 정보제공 |
| getRequestURI() | String | 브라우저가 요청한 URL 경로에 대한 정보를 제공 |
| getContextPath() | String | JSP 페이지에 속한 웹 어플리케이션의 컨텍스트 경로 정보 제공 |
| getServerName() | String | 연결시 사용한 서버 이름 정보 제공 |
| getServerPort() | int | 서버가 실행 중인 포트 번호 정보 제공 |