#MinHeap
````java
import java.util.Arrays;
import java.util.Scanner;

public class MinHeapTest {
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
- 시간초과