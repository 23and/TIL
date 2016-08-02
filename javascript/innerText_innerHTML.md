#innerText, innerHTML

###innerText
- 태그를 제외한 텍스트
- HTML 태그를 포함해도, 태그 자체를 텍스트로 인식한다.

###innerHTML
- 태그 적용 가능
- 자신을 둘러싼 태그는 제외하고, 그 안의 내용을 태그를 포함해서 넣을 수 있다.

###jquery html()
- innerHTML
````jquery
$('#id명').html('내용');
````
