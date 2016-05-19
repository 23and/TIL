#CSS rem

###em
- 현재의 font-size를 정의한다.
- body 태그에 em값을 이용해 폰트 사이즈를 지정하면 모든 자식 요소들은 body의 폰트 사이즈에 영향을 받는다.

````
<body>
    <div class="test">Test</div>
</body>
````

````
body {
    font-size: 14px;
}
div {
    font-size: 1.2em; // calculated at 14px * 1.2, or 16.8px
}
````
- div에 font-size를 1.2em으로 지정하면, body의 14px을 기준으로 1.2배의 폰트 사이즈로 표현된다.
- em으로 정의한 폰트 사이즈를 각각의 자식에 선언하면 각각의 div는 각 부모의 폰트 사이즈를 상속받아 점점 커지게 된다.

````
<body>
    <div>
        Test <!-- 14 * 1.2 = 16.8px -->
        <div>
            Test <!-- 16.8 * 1.2 = 20.16px -->
            <div>
                Test <!-- 20.16 * 1.2 = 24.192px -->
            </div>
        </div>
    </div>
</body>
````

###rem
- "r"은 "root(최상위)"이다.
- 최상위 태그(요소)에 지정한 것을 기준으로 삼으며, 보통 최상위 태그는 html태그이다.
````
html {
    font-size: 14px;
}
div {
    font-size: 1.2rem;
}
````
- 이 경우 모든 div에서 동일하게 16.8px로 표현된다.

- 출처 : http://webdesign.tutsplus.com/ko/articles/7-css-units-you-might-not-know-about--cms-22573