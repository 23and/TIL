#Find Path

- 가중치 없는 방향 그래프 G가 주어졌을 때, 모든 정점 (i, j)에 대해서, i에서 j로 가는 경로가 있는지 없는지 구하는 프로그램

````java
import java.util.Scanner;

public class FindPath {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int N = sc.nextInt();
        int[][] input = new int[N][N];

        for(int i=0; i<N; i++){
            for(int j=0; j<N; j++){
                input[i][j] = sc.nextInt();
            }
        }
        
        for(int k=0; k<N; k++){
        	for(int i=0; i<N; i++){
        		for(int j=0; j<N; j++){
        			if(input[i][k] == 1 && input[k][j] == 1){
        				input[i][j] = 1;
        			}
        		}
        	}
        } 
        
        for(int i=0; i<N; i++){
            for(int j=0; j<N; j++){
                System.out.print(input[i][j] + " ");
            	if(j==N-1){
            		System.out.println();
            	}
            }
        }
    }
}
````
- 입력
````
3
0 1 0
0 0 1
1 0 0
````
- 출력
````
1 1 1
1 1 1
1 1 1
````