#public static void main(String[] args) 
- main 함수는 자바의 Entry Point를 나타내는 함수이다.
- main이라는 함수는 항상 static 하게 정의 되어있어야 누가 생성해주지 않아도 JVM에서 알아서 찾아서 실행시킬 수 있다.
- static은 메모리 선언(new)를 하지 않아도 사용할 수 있다. 실행되기 위해서는 메모리에 미리 올라가야한다.
- 메인 메서드는 Entry Point이기도 하면서 프로그램의 끝이기도 하다. 그러므로 리턴값을 가지는 것 자체가 무의미하다.
- Sting[] args는 C++에서 int argc,int[] arg와 같이 메인함수를 실행할때 인자값을 전달 받는데 String 배열을 통해서 전달을 받겟다는 의미이다.
