#MySQL INT, UNSIGNED INT

- 일반적으로 컬럼의 데이터형을 지정할 때 정수형일 경우 별 고민 없이 int형을 지정하는 경우가 많다.
- 컬럼값이 음수가 될 경우가 없다면 unsigned int로 명확히 지정해 주시는 것이 성능에 유리하다.
- int형은 -2147483648 ~ 2147483647 범위
- unsigned int는 0 ~ 4294967295 범위
- 이것이 음수를 사용하지 않는 컬럼에 int형을 지정했을 때 성능 차이가 나는 원인이다.
````sql
SELECT *
FROM customer
WHERE quantity <= 500
````
- quantity가 500 이하인 고객 리스트를 반환한다.
- 컬럼 데이터형이 int형일 경우 확인해 봐야 할 quantity 컬럼의 범위는 -2147483648 ~ 500
- 데이터형이 unsigned int 일 경우 확인해 봐야 할 quantity 컬럼의 범위는 0 ~ 500
- 컬럼의 데이터형은 최대한 자세히 명시
- http://blog.naver.com/bbangpower

