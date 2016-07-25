#git Checkout conflict with files

- eclipse
 - Team -> Pull
````
Checkout conflict with files: 대상 파일 (ProjectName/source/file...)
````
- Source 파일이 Commit되지 않아서 발생한 문제이다.

###해결
- Team -> Commit
- Team -> Pull
 - 자동으로 Merge or Conflict 발생
- Conflict가 발생했다면 해당 파일의 충돌 부분 해결
- Index에 추가
 - Team -> Add to Index
- Team -> Commit -> Commit and Push