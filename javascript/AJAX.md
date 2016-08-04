###AJAX
1. AJAX란
- Asynchronous Javascript And XML
- AJAX는 사실 새로운 프로그래밍 언어가 아니라 기존에 있던 기술들을 현명하게 사용하는 방법론적 기술
- 기존의 있던 기술들 : HTML (컨텐츠), CSS (스타일), JavaScript, DOM (동적인 출력과 상호작용), XML (데이터 전송 형식), XMLHttpRequest (비동기적 데이터 교환)
 
2. AJAX 왜 쓰는가
- 기존의 웹 브라우저는 서버로부터 페이지 단위로만 받을 수 있었다. 때문에 간단한 상호작용을 하려고 해도 페이지 전체를 로딩해야 했고, 이것은 대역폭 낭비를 초래했다.
- AJAX를 사용하면 XML 파일 조각 단위로 데이터를 받아올 수 있기 때문에 전체 페이지를 다시 로드하지 않아도 페이지 일부를 동적으로 갱신할 수 있다.

3. AJAX 동작원리
- 유저가 이벤트를 발생시키면 자바스크립트 함수가 호출 된다.
- XMLHttpRequest 객체의 인스턴스가 생긴다.
- XMLHttpRequest 객체는 현재 HTML페이지의 상태를 가진 XML 메세지를 구성하여 웹서버로 보낸다.
- 서버 내에서 내부 처리한 뒤에 응답 XML 메세지를 보내어 XMLHttpRequest 객체가 수신한다.
- 웹 서버에서 반환된 XML 메세지를 파싱하여 DOM 객체를 업데이트한다.

- password check
````jquery
$(document).ready(function(){
	$('#currentPassword').blur(function(){
	    $.ajax({
	        url:'요청 주소',
	        type:"POST",
	        data: {
	        	"password" : $('#password').val()
	        },
	        success:function(data){
	        	var result = data;
	            if($.trim(data) == "true"){
	            	$('#checkResult').html('&nbsp;&nbsp;');
	            }else if($.trim(data) == "false"){
	            	$('#checkResult').html('Password did not match.');
	            }
	        },
	        error:function(jqXHR, textStatus, errorThrown){
	            alert("error\n" + textStatus + " : " + errorThrown);
	            self.close();
	        }
	    });	
	});
});
````
````java
PrintWriter out = response.getWriter();
String password = request.getParameter("password");
try{
	HttpSession session = request.getSession();
	int memberNumber = (int)session.getAttribute("memberNumber");
	if(password.equals(MemberDAO.checkPassword(memberNumber))){
		out.println("true");
	}else{
		out.println("false");
	}
}catch(Exception e){
	response.sendRedirect("error.jsp");
}
````