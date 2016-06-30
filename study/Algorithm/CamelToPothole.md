#Camel To Pothole

- CameleCase -> Pothole_case
- ex) camelToPothole -> camel_to_pothole
````java
public class CamelToPotholeTest {
	public static void main(String[] args){
		System.out.println(CamelToPothole("camelToPothole"));
		
	}
	public static String CamelToPothole(String str){
        StringBuffer sb = new StringBuffer();
        char[] ch = str.toCharArray();
        int i = 0;
        while(i<ch.length){
            char temp = ch[i];
            // 대문자
            if(ch[i]>=65 && ch[i]<=90){
                sb.append('_');
                ch[i] += 32;
            } 
            // 정수
            if(ch[i]>=48 && ch[i]<=57){
                sb.append('_');
            }
            sb.append(ch[i]);
            i++;
        }
        return sb.toString();
    }
}
````