#TreeCutting

````java
import java.util.Arrays;
import java.util.Scanner;

public class TreeCutting {
	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		int N = sc.nextInt();
		int M = sc.nextInt();
		int[] tree = new int[N];
		int sum = 0;
		int result = 0;
		
		for(int i=0; i<N; i++){
			tree[i] = sc.nextInt();
		}
		Arrays.sort(tree);
		result = tree[N-1];
		/* result 값을 구해도 - 했음. 틀림
		while(M >= sum){
			sum = 0;
			for(int j=0; j<tree.length; j++){
				if(tree[j] - result > 0){
					sum = sum + tree[j] - result;
				}
			}
			result = result - 1;
		}
		*/
		while(result > 0){
			for(int j=0; j<tree.length; j++){
				if(tree[j] - result > 0){
					sum = sum + tree[j] - result;
				}
			}
			if(sum >= M){
				break;
			}
			result = result - 1;
			sum = 0;
		}
		System.out.println(result);
	}
}
````
- 입력값
````
4 7
20 15 10 17
````
- 출력값
````
15
````
- 틀림