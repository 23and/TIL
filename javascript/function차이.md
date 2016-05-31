#javascript function 차이

````javascript
function Person() {
  return 'hello world'; 
}
````
- var person = Person();
 - 함수 수행에 따른 return 을 변수에 저장한다. person 에는 'hello world' 가 할당된다.
- var person = new Person();
 - person 변수에 Person 함수 객체를 생성하여 할당한다. 이때 할달되는 객체는 Person 함수의 프로토타입을 기반으로 생성된다.

- 출처 :http://insanehong.kr/post/front-end-developer-interview-javascript/