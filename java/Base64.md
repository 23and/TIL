#Base64 Encoding, Decoding

- 이전 java 표준라이브러리에서는 base64 encoding과 decoding이 제공되지 않았다.
 - sun.misc.BASE64Encoder, sun.misc.BASE64Decoder를 사용했었다.
- java8에서는 자바 표준 라이브러리에서 Base64 encoding과 decoding이 제공된다.
 - java.util.Base64

````java
import java.io.UnsupportedEncodingException;
import java.util.Base64;
 
public class Base64Sample {
public static void main(String args[]){
 
String str = "Welcome to see java.util.Base64";
Base64.Encoder base64Encoder= Base64.getEncoder();
 
//encoding byte array into base 64
byte[] byteArray = null;
try {
    byteArray = base64Encoder.encode(str.getBytes("UTF-8"));
    System.out.println("Base64 Encoded String : " + new String(byteArray,"UTF-8"));
 
    //decoding byte array into base64
    Base64.Decoder base64Decoder= Base64.getDecoder();
    byte[] strdec=base64Decoder.decode(byteArray);
 
   System.out.println("Base64 Decoded String : " + new String(strdec,"UTF-8"));
  } catch (UnsupportedEncodingException e) {
      e.printStackTrace();
   }
  }
}
````
- 출처 : 번역 https://smarttechie.org/2015/06/06/java-8-base64-encoding-decoding/