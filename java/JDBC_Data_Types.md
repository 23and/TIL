#JDBC Data Types

- VARCHAR
 - java.lang.String
- CHAR
 - java.lang.String
- LONGVARCHAR
 - java.lang.String
- BIT
 - boolean
- NUMERIC
 - java.math.BigDecimal
- TINYINT
 - byte
- SMALLINT
 - short
- INTEGER
 - int
- BIGINT
 - long
- REAL
 - float
- FLOAT
 - float
- DOUBLE
 - double
- VARBINARY
 - byte[ ]
- BINARY
 - byte[ ]
- DATE
 - java.sql.Date
- TIME
 - java.sql.Time
- TIMESTAMP
 - java.sql.Timestamp
- CLOB
 - java.sql.Clob
- BLOB
 - java.sql.Blob
- ARRAY
 - java.sql.Array
- REF
 - java.sql.Ref
- STRUCT
 - java.sql.Struct
````java
import java.sql.Date;
import java.sql.Time;
import java.sql.Timestamp;
import java.util.*;

public class SqlDateTime {
   public static void main(String[] args) {
      //Get standard date and time
      java.util.Date javaDate = new java.util.Date();
      long javaTime = javaDate.getTime();
      System.out.println("The Java Date is:" + 
             javaDate.toString());

      //Get and display SQL DATE
      java.sql.Date sqlDate = new java.sql.Date(javaTime);
      System.out.println("The SQL DATE is: " + 
             sqlDate.toString());

      //Get and display SQL TIME
      java.sql.Time sqlTime = new java.sql.Time(javaTime);
      System.out.println("The SQL TIME is: " + 
             sqlTime.toString());
      //Get and display SQL TIMESTAMP
      java.sql.Timestamp sqlTimestamp =
      new java.sql.Timestamp(javaTime);
      System.out.println("The SQL TIMESTAMP is: " + 
             sqlTimestamp.toString());
     }//end main
}//end SqlDateTime
````
- http://www.tutorialspoint.com/jdbc/jdbc-data-types.htm