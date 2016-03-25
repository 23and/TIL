#K번째 수
````java
import java.util.Arrays;
import java.util.Scanner;

public class Main {
	public static void main(String[] args) {
    	Scanner sc = new Scanner(System.in);
		String first = sc.nextLine();
		String second = sc.nextLine();
		
		String[] input1 = first.split(" ");
		String[] input2 = second.split(" ");
		
		int number = Integer.parseInt(input1[0]);
		int index = Integer.parseInt(input1[1]);
		
		int[] array = new int[number];
		
		for(int i=0; i<number; i++){
			array[i] = Integer.parseInt(input2[i]);
		}
		
		Arrays.sort(array);
		
		System.out.println(array[index-1]);		
	}
}
````
- 시간초과