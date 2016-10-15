#jqeury callback
- 응답왔을 때, 실행
- 반응이 온 것으로 응답하는 함수
- 프로그램에서 호출한 함수가 실행중에 실행하도록 먼저 지정해둔 함수
````jqery
$("선택자").이벤트(속도, function(){구문;});
````
````jqeury
$(“p").hide(1000,function(){
alert("hide“);
});
````
- callback O
````jqeury
$(“p").hide(1000);
alert("hide“);
````
- callback X