### RegularExpression
```
^ : 시작표시(매칭이 처음부터 되어야 함) 
$ : 끝표시(문자열 끝에 매칭되어야 함)
[]: 문자열 셋
    -> [ab][a-z][0-9] 라고 써주면 첫글자는 a또는 b이고 그 다음에 a~z가 나오고 그 뒤에 0~9가 나온다는 뜻.
* : 0번 이상 반복
+ : 1번 이상 반복
? : 0 또는 1회
{}: 횟수 표시
    -> [a]{2}이면 aa이고 [a]{2,}이면 a가 2개 이상, [a]{2, 4}이면 aa, aaa, aaaa 이다.
\d: 숫자, [0-9]
\D: 숫자가 아닌 것, [^0-9]
| : or
{}: 그룹
. : 뉴라인(\n)제외한 한 문자 (진짜 .을 찍기 위해선 \.으로 표시해야 한다.)
```
### Java Matcher 클래스의 중요 메소드들
-  boolean matches()
 -> 주어진 문자열 전체가 특정 패턴과 일치하는가를 판단한다.

-  boolean lookingAt()
 -> 주어진 문자열이 특정 패턴으로 시작하는가를 판단한다.

- boolean find()
 -> 주어진 문자열에서 특정 패턴을 찾아낸다.

- boolean find(int start)
 -> Start위치 이후부터 매칭 검사를 수행한다.

- int start()
 -> 매칭되는 문자열 끝 다음 문자 위치를 반환한다.

- int start(int group)
 -> 지정된 그룹이 매칭되는 시작 위치를 반환한다.

- int end()
 -> 매칭되는 문자열 끝 다음 문자 위치를 반환한다.

- int end(int group)
 -> 지정된 그룹이 매칭되는 끝 다음 문자 위치를 반환한다.

- String group()
 -> 매칭된 부분을 반환한다.

- String group(int group)
 -> 매칭된 부분 중 group 번째 매칭 부분을 반환한다.

- String replaceAll(String replacement)
 -> 패턴과 일치되는 부분을 모두 replacement로 대체한다.

- String replaceFirst(String replacement)
 -> 패턴과 일치되는 첫 번째 문자열을 replacement로 대체한다.

- Matcher appendReplacement(StringBuffer sb, String replacement)
 -> 일치되는 패턴이 나타날 때까지 모든 문자들을 버퍼(sb)로 옮기고, 패턴에 일치되는 문자열은 두 번째 파라미터인 replacement 문자열로 대체한다.

- StringBuffer appendTail(StringBuffer sb)
 -> 캐릭터 시퀀스의 현재 위치 이후의 문자들을 버퍼(sb)에 복사해 넣는다. (appendReplacement() 메소드의 치환 처리를 하고 마지막으로 찾은 위치 이후)

- Matcher reset(),  Matcher reset(CharSequence input)
 -> find() 메소드, replaceAll 메소드, replaceFirst() 메소드의 사용에 의해 진행된 matcher 객체의 시퀀스를 초기화 한다.