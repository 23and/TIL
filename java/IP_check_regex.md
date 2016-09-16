#IP check regex

````java
import java.util.regex.Matcher;
import java.util.regex.Pattern;

final static String IP_REGEX = "^([01]?\\d\\d?|2[0-4]\\d|25[0-5])\\.([01]?\\d\\d?|2[0-4]\\d|25[0-5])\\." +
            "([01]?\\d\\d?|2[0-4]\\d|25[0-5])\\.([01]?\\d\\d?|2[0-4]\\d|25[0-5])$";

public boolean checkIp(String ip){
    Pattern regex = Pattern.compile(IP_REGEX);
    Matcher regexMatcher = regex.matcher(ip);
    return regexMatcher.matches();
}
````
````
/\[([.\d]+)]/
````
- [.\d]+ <<- .과 숫자 확인 
([.\d]+) <<- 그룹핑,여러번
\[([.\d]+)] <<- \[는 [를 문자로 보는 것, []안에 위의 패턴있는지 확인
