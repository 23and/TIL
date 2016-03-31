#BufferedReader, Scanner
- parser를 만들거나 인풋을 받아 복잡하게 쪼개 사용하고 싶으면, BufferedReader로 받아서 쪼개주는 것보다는, Scanner를 사용하여 몇 줄 안되는 코드로 원하는 동작을 수행하는게 더 바람직하다. 반대로 만약 그냥 읽어 들이기만 하는 용도라면 BufferedReader를 사용하는 것이 바람직하다.
- Scanner의 버퍼 사이즈는 1024 chars 이고, BufferedReader의 버퍼사이즈는 8192 chars이기 때문에 많은 입력이 있다면 BufferedReader를 사용하는 것이 성능상 좋다.

###BufferedReader
- Reader를 사용하여 사용자 인풋을 받거나 파일을 읽어들인다면, 스트림을 열고 한 문자를 받고 스트림을 닫기 때문에 문장이 길어지면 길어질수록 스트림을 열고 닫는 것 때문에 딜레이가 심해진다. 그렇기 때문에 이러한 Reader를 BufferedReader로 래핑을 한다. 그렇게 하면 스트림을 한 번 열었을 때 뭉땡이로(보통 한 줄) 재빠르게 읽어들일 수가 있다.
- 버퍼를 이용하여 입출력의 효율을 높일 수 있다.
- 단순한 구조, 읽어들이는 메소드 : read, readLine
- Synchronized로 멀티쓰레딩 기반 환경에서 안전하다.

###Scanner
- Scanner는 parsing과 tokenizing을 할 수가 있다.
- nextInt(), nextDouble(), nextLine() 등 자료형에 따라서 선택할 수 있다. 
- Non-Synchronized 멀티스레딩 환경에서 사용하려면 Scanner의 wrap해서 (subclass를 만들거나 composition을 이용하여) 사용해야 안전하다

````
399 ms Scanner.nextLine()        
39 ms BufferedReader.readLine() 
549 ms Scanner.nextInt()         
44 ms Integer.parseInt(BufferedReader.readLine())
````
- 출처 : gwpark.tistory.com/1766, http://stackoverflow.com/questions/2231369/scanner-vs-bufferedreader, http://pooh-explorer.tistory.com/30

