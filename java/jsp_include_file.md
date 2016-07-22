#jsp include file

````
<jsp:include page="b.jsp" />
````
- a.jsp 안에서
 - a.jsp 가 자바로 바뀌고 컴파일이 된 후 값이 들어간다.
 - a.jsp 의 컴파일과 b.jsp 의 컴파일이 각각 일어난 후 실행된다.
 - 동적 지시문
 - a.jsp 가 html로 바뀌어서 브라우저로 보여질 시점에 이미 컴파일된 b.jsp가 삽입되기 때문에 include 처럼 b.jsp 내에 있는 변수를 a.jsp에서 사용할 수 없다.
- b.jsp가 수정되는 경우 컴파일이 다시 된다.

````
<%@ include file="b.jsp" />
````
- a.jsp 안에서
 - a.jsp 파일이 자바로 바뀔 때에 자바문서에 삽입이 되어 한번에 컴파일 된다.
 - a.jsp 내에 b.jsp가 삽입 된 후 컴파일이 일어나기 때문에 한번에 컴파일이 된다.
 - 정적인 지시문
 - a.jsp 파일이 java파일로 수정되기 전 b.jsp 파일의 모든 내용이 a.jsp로 include 되고 나서 컴파일 된 후 html문서로 바뀐다.
 - b.jsp 파일 내에 abc라는 변수가 있다면 부모인 a.jsp 파일에서도 그 변수를 사용할 수 있다.

````
