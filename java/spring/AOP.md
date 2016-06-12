#AOP
- Aspect Oriented Programming : 관점 지향 프로그래밍
- 장점
 - 중복 코드 최소화
 - 유지보수 공통 요구사항 변경시 수훨하게 적용 가능 
 - 비즈니스 코드와 모든 비즈니스가 공동적으로 사용되는 공통 로직이 있을경우 명확한 분리 및 적용 시점 임의 설정 가능 
- aspect : 공통로직을 범용적으로 표현
- pointcut : 공통로직을 적용받을 핵심로직의 범위 설정 표기
- 적용 시점
 - before
 - after
 - after-return
 - after-throwing
 - around *
- xml 기반
 - aop 사용 가능한 스펙을 xml 상단에 추가
````
<aop:aspectj-autoproxy /> 
<aop:config>
    ...
<aop:pointcut>  : 공통로직 적용 받을 biz 메소드 지정
<aop:aspect> : 공통로직을 pointcut에 지정된 biz 메소드와 매핑
````
- 어노테이션 기반 
 - aop 사용 가능한 스펙을 xml 상단에 추가
 - <aop:aspectj-autoproxy /> 
 - 설정용 자바 소스 필수 어노테이션
 - @Aspect : class상단에 필수
 - @Pointcut : biz 설정
 - (){} blank인 메소드 상단에 순수 설정용으로 개발 
 - @5가지의 적용 시점
   