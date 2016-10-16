#scroll
````jquery
.scrollTop()
````
- Returns : Integer
- 조건에 일치하는 요소들 중 첫번째 요소의 스크롤바의 수직 위치(y좌표)를 얻을 수 있다.
````jqery
.scrollTop( value )
````
- Returns : jQuery
- 조건에 일치하는 요소들의 수직 스크롤의 위치를 value값으로 세팅한다.

````jqery
function handleHeader() {
	jQuery(window).scroll(function() {
	  if (jQuery(window).scrollTop() > 100) {
		jQuery('.a').addClass('b');
	  } else {
		jQuery('.a').removeClass('b');
	  }
	});
}
````
- scroll 100이상인 경우에 a에 b클래스 추가, 그 밖의 경우 b클래스 제거