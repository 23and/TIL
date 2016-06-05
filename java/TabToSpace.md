#Tab을 공백으로 변환
````java
public class TabToSpace {
    public static void main(String[] args) {
        String str = "test	test";
        str=str.replaceAll("\t"," ");
        System.out.println(str);
    }
}
````