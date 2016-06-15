#DFS, BFS

###DFS
- Depth First Search

````java
public void DFS(int v){
	visited[v] = true;
	for(int i = 0; i < MAX_LENGTH; i++){
		if(map[v][i] == 1 && !visited[i]){
			DFS(i);
		}
	}
}
````

###BFS
- Breadth First Search

````java
public void BFS(int v){
	Queue queue = new LinkedList();
	queue.add(i);
	while(queue.isEmpty()){
		v = (int)queue.poll();
		for(int i = 0; i < MAX_LENGTH; i++){
			if(map[v][i] == 1 && !visited[i]){
				queue.add(i);
				visited[i] = true;
			}
		}
	}
}
````

###DFS, BFS 차이점
|DFS|BFS| 
|:---:|:---:|
|막다른 곳에서 되돌아오기 가능|되돌아오기 불가능|
|탐험이 끝나지 않은 정점들이 LIFO순서로 처리된다|탐험될 정점들이 FIFO큐에 저장된다.|
|검색은 특정한 한 방향으로만 이루어진다.|같은 레벨의 정점들은 평행하게 관리된다.|