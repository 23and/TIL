#how to get the host url
````java
InetAddress.getLocalHost().getHostName()
````
````java
import java.net.InetAddress;
import java.net.UnknownHostException;


public class LocalHostIpTest {

	public static void main(String args[]){
	    try {

	        InetAddress addr = InetAddress.getLocalHost();
	    
	        // Get IP Address
	        byte[] ipAddr = addr.getAddress();
	    
	        // Get hostname
	        String hostname = addr.getHostName();

	        // IP 형식으로 변환
	        String ipAddrStr = "";
	        for (int i=0; i 0) {
	                ipAddrStr += ".";
	            }
	            ipAddrStr += ipAddr[i]&0xFF;
	        }
	        
	        
	        System.out.println("ip : "  + ipAddrStr);
	        System.out.println("host name : "  + hostname);
	        
	    } catch (UnknownHostException e) {
	    	e.printStackTrace();
	    } 
	}
}

````