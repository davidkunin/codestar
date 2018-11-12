#### 오류 있는 버전 pic25 ~ pic33

* 기본적으로 hello_page 컨트롤러 뷰 가 설정되어있는것을 확인할수 있다. 
![demo](/demo/pic25.png)   
* h1,h2 태그만 간단하게 바꾸어 보자 > 수정!
![demo](/demo/pic25_1.png)   
* 바로 깃 에드 커밋 푸시 !
* 여기서 주의 할것이 해당 터미널의 위치가 프로젝트 파일안으로 가야 한다. 
![demo](/demo/pic26.png)   
* 푸시가 끝나면 codestar 대시보드를 새로고침 해보면 커밋이 진행되고 빌드, 배포까지 자동으로 되는것을 확인할수 있다. 
![demo](/demo/pic27.png)   
* 이는 pipeline 메뉴에서 좀더 자세히 알수 있다. 
* 코드를 작성만 하면 수 분만에 배포까지 자동으로 되는것을 확인할수있다. 이러한 방식을 서버리스 라고 할수있다.
![demo](/demo/pic28.png)   
* 잠시 기다려보면 코드가 빌드가 실패한것을 알수있다. 
![demo](/demo/pic29.png)   
* 코드 빌드로 들어가서 로그를 살펴보자 알고보니 기본 페이지가 템플릿으로 설정되어서 코드를 수정하면 오류가 나오는것을 알수있다. 
![demo](/demo/pic30.png)   
* error가 나온부분을 찾아가보면 어디위치에서 error 가 나왔는지 확인할수있다. 해당위치로 가보자
![demo](/demo/pic31.png)   
* spec > controller 안의 rb 파일이다. 파일을 보면 body 안쪽에서 Congratulations이 있어야 정상 작동되는것을 알수있다. 
![demo](/demo/pic32.png) 
* ctrl + z 로 h1은 원상복귀 시키고 h2만 수정해서 깃 에드 커밋 푸시 !
![demo](/demo/pic33.png)   

#### 오류 없는 버전 pic34
* h2를 바꾸고 깃 에드, 커밋, 푸시 !
![demo](/demo/pic34.png)

#### [전반부](demo1.md)
#### [후반부](demo3.md)
#### [README](README.md)