#CASE
````
CASE 컬럼명 | 표현식 WHEN 조건식1 THEN 결과1
                  WHEN 조건식2 THEN 결과2
                  WHEN 조건식n THEN 결과n 
                  ELSE 결과
END
````
- 조건문과 조건문 사이에는 콤마(,) 를 사용하지 않는다.
- CASE 문은 반드시 END 로 끝내야 한다.
- CASE 표현식은 ANSI SQL 형식도 지원한다.
- 결과 부분은 NULL 을 사용해서는 안된다.
````
CASE WHEN x = y THEN a ELSE b END
````
- 조건 x = y 가 true 일 경우 a 이고 그렇지 않으면 b
````
CASE WHEN x < y THEN a WHEN x = y THEN b ELSE c END
````
- 조건 x<y 가 true 일 경우 a 로, 조건 x = y 일 경우엔 b 로 그렇지 않으면 c 로 변경
````
CASE NAME WHEN 'pink' THEN 'red' ELSE 'blue' END
````
- NAME이 pink일 경우 red 로 변경, 그렇지 않으면 blue로 변경