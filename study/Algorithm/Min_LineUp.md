#Min, LineUp

````java
import java.util.Arrays;
import java.util.Scanner;

public class Min {
	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		int T = sc.nextInt();
		long[] heap = new long[T];
		long max = 2147483648L;
		for(int j=0; j<heap.length; j++){
			heap[j] = max;
		}
		for(int i=0; i<T; i++){
			int input = sc.nextInt();
			if (input == 0) {
				if(heap[0] == max){
					System.out.println(0);
				}else{
					System.out.println(heap[0]);
					heap[0] = max;
					Arrays.sort(heap);
				}
			} else {
				heap[i] = input;
				Arrays.sort(heap);
			}
		}
	}
}
````
- 입력
````
3 2
1 3
2 3
````
- 출력
````
1 2 3
````
- 시간초과, PriorityQueue로 다시 풀기 

````java
import java.util.LinkedList;
import java.util.Scanner;

public class LineUp {
	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		int N = sc.nextInt();
		int M = sc.nextInt();
		LinkedList list = new LinkedList();
		for(int i=0; i<M; i++){
			int first = sc.nextInt();
			int second = sc.nextInt();
			if(list.contains(first)){
				int index = search(first, list);
				list.add(index+1, second);
			}else if(list.contains(second)){
				int index = search(second, list);
				list.add(index-1, first);
			}else{
				list.add(first);
				list.add(second);
			}
		}
		for(int j=0; j<list.size(); j++){
			System.out.print(list.get(j) + " ");
			if(j==list.size()){
				System.out.print(list.get(j));
			}
		}
	}
	public static int search(int key, LinkedList list){
		for(int j=0; j<list.size(); j++){
			if((list.get(j)).equals(key)){
				return j;
			}
		}
		return key;	
	}
}
````
- 입력
````
9
0
12345678
1
2
0
0
0
0
32
````
- 출력
````
0
1
2
12345678
0
````
- DFS사용해서 다시 풀기