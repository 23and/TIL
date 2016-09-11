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