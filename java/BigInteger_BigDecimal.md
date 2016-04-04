#BigInteger,BigDecimal
- 자바의 기본형 중에서 보통 int형으로 정수 표현을 하며, 상황에 따라서 더 표현할 수 있는 범위가 넓은 long형을 사용한다.
- 그 이상의 값을 필요로 할 때는 BigInteger 클래스를 이용한다.
- BigDecimal는 정확한 실수 표현을 위한 클래스이다.
- java.math 패키지에서 제공하는 BigInteer와 BigDecimal 클래스는 원시타입 int와 double과 달리 범위나 정확도에 대한 제항이 없다.
- 그러나 계산에 소요되는 시간은 int double에 비교해서 느리다.
- BigInteger은 BigDecimal 은 +,-,*,/ 연산 대신에 add, subtract, multiply, divide 메소드를 이용하여 사칙 연산을 수행한다.
````java
import java.math.BigInteger;
import java.math.BigDecimal;
 
public class Main {
    public static void main(String[] args) {
        BigInteger bigValue1 = new BigInteger("1000000000000");
        BigInteger bigValue2 = new BigInteger("100000000000");
        BigInteger addResult = bigValue1.add(bigValue2);
        BigInteger mulResult = bigValue1.multiply(bigValue2);

        int value1 = 5;
        int value2 = 10;
        BigInteger bigValue1 = new BigInteger(Integer.toString(value1));
        BigInteger bigValue2 = new BigInteger(Integer.toString(value2));

        BigDecimal bigE1 = new BigDecimal("1.6");
        BigDecimal bigE2 = new BigDecimal("5.3");
        BigDecimal addResult = bigE1.add(bigE2);
        BigDecimal mulResult = bigE1.multiply(bigE2);
    }
}
````