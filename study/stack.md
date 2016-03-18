#스택 (Stack)
- top 이라고 하는 리스트의 한쪽 끝에서만 삽입과 삭제가 일어나는 자료구조
- 자료의 후입선출 (last-in-first-out) 방법
- TOP : 자료의 삽입과 삭제가 이루어지는 스택공간의 위치를 표시하는 포인터
- PUSH : 스택에서 자료의 삽입
- POP : 스택에서 자료의 삭제
- 자료의 삽입: TOP = TOP + 1 
- 자료의 삭제: TOP = TOP - 1
- Overflow 발생 : 스택의 크기가 M 일때, TOP > M 이면 Overflow 발생

###스택의 용도 
- 재귀호출
- 인터럽트의 처리
- 수식의 계산 (산술식 표현)
- 서브루틴의 복귀번지 저장 (함수 호출의 순서 제어)

###삽입 알고리즘
```
Top = Top + 1
If(Top > M) Then
            Stack_overflow
Else
            Stack(top) ← data
```

###삭제 알고리즘
```
If(Top = 0) Then
            Stack_underflow
Else
            data ← Stack(top)
            top = top - 1
```


