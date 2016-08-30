#jquery contains

````
jQuery( ":contains(text)" )
````
- text 단어가 포함된 요소를 찾는 선택자
- 특정 text를 검색하고 싶을 때 사용할 수 있다.
- 대소문자 구분
````html
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <title>contains demo</title>
  <script src="https://code.jquery.com/jquery-1.10.2.js"></script>
</head>
<body>
 
<div>John Resig</div>
<div>George Martin</div>
<div>Malcom John Sinclair</div>
<div>J. Ohn</div>
 
<script>
$( "div:contains('John')" ).css( "text-decoration", "underline" );
</script>
 
</body>
</html>
````
- http://api.jquery.com/contains-selector/