#linux scp

- Secure CoPy
- scp는 클라이언트 컴퓨터에서 서버 컴퓨터로 파일을 upload하거나 download 할때 쓰는 명령어다.
- scp는 파일뿐만 아니라 디렉토리까지 복사할 수 있다는 장점이 있다.
- 포트는 SSL 기반의 세션 보안 프로토콜을 사용한다.
````
scp [계정명@server_ip]:[server에 다운로드할 파일 경로] [저장할 경로]
````
- download
````
scp [업로드할 파일 경로] [계정명@server_ip]:[server에 저장할 경로]
````
- upload
- -r 옵션을 붙여주면 디렉토리를 복사한다.


