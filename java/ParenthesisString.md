#Parenthesis String

````java
import java.util.Scanner;
import java.util.Stack;

public class ParenthesisString {
	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		String input = sc.nextLine();
		System.out.println(isCorrect(input));
	}

	public static boolean isCorrect(String input) {
		char[] check = input.toCharArray();
		Stack<Character> st = new Stack<Character>();
		for (int i = 0; i < check.length; i++) {
			if (check[i] == '<' || check[i] == '{' || check[i] == '[' || check[i] == '(') {
				st.push(check[i]);
			} else if ((check[i] == '>' && st.peek() == '<')
					|| (check[i] == '}' && st.peek() == '{')
					|| (check[i] == ')' && st.peek() == '(')
					|| (check[i] == ']' && st.peek() == '[')){
				st.pop();
			}
		}
		
		if (st.isEmpty()){
			return true;
		}
		
		return false;
	}
}

````
- 예
 - 입력 : (){} / ({)}
 - 결과 : true / false
