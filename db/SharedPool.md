#Oracle Shared Pool
 
- 가장 최근에 실행한 SQL문(Libraray Cache), DATA 정의(Data Dictionary Cache)
- Library Cache, Data Dictionary Cache로 구성된다.
- 크기 조정, Shared Pool 변경할 때 사용한다.
 - SGA의 SGA_MAX_SIZE는 초과할 수 없다.
````
alter system set shared_pool_size = 64M ;
````
###Library Cache ﻿
- 실제 SQL문이 저장되는 곳이다.
- 실제 Sysntax check를 한다.  
- 가장 최근에 사용한 SAL문 PL/SQL문 저장한다.
- LRU(Least Recently Used) 알고리즘 사용한다.
 - 사용하지 않는 것은 버린다.
 - 자주 사용된 데이터만 남겨둔다.
 - 최근 적게 사용되는 데이터를 찾아 버린다. 
- 최근 실행 계획(Plan)을 저장한다.
- 동일한(대, 소문자, 공백)SQL문 실행 시 parse tree + execution plan을 저장해두어 실행시간을 줄인다.

###Data Dictionary Cache
- User 계정, data file 이름, segment 이름, extent 위치, table 설명 및 user 권한 등 모든 DB 정보를 Data Dictionary에 저장한다.
- Parse 단계에서 Server Process는 SQL문에 지정된 Object이름을 찾아내고 접근 권한을 검증하기 위해 Dictionary Cache 정보를 찾아본다.
- SQL문 처리과정중 Semantic Check 정보를 저장한다.
 - Semantic Check를 하는 이유?  => 권한, 컬럼, 테이블에 대한 정보가 Data Dictionary Cache에 저장되어 있기 때문이다.

###예시
````
select * from employee
````
- Syntax Check
 - SQL문법을 확인한다.
- Database Resolution
 - 데이터베이스를 분석한다.
 - employee테이블이 데이터베이스에 존재하는지 확인하기 위해서 오브젝트 정보를 저장하는 오라클 내부 데이터 딕셔너리 정보를 검색한다.
- employee 테이블 정보를 데이터 딕셔너리 캐쉬에 저장한다.
- SQL문, 분석 정보 및 실행 계획을 라이브러리 캐쉬에 저장한다.
- 공유 풀에 저장된 정보는 동일 유저 또는 다른 유저가 동일한 SQL을 다시 실행했을 경우 해당 정보를 재사용할 수 있게 된다.
- 재사용을 하게 되면 SQL문 분석, 오브젝트 확인, 실행계획 수립 절차를 수행하지 않기 때문에 구문 분석에 대한 부하를 감소시키고 전체 실행 시간을 단축할 수 있다.
- 동일한 SQL로 인식하기 위해서 조회하는 내용일 동일해야한다.
 - 대소문자 일치
 - 띄어쓰기 일치
 - 오브젝트 소유자 일치
 - 하나라도 불일치할 경우 오라클은 새로운 SQL로 인식한다.
 - 동일한 SQL이여도 대상 테이블에 대한 소유자가 동일해야 재사용이 가능하다.
- 다음 SQL문은 동일한 결과를 출력하지만 다른 SQL로 인식한다.
- 구문 분석 결과를 재사용하지 않고, 별도로 구문 분석 결과를 공유 풀에 저장한다.
````
select * from employee
SELECT * FROM employee
````


출처 : http://blog.naver.com/kdi0373/120183770727, http://blog.naver.com/apollo2810/60140377660