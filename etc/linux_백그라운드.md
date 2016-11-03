#Linux 백그라운드 실행(nohup)

- 리눅스 환경에서 java (jar) 데몬처럼 실행
````
java –jar name.jar &
````
- 사용자가 로그아웃시 프로그램 종료
````
nohup java -jar name.jar &
````
- 사용자가 로그아웃해도 백그라운드로 실행되게 하는 명령어
````
찾기 : ps –ef | grep 'name'
종료 : kill -9 (pid)
````
- 프로세스 종료
