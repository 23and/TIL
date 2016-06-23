#Dijkstra

- Dijkstra's algorithm은 어떤 변도 음수 가중치를 갖지 않는 유향 그래프에서 주어진 출발점과 도착점 사이의 최단 경로 문제를 푸는 알고리즘이다. 
- 하나의 시작 정점이 있고, 모든 다른 정점까지의 최단경로를 찾는다.
- S 집합 : 시작 정점으로부터 최단경로가 이미 발견된 정점 집합
- Distance 배열 : 최당경로를 알려진 정점만을 통하여 각 정점까지 가는 최단경로 길이 들의 배열
- 매 단계에서 가장 Distance 값이 적은 정점을 S에 추가하고, Distance 값을 갱신한다.
- 알고리즘의 시간복잡도 : O(n^2)

###단계
- Distance배열을 생성하고, 모든 원소들을 무한대값(큰 값)으로 초기화 한다.
- Distance배열 중 시작하는 정점의 길이를 0으로 초기화한다.
- Distance배열 중 S집합에 있는 정점을 제외하고 최소 정점을 찾는다. 
- 최소 정점의 인접정점들에 대한 경로의 길이를 계산하여 Distance배열 안의 값보다 작다면 갱신한다. 
- 그래프 내의 모든 정점이 최단경로가 될 때 까지 앞의 단계를 반복한다.

###의사코드
- u := Extract_Min(Q)
 - 꼭짓점의 집합 Q에서 가장 작은 d[u]값을 찾은 다음 그 꼭짓점 u를 Q에서 제거한 후 반환하는 함수
````
function Dijkstra(G, w, s)
	for each vertex v in V[G]// 초기화
			d[v] := infinity
			previous[v] := undefined 
	d[s] := 0//덮어쓰기
	S := empty set
	Q := set of all vertices
	while Q is not an empty set// 알고리즘의 실행
		u := Extract_Min(Q)//집합 Q에서 d[u]가 최소인 u를 찾아 빼냄
		S := S union {u}//빼낸 u를 S에 삽입
		for each v with edge (u,v) defined      
			if d[v] > d[u] + w(u,v)             
				d[v] := d[u] + w(u,v)// 변(u,v)의 경감
				previous[v] := u//경로 추적할 때 쓰임//
````
- 출처 :http://pooh-explorer.tistory.com/, 위키피디아
