#print

- 페이지 나눠서 출력
````html
<div style='page-break-before:always'></div>
````
````html
<html>
	1 page
</html>
<div style='page-break-before:always'></div>
<html>
	2 page
</html>
<div style='page-break-before:always'></div>
````

- 화면에 보여지는 그대로 출력
````javascript
<script type="text/javascript">
    window.print();
< /script> 
````

- 선택 출력
````
<html>
	<head>
	 <script type="text/javascript">
		var fnPrint = function() {
			document.body.innerHTML = selectArea.innerHTML;
			window.print();
		};
	 </script>
	</head>
	<body>
		<!-- 제외될 영역--> 
		프린트<input type="button" value="확인" onClick="fnPrint()" /> 

		<!-- 인쇄될 영역--> 
		<ul id="selectArea">
			<li>A</li>
			<li>B</li>
			<li>C</li>
			<li>D</li>
		</ul>
	</body>
</html>
````