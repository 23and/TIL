#JSTL (JSP Standard Tag Library)
- 자주 사용될 수 있는 custom tag들을 표준으로 정해놓은 tag library
- taglib
````
<%@ taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core" %>
````
- 코어 라이브버리 : 변수지원, 흐름제어, URL처리 (접두어 : c) 
- http://java.sun.com/jsp/jstl/core
- set : JSP에서 사용 될 변수설정
````
<c:set var="변수명" scope="scope" value="변수값"/>
````
- scope : page, request, session, application
- remove
````
<c:remove var="name" scope="scope"/>
````
- if : 조건문 처리, 조건이 true이면 실행 if의 다중조건 else if 사용 불가
````
<c:if test="조건">
    내용
</c:if>
````
- choose : 다중조건처리(else if)
````
<c:choose>
    <c:when test="조건">
        내용
    </c:when>
    <c:when test="조건2">
        내용
    </c:when>
    <c:otherwise>
        내용
    </c:otherwise>
</c:choose>
````
- forEach : collection 또는 map의 각 항목을 처리 할때 사용 (loop)
 - var : Collection에서 처리한 값을 저장 할 변수
 - items : 처리할 Collection
````
<c:forEach var="변수" items="아이템">
    내용
    ${변수}
</c:forEach>
````
````
<c:forEach var="i" begin="1" end="20" step="2">
    출력 : ${i}<br>
</c:forEach>
````
- map의 경우 key 값은 .key, value는 .value로 출력
````
<c:forEach var="i" items="${map}">
    ${i.key} = ${i.value}<br>
</c:forEach>
````
- forTokens : 구분자로 분리된 각각의 토큰을 처리시 사용
