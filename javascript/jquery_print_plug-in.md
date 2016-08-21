#jquery print plug-in

- jquery.printElement.js
````jquery
$(document).ready(function() {
 $("#btnPrint").click(function() {
  printByJquery({
   printMode: 'popup', //팝업설정 popup = 팝업창 , iframe = iframe
   overrideElementCSS:[ '<c:url value="/common/w/css/wchkin.css"/>', { href:'<c:url value="/common/w/css/wchkin.css"/>',media:'print' } ], //css경로
   pageTitle:'인쇄 타이틀', //인쇄 타이틀
   leaveOpen:false //false = 인쇄후 창닫기
  });
 });
});
 
function printByJquery(options) {
 $("#target").printElement(options);
}
````
````html
<div id="target">
인쇄 영역
</div>
````
- http://projects.erikzaadi.com/jQueryPlugins/jQuery.printElement/