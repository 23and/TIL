#Responsive Web

````
@media only all and (조건문) {실행문}
````
- @media
 - 미디어 쿼리가 시작됨을 선언한다. @media, only, all, and, (조건문) 사이에 포함되어 있는 공백은 필수적이다.
 - 익스 8이하 버전은 미디어 쿼리를 공식적으로 지원하지 않는다.
- only
 - only 키워드는 미디어 쿼리를 지원하는 사용자 에이전트만 미디어 쿼리 구문을 해석하라는 명령이며 생략 가능하다. 생략했을 때 기본 값은 only로 처리 된다. 생략해도 무방하므로 이 키워드는 일반적으로 작성하지 않는다. 이 자리에는 not 키워드를 사용할 수 있는데 뒤에 오는 모든 조건을 부정하는 연산을 한다.
- all
 - all 키워드는 미디어 쿼리를 해석해야 할 대상 미디어를 선언한 것이다. all 이면 모든 미디어가 이 구문을 해석해야 한다. all 키워드 대신 screen 또는 print와 같은 특정 미디어를 구체적으로 언급할 수도 있다. all 키워드는 생략 가능하고 생략했을 때 기본 값은 all 으로 처리된다. 이 밖에도 다양한 미디어 타입(all, aural, braille, embossed, handheld, print, projection, screen, speech, tty, tv)이 있다. all, screen, print를 가장 널리 쓴다.
- and
 - and 키워드는 논리적으로 ‘AND’ 연산을 수행하여 앞과 뒤의 조건을 모두 만족해야 한다는 것을 의미한다. 조건이 유일하거나 또는 only, all과 같은 선행 키워드가 생략되면 and 키워드는 사용하지 말아야 한다. and 대신 콤마 ‘,’ 기호를 사용하면 ‘OR’ 연산을 수행한다. ‘OR’ 연산은 나열된 조건 중에서 하나만 참이어도 {실행문}을 해석한다. OR 조건을 위한 콤마 ‘,’ 기호 사용시 유의점.
- (조건문)
 - 브라우저는 조건문이 참일때{실행문}을 처리하고 거짓일 때 무시한다. 조건문은 두 가지 이상 등장할 수 있다. 둘 이상의 조건문은 ‘and’ 키워드 또는 콤마 ‘,’ 기호로 연결해야 한다.
- {실행문}
 - 일반적인 CSS 코드를 이 괄호 안에 작성한다. 브라우저는 (조건문)이 참일때 실행문 안쪽에 있는 CSS 코드를 해석한다
````css
/* 윈도우 */
@media all and (min-width:769px) { }

/* 아이패드 */
@media all and (max-width:769px) { }

/* 스마트폰 */
@media all and (max-width:640px) { }
```
````css
@charset "utf-8";

/* 768px 이상에서 보여지는 화면 */
@media all and (min-width:768px){ }

/* 1000px 이상에서 보여지는 화면 */
@media all and (min-width:1017px){#wrap{width:1000px !important;}}
````
````css
@media all and (min-width:768px){ }
````
- 브라우저 크기가 768픽셀 이상인 경우에 적용될 코드를 작성한다.
 - min-width:768px: 브라우저 크기가 768픽셀 이상
 - max-width:768px; 브라우저 크기가 768픽셀 이하
 - min-device-width:768px: 실제 화면 크기가 768픽셀 이상
 - max-device-width:768px: 실제 화면 크기가 768픽셀 이하 

````css
/* by 파미유 */
@charset "utf-8";
@charset "euc-kr";

/* divice 해상도에 따른 이미지 크기 조정 - 필요할 경우 사용 */
@media screen and (-webkit-min-device-pixel-ratio:1.5){ } /* 안드로이드 */

/*smartphones ( portrait )*/
@media all and (max-width:320px){ }

/*smartphones ( landscape )*/
@media all and (min-width:321px) and (max-width:360px){ }

/*smartphones ( landscape )*/
@media all and (min-width:361px) and (max-width:375px){ }

/*smartphones ( landscape )*/
@media all and (min-width:376px) and (max-width:414px){ }

/*smartphones ( landscape )*/
@media all and (min-width:415px) and (max-width:480px){ }

/*tablet( portrait )*/
@media all and (min-width:481px) and (max-width:533px){ }

/*tablet ( portrait )*/
@media all and (min-width:534px) and (max-width:640px){ }

/*tablet ( portrait )*/
@media all and (min-width:641px) and (max-width:768px){ }

/*tablet ( landscape )*/
@media all and (min-width:769px) and (max-width:1024px){ }

@media all and (min-width:1025px){ }
````
- 출처 : http://naradesign.net/wp/2012/05/30/1823/, http://linguist79.tistory.com/29
