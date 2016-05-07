#Prime Factorization

````java
public class PrimeFactorization {
	public static void main(String[] args){
		int div = 2;
		System.out.print("값입력 : ");
		Scanner sc = new Scanner(System.in);
		int n = sc.nextInt();
		
		while(n > 1){
			if(n%div == 0){
				n/=div;
				System.out.print(div + " ");
			}else{
				div++;
			}
		}
	}
}
````