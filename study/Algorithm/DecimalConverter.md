#DecimalConverter
- n진수 변환

````java
public String DecimalConverter(int value, int i){
   String returnString = "";
    String temp = "";
    while(value != 0){
        if( (value % i) < 10 ) {
            returnString = (value % i) + returnString;
            value /= i;
        }
        else {
            int temp1 = (char)((value % i)  + 55);
            returnString = Integer.toString(temp1) + returnString;
        }
    }
    return returnString;
}
````