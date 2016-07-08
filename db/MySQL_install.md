#MySQL install

###homebrew install
- macOS용 패키지 관리자
- 공식 사이트에서 dmg파일로 설치파일을 제공하지 않는 패키지도 Homebrew에서 다운받을 수 있다.
- http://brew.sh/
-
````
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
````
- $ brew -v

### MySQL install
````
 $ brew install mysql
````
````
$ mysql.server start
````
````
$ mysql -uroot
````
````
$ quit;
````
````
$ mysql.server stop
````
