#radio button checked

- field3 radio button check
````javascript
function radioCheck(){
	var element = document.getElementsByName("field");
	for (var i = 0; i < element.length; i++){
		if (element[i].value == 'field3'){
			element[i].checked = true;
		}
	}
}
````
````
window.onload = radioCheck;
````
````
<input type="radio" name="field" value="field1">
<input type="radio" name="field" value="field2">
<input type="radio" name="field" value="field3">
<input type="radio" name="field" value="field4">
````