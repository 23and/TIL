#javascript tag 제거
````javascript
<!DOCTYPE html>
<html>
<head>
	<meta charset="utf-8">
	<title>자바스크립트 정규식으로 Html 태그 제거하기</title>
	<script src="http://ajax.googleapis.com/ajax/libs/jquery/1.9.1/jquery.min.js"></script>
	<script>

			function removeTag( html ) {
				return str.replace(/(<([^>]+)>)/gi, "");
			}
	 
			function doRemoveTag() {
				var beforeText = $("[name=beforeText]").val();
				var afterText = removeTag( beforeText );
				$("[name=afterText]").val( afterText );
			}

	</script>
</head>
<body>
````