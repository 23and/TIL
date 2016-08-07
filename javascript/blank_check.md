#blank check

- 텍스트 빈칸 확인
- 빈칸이 아닌 경우에만 submit

````javascript
function check() {
	var text = document.getElementById("text");
	
	if (text.value.length == 0){
		alert("blank");
		text.focus();
		return false;
	}
}

function checkSubmit(){
    if(check()){
        document.formName.submit();
    }
}
````