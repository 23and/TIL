#time
- java 8에서는 새로운 날짜/시간 관련 API가 java.time 패키지에 추가되었다.
- 클래스는 immutable이며 스레드에 대해 안전하다.
- 날짜 및 시간 형식
 - Instant, LocalDate, LocalDateTime, ZonedDateTime
- 날짜와 시간 이외
 - Duration과 Period
 - 새로 추가된 값 형식
  - Month, DayOfWeek, Year, Month YearMonth, MonthDay, OffsetTime, OffsetDateTime 등
 - 새로운 날짜/시간 클래스는 대부분이 JDBC에서 지원됨으로써 RDB 연동의 효율적인 구현이 가능하다.

###java.time.LocalDate
````java
import java.time.LocalDate;
import java.time.temporal.ChronoUnit;

public class DateTimeDemonstration {

public static void main(String[] args) {
   //Create date LocalDate localDate = LocalDate.now();
    System.out.println("The local date is :: " + localDate); 
 
   //Find the length of the month. That is, how many days are there for this month.
   System.out.println("The number of days available for this month:: " + localDate.lengthOfMonth()); 
 
   //Know the month name
   System.out.println("What is the month name? :: " + localDate.getMonth().name()); 
 
   //add 2 days to the today's date.
   System.out.println(localDate.plus(2, ChronoUnit.DAYS)); 
 
   //substract 2 days from today
   System.out.println(localDate.minus(2, ChronoUnit.DAYS)); 
 
   //Convert the string to date
   System.out.println(localDate.parse("2017-04-07"));
  }
}
````

###java.time.LocalTime
````java
import java.time.LocalTime;
import java.time.temporal.ChronoUnit;

public class DateTimeDemonstration {

public static void main(String[] args) {
   //Get local time
   LocalTime localTime = LocalTime.now();
   System.out.println(localTime);
  //Get the hour of the day
  System.out.println("The hour of the day:: " + localTime.getHour());
 
  //add 2 hours to the time.
  System.out.println(localTime.plus(2, ChronoUnit.HOURS));
  //add 6 minutes to the time.
  System.out.println(localTime.plusMinutes(6));
  //substract 2 hours from current time
  System.out.println(localTime.minus(2, ChronoUnit.HOURS));
 }
}
````

###java.time.LocalDateTime
````java
import java.time.LocalDateTime;
import java.time.temporal.ChronoUnit;

public class DateTimeDemonstration {

public static void main(String[] args) {
 
    //Get LocalDateTime object
    LocalDateTime localDateTime = LocalDateTime.now();
 
    System.out.println(localDateTime);
 
    //Find the length of month. That is, how many days are there for this month.
    System.out.println("The number of days available for this month:: " + localDateTime.getMonth().length(true));
 
    //Know the month name
    System.out.println("What is the month name? :: " + localDateTime.getMonth().name());
 
    //add 2 days to today's date.
    System.out.println(localDateTime.plus(2, ChronoUnit.DAYS));
 
    //substract 2 days from today
    System.out.println(localDateTime.minus(2, ChronoUnit.DAYS));
 
  }
}
````

###java.time.Year
````java
import java.time.Year;
import java.time.temporal.ChronoUnit;
 
public class DateTimeDemonstration {
 
public static void main(String[] args) {
 
   //Get year
   Year year = Year.now();
   System.out.println("Year ::" + year);
 
   //know the year is leap year or not
   System.out.println("Is year[" +year+"] leap year?"+ year.isLeap());
  }
}
````

###java.time.Duration
````java
import java.time.Duration;
import java.time.LocalDateTime;
import java.time.temporal.ChronoUnit;

public class DateTimeDemonstration {
 
public static void main(String[] args) {
 
   LocalDateTime localDateTime = LocalDateTime.now();
 
   //Get the duration between two dates
   Duration duration = Duration.between(localDateTime, localDateTime.plus(2, ChronoUnit.DAYS));
   System.out.println(duration.toDays());
  }
}
````

###java.time.Period
````java
import java.time.LocalDate;
import java.time.Period;
import java.time.temporal.ChronoUnit;
 
public class DateTimeDemonstration {
 
public static void main(String[] args) {
 
   LocalDate localDate = LocalDate.now();
 
   Period period = Period.between(localDate, localDate.plus(2, ChronoUnit.DAYS));
   System.out.println(period.getDays());
  }
}
````
 출처 : https://smarttechie.org/2016/04/07/java-8-new-way-to-deal-with-date-and-time/, http://www.moreagile.net/search/label/Java