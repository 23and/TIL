#String Compare

- 1120

````java
import java.util.Scanner;

public class StringCompare {
	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		String A = sc.next();
		String B = sc.next();
		int diff = B.length() - A.length();
		int min = 100;
		for(int i=0; i<=diff; i++){
			int count = 0;
			for(int j=0; j<A.length(); j++){
				if(A.charAt(j)!=B.charAt(i+j)){
					count += 1;
				}
			}
			if(min>count) min = count;
		}
		System.out.println(min);
	}
}
````
- 입력
````
adaabc aababbc
````
- 출력
````
2
````