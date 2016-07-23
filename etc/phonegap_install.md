#phonegap install

- phonegap 설치
````
sudo npm install -g cordova
````
- 비밀번호 입력
- 폴더 이동
- project 생성
````
cordova create 폴더이름, 프로젝트명, app이름
````
- 프로젝트 폴더로 이동
````
cd 폴더이름
````
- platform 생성
````
cordova platform add android
cordova platform add ios
````
- wwww/index.html
- 프로젝트 폴더에서 빌드
````
cordova build android
cordova build ios
````
- 에뮬레이터
````
cordova run android
cordova run ios
````
or
- 모두 빌드
````
cordova build
cordova run
````
###다른 방법
- phonegap 프로젝트 압축 후 업로그
- https://build.phonegap.com/

