#Stack 문제

````java
import java.util.Scanner;
import java.util.Stack;

public class Main {
   public static void main(String[] args) {
      Scanner sc = new Scanner(System.in);
      String input = sc.nextLine();
      System.out.println(isCorrect(input));
   }
   public static String isCorrect(String input){
       char[] check = input.toCharArray();
       Stack<Character> st = new Stack<Character>();
       st.push('s');
       for (int i = 0; i < check.length; i++) {
           if((st.peek() =='m' && check[i] == 'M') || (st.peek() =='t' && check[i] == 'T')){
                   st.pop();
           }else if(check[i] == 'M'){
               st.push('m');
           }else if(check[i] == 'T'){
              st.push('t');
           }
       }
       
       if(st.peek() =='s'){
          st.pop();
       }

       if(st.isEmpty())
           return "True";
       return "False";
   }
}
````
- 괄호 짝 맞추기랑 비슷
- 스택 사용