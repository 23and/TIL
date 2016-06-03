#JSONP

- JSON with Padding
- 웹에서 자바스크립트로 통신하기 위한 기술이다.
- JSON
````
{"name":"abc","id":1} 
````
- JSONP
````
func({"name":"abc","id":1}); 
````
- CORS(cross-origin resource sharing) 정책에 의해 도메인이 다른 사이트에 JSON 데이터를 요청할 수 없다.
- JSONP를 호출하기 위해서는 callback이라는 parameter를 붙여서 호출해야한다.
- 응답에서 주어진 callback값으로 응답해야한다.