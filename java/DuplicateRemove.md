#Duplicate Remove

````java
public static void main(String[] args) {
        List<String> list = new ArrayList<String>();

        list.add("1");
        list.add("1");
        list.add("2");
        list.add("2");
        list.add("3");
        list.add("4");
        list.add("5");

        //HashSet - 중복제거, LinkedHashSet - 중복제거,정렬
        List<String> duplicateRemoveList = new ArrayList<String>(new LinkedHashSet<String>(list));
}
````