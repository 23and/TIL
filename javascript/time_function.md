#time function
````javascript
setTimeout([Function], [Milliseconds])
````
- 특정 시간 이 후, 단 한번만 특정 함수 또는 코드를 실행시킬 때 사용한다.
- 2번째 인자의 시간(Milliseconds)이 경과하면 1번째 인자의 함수를 실행한다.
- 1000ms = 1초
````javascript
setInterval([Function], [Milliseconds])
````
- 특정 시간 마다 특정 함수 또는 코드를 실행시킬 때 사용한다.
- 2번째 인자의 시간(Milliseconds)이 지날때마다 1번째 인자의 함수를 실행한다.
````javascript
clearInterval([Timer Id]) 
````
- setInterval 함수를 사용하면 매 특정 시간마다 함수가 실행된다. 페이지가 바뀌거나 리프레시 될때까지 무한 실행된다.
- 더 이상 setInterval이 동작하지 않기 원할 때 clearInterval 함수를 사용한다.
- setInterval 함수 실행 시, 반드시 return 값 (Timer ID)을 반환 받아서 가지고 있어야 한다.

