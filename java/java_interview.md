#java interview

````java
public class Main extends Thread{

	public void run(){
		System.out.println("Run");
	}
	
	public static void main(String a[]){
		Thread t1 = new Thread(new MyExmpCode());
		t1.start();
		t1.start();
	}
}
````
- Can Java thread object invoke start method twice?
 - No, it throws IllegalThreadStateException