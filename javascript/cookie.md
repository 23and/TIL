#cookie
- 사용자가 웹사이트를 방문할 경우 해당 사이트에서 사용자의 컴퓨터에 설치하는 기록 정보
- 쿠키 같은 상태 정보는 서버에 저장되지 않고 로컬에서 관리
- 서버에서 저장하는 쿠키의 형태는 키=값 형태
 - 사용자 컴퓨터에 텍스트 형태로 저장
 - 보통 방문자가 다른 페이지로 이동 했을 때 브라우저가 서버에서 방문자 쿠키를 보내게 된다. 서버는 이것을 기억하고 있다가 동일한 사용자임을 판단한다.
````
유효기간(Expires) : 쿠키의 만료날짜를 설정한다. 비어있다면 방문자가 브라우저를 종료하게 되면 쿠키가 만료된다.
도메인(Domain) : 사이트의 도메인 이름
경로(Path) : 쿠키가 저장되는 디렉토리나 웹페이지 경로
보안(Secure) : 이 필드에 단어가 포함될 경우 안점함을 보장한다.
이름=값 : 실질적인 쿠키 설정값이 되는데 키와 값의 쌍으로 저장이 되게 된다.
````
````javascript
document.cookie = "key1=value1;key2=value2;expires=date";
````
````javascript
<html>
<head>
<script type="text/javascript">
<!--
function WriteCookie()
{
   if( document.myform.customer.value == "" ){
      alert("Enter some value!");
      return;
   }
 
   cookievalue= escape(document.myform.customer.value) + ";";
   document.cookie="name=" + cookievalue;
   alert("쿠키 Cookies : " + "name=" + cookievalue );
}
//-->
</script>
</head>
<body>
<form name="myform" action="">
이름입력 : <input type="text" name="customer"/>
<input type="button" value="쿠키셋팅" onclick="WriteCookie();"/>
</form>
</body>
</html>
````
````javascript
<html>
<head>
<script type="text/javascript">
<!--
function ReadCookie()
{
   var allcookies = document.cookie;
   alert("모든쿠키값 : " + allcookies );
 
   // Get all the cookies pairs in an array
   cookiearray  = allcookies.split(';');
 
   // Now take key value pair out of this array
   for(var i=0; i<cookiearray.length; i++){
      name = cookiearray[i].split('=')[0];
      value = cookiearray[i].split('=')[1];
      alert("키 : " + name + " , 값 : " + value);
   }
}
//-->
</script>
</head>
<body>
<form name="myform" action="">
<input type="button" value="Get Cookie" onclick="ReadCookie()"/>
</form>
</body>
</html>
````
- http://mainia.tistory.com/1014