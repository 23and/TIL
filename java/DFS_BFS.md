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