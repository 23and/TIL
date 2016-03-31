#K번째 수
````java
import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;

public class Main {
	public static void main(String[] args) throws IOException {
		BufferedReader sc = new BufferedReader(new InputStreamReader(System.in));
		String first = sc.readLine();
		String second = sc.readLine();

		String[] input1 = first.split(" ");
		String[] input2 = second.split(" ");

		int number = Integer.parseInt(input1[0]);
		int[] array = new int[number];

		for (int i = 0; i < number; i++) {
			array[i] = Integer.parseInt(input2[i]);
		}
		System.out.println(Sort.selectKth(array,
				Integer.parseInt(input1[1]) - 1));
	}

	public static class Sort {
		public static int selectKth(int[] arr, int k) {
			if (arr == null || arr.length <= k)
				throw new Error();

			int from = 0, to = arr.length - 1;

			while (from < to) {
				int r = from, w = to;
				int mid = arr[(r + w) / 2];

				while (r < w) {
					if (arr[r] >= mid) {
						int tmp = arr[w];
						arr[w] = arr[r];
						arr[r] = tmp;
						w--;
					} else {
						r++;
					}
				}

				if (arr[r] > mid){
					r--;
				}

				if (k <= r) {
					to = r;
				} else {
					from = r + 1;
				}
			}
			return arr[k];
		}
	}
}
````
- 해결 : 퀵셀렉트 정렬방법 사용, Scanner대신 BufferedReader 사용
