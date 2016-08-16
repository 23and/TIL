#기초 Front-end 개발론

- 웹환경에서 사용자가 접하는 부분의 표현방법인 html5, css습득
- 다양한 환경 방법
- 접근성 관련 다양한장애와 환경에 놓여져있는 웹 사용자의 이용형태를 이해
- 서브라임텍스트 :  코드에디터 프로그램 http://www.sublimetext.com/
- chrome설치
 - 마우스우클릭 -> 팝업메뉴 하단 개발자모드
- 필수 설치프로그램
 - 포토샵
 - 현존 브라우저
- web
 - 거미줄
 - 웹자원 위치 지정방법 url
 - 웹자원 이름 접근 프로토콜 http
- w3c
- 브라우저
 - 웹브라우저란? 인터넷에서 웹서버의 웹문서를 가져와 이를 해석하고 직관적이게 보기 편하게해주는 소프트웨어
버전 별 테스트가 중요
- HTML5
 - 웹페이지를 위한 마크업 언어
 - 웹서핑할때 많이보게되는 문서는 XHTML이라고 생각하면 됨
- HTML5 철학기반
 - 현재 브라우저에서 발생하는 행위 중 상호호환이 가능한 것에 대해서만 정의
 - 기존에 정의하지않았던 에러처리에 대한 부분정의
 - 예: <p><strong></p></strong>
 - 브라우저 간의 랜더링 차이를 줄여준다
 - 랜더링이란? 우리가 작업한 파일을 사용자 브라우저에 뿌려주는 과정
 - 예: 인터넷쇼핑하는 경우 사진이 늦게뜰때 랜더링이 느리다
- HTML5 APIs
 - api? 설명서, 사용기술
 - api 중 하나 -> svg : xml을 기반으로 한 vector drawing표준
 - svg 화면을 매끄럽게 보여줄 수 있음 (사용분야 그래프)
 - Web GL
 - Geo location
 - https://sketch.io/sketchpad/
- HTML5 요소
 - 최초 진입 장벽이 낮고, 기본적인 언어
- front-end 뭘까?
 - 웹기획자, 웹디자이너
 - 서비스 시작전, 어떤 서비스를 해야 사람들이 찾을까?
 - 기능을 어떤식으로 화면에 보여줄 수 있을까?
 - 각 직군마다 테스트도 하고 주어진 일을 잘해야 서비스가 잘 돌아갈 수 있음
- 태그의 기본구조 <p> : < >는 태그, p는 요소
- w3schools.com
- HTML5 의 기본구조
 - DTD
 - HTML
 - HEAD
 - BODY
- HTML에서  DTD
 - 그 문서의 문단을 구분하고 주제의 제목을 식별하고 또 각각이 어떻게 처리되어야할지를 나타내는 마크업을 식별할 수 있도록 문서와 함께 동반되는 하나의 규격
- head
 - 문서의 정보를 나타내는 요소
 - meta요소 :  인코딩, 저작자 정보, 키워드, 검색조건 등을 명시
 - 인코딩의 경우에는 문서가 시작되고 512byte 안에 정의
- body
 - 헤딩요소 <h> 제목
 - <ul><li></li></ul> 목록
 - <section> 하나로 묶는
 - <article> 하나의 컨텐츠
 - <nav> 탭과 비슷한
 - <header> 페이지에서 밑에 컨텐츠와 상관없이 고정되어있는 . article과 비슷한 요소
 - <footer> 페이지의 아래에 고정되어 있는
 - <aside>
 - <dl> : 정의형 목록
 - <dt> : 정의형 목록에서 용어
 - <dd> : 정의형 목록에서 설명
 - <hr> : 구분하는 선
 - <figure> : 이미지에 대한 설명 글
- 브라우저 마다 화면이 항상 같은 사이즈로 나오지않음. 브라우저마다 사이즈를 다 맞추기위해서는 많은 시간이 소요됨
- 점유율을 바탕으로 오래된 기기, 브라우저를 제외할 수 있음
- 로그에 사용자가 어떤 디바이스로 접속을 하는지, 정보를 알 수 있다. 그러면 개발할 때, 해당 디바이스에 관한 것을 뺄 수 있음
- 브라우저를 어느정도 컨트롤할 것인지도 중요한 요소
- <a> : 페이지 이동
 -	href 속성: 이동할 자원의 경로
 -	target속성 (예:target=”_blank”)
 -	download속성
- HTML은 소스를 보면 의미를 알 수 있다.
- <img> : 이미지
 -	src :  이미지 주소
 -	alt : 이미지에 대한 설명을 나타낸다
````html
<nav>
  <ul>
    <li><a href="http://www.daum.net">다음이동</a></li>
    <li><img src="http://adimg.daumcdn.net/www4/3HuA/dfSJ/280x150_0107.jpg"></li>
 </ul>
</nav>
````
````html
<section>
   <dl>
    <dt>Coffee</dt>
    <dd>Black hot drink</dd>
    <dt>Milk</dt>
    <dd>White cold drink</dd>
  </dl>
</section>
````
````html
<figure>반갑습니다. 테스트중입니다. </figure>
````
````html
<section>
  <h2>과일의 종류</h2>
  <ul>
    <li>사과</li>
    <li>포도</li>
    <li>귤</li>
    <li>배</li>
  </ul>
</section>
<section>
  <h2>내가 좋아하는 과일 순위는 ?</h2>
  <ul>
    <li><strong>포도</strong></li>
    <li>귤</li>
    <li>배</li>
    <li>사과</li>
  </ul>
  <time datetime="2008-02-14 20:00">Valentines day</time>
</section>
````
-	표 형식의 데이터를 표현하기 위한 요소
-	표의 특성상 많은 양의 데이터를 담고 있기 때문에 접근성 측면에서 상당히 중요하게 언급되어 있다.
````html
<table border=1>
<caption>예능 성적표</caption>
<thead>
<tr>
    <th>고사명</th>
    <th>방법</th> 
    <th>미술</th>
    <th>음악</th>
</tr>
</thead>
<tbody>
<tr>
    <td colspan="4">1학기 중간</td> 
</tr>
<tr>
    <td>1학기 기말</td>
    <td>필기</td>
    <td>87</td>
    <td>90</td>
</tr>
<tr>
    <td>2학기 중간</td>
    <td>실기</td>
    <td>95</td>
    <td>85</td>
</tr>
<tr>
    <td rowspan="1">2학기 기말</td>
    <td rowspan="3">필기</td>
    <td rowspan="3">88</td>
    <td rowspan="1">97</td>
</tr>
<tr>
    <td>평균</td>
    <td>91.75</td>
</tr>
<tr>
  <td>안뇽</td>
  <td>안뇽</td>
</tr>
</tbody>
</table>
````
- 멀티미디어 요소
 - <video>
 - <audio>
 - <canvas> : 자바스크립트와 HTML Canvas 2D Context API에서 제공하는 메서드와 속성을 사용하여 2차원적 그래픽을 bitmap캔버스 형태를 표현할 수 있다
- form관련 요소
- <input> 사용자에 의해 데이터를 입력받는 요소
````
-	text
-	password
-	submit
-	radio : 예 - 성별 하나 선택해야할 때
-	checkbox
-	button
-	number
-	date
-	color
-	range
-	month
-	week
-	datetime
-	datetime-local
-	email
-	search
````
- <textarea>요소 : 예 - 카톡 문자보낼 때 칸
- <select> <option> 요소 :  선택이 필요한 경우, 열려서 펴지는 형태
- <button> : 버튼
 -	reset : 초기화 버튼
 -	submit : submit용도로 사용가능
````html
<form>
  <textarea rows="8" cols="40"></textarea>
  <select>
    <option value="seoul">서울</option>
    <option value="jeju">제주</option>
    <option value="pangyo">판교</option>
  </select>
  <select multiple>
    <option value="kimchi">김치찌개</option>
    <option value="doaenjang">된장찌개</option>
    <option value="tofu">두부조림</option>
  </select>
  <button type="button">Click Me!</button>
  <button type="submit">전송 버튼</button>
  <button type="reset">초기화 버튼</button>
</form>
````
