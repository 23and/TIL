#jquery blur()

- 대상 element가 focus()를 잃었을 때 발생한다.
- 비활성 상태는 클릭등으로 선택되어졌다가 다시 선택되지 않은 상태로 돌아간 경우이다.
- ex) id 중복체크
 - 입력창의 focus가 사라졌을 때, ajax 통신
````html
<form>
  <input id="target" type="text" value="Field 1">
  <input type="text" value="Field 2">
</form>
<div id="other">
  Trigger the handler
</div>
The event handler can be bound to the first input field:
$( "#target" ).blur(function() {
  alert( "Handler for .blur() called." );
});
````
````jqeury
$( "#other" ).click(function() {
  $( "#target" ).blur();
});
````