#break, continue
- 반복문에 사용되는 break와 continue는 제어문의 흐름을 변경할 수 있는 각각의 기능을 한다.
- break문은 현재의 반복을 중지한다.
- continue는 현재 차례의 반복만 중지하고 다음 반복으로 이어나가는 역할을 한다.
````java
for(int i=0; i<10; i++){
	i=i+2;
	if(i==8) continue;
	System.out.print(i);
}
````
- 2 5 11