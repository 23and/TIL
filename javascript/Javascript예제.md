#Javascript 예제
````
"i'm a lasagna hog".split("").reverse().join("");
```
- 문제: 위 상황의 결과 값은?
- 답: "goh angasal a m'i"
````
( window.foo || ( window.foo = "bar" ) );
````
- 문제: window.foo의 값은 무엇인가요?
- 답: "bar"
- 처음에 window.foo는 false, undefined 혹은 0등의 값을 가지고 있다.
````
var foo = "Hello"; (function() { var bar = " World"; alert(foo + bar); })(); alert(foo + bar);
````
- 문제: 어떠한 두 가지의 알럿이 나올까요?
- 답: "Hello World" & ReferenceError: bar is not defined
- https://github.com/h5bp/Front-end-Developer-Interview-Questions/tree/master/Translations/Korean