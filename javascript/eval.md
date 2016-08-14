#eval

- 자바스크립트 코드를 계산하고 실행
````
eval(codeString)
````
- 파라미터(codeString) : 올바른 JavaScript 코드를 포함하는 String 값
- javasctip 소스 코드를 동적으로 실행할 수 있다.
- codeString 문자열은 javasctip 파서에 의해 구문 분석되고 실행된다
- eval 함수에 전달된 코드는 eval 함수가 호출되는 것과 같은 상황에서 실행
````javascript
var x = 20;
var y = 30;
 
var xy1 = eval("x * y") + "<br>";
var xy2 = eval("10 * y") + "<br>";
var xy3 = eval("100 + 200") + "<br>";

document.write(xy1 + xy2 + xy3);
````
````
600
300
300
````

