#### pic1 ~ pic24

![demo](/demo/pic1.png)  
* aws 로그인 후 AWS 서비스 검색창에서 codestar를 검색한다. 
![demo](/demo/pic2.png)  
* codestar 서비스로 들어가서 화면 가운데 있는 프로젝트 시작을 선택한다. 
![demo](/demo/pic2_1.png)
* 이후 나오는 선택창에서 YES를 클릭후 프로젝트 템플릿을 선택해야 한다. 
![demo](/demo/pic3.png)   
* 애플리케이션 범주를 웹 어플리케이션과 프로그래밍언어 Ruby를 선택해준다. 
![demo](/demo/pic4.png)   
* 선택 후 남은 EC2 인스턴스 와 Elastic Beanstalk중 EC2 인스턴스를 선택해준다. 
![demo](/demo/pic5.png)   
* 프로젝트 이름을 적당하게(likelion)정해주고 다른부분은 건들이지 않고 다음을 눌러준다. 
![demo](/demo/pic6.png)   
* 프로젝트 세부 정보 검토 화면 > EC2 구성은 기본적으로 t2.micro(free tier)로 되어있다. 바로 다음으로!
![demo](/demo/pic7.png)   
* 키 페어 선택을 요구한다. 
![demo](/demo/pic8.png)   
* 새창으로 넘어가 AWS EC2 서비스로 이동한다. 
![demo](/demo/pic9.png)   
* 리소스 중에서 키 페어를 선택해준다. > 키페어 생성 클릭(likelion) 그리고 진행...
![demo](/demo/pic10.png)   
* 다시 codestar로 넘어와 키 선택창 오른쪽의 새로고침을 누르면 키를 선택할수있다. 
* 하단부 체크박스를 선택하고 프로젝트 생성을 클릭
![demo](/demo/pic11.png)   
* 코드를 편집할 방법을 선택한다. AWS에서 ALL IN ONE 하게 실행하기위해  CLOUD9을 선택해준다.  
![demo](/demo/pic12.png)   
* Cloud9 환경설정을 디폴트에서 바꾸지 않고 넘겨준다. 이후 IDE 세팅과 이외의 다른 설정들을 자동으로 해준다.  
![demo](/demo/pic12_1.png)   
* 첫세팅에서는 조금 오래 걸릴수도 있다.  
![demo](/demo/pic13.png)   
* 파이프라인을 선택해 들어가면 진행중인 과정들을 한눈에 볼수도 있다. 
![demo](/demo/pic14.png)   
* 1~2분까지 기다리다보면 데시보드가 생기기 시작한다. 
![demo](/demo/pic16.png)   
* 어플리케이션 엔드포인트가 나온다면 해당 엔드포인트를 선택해서 기본 설정으로 배포된 웹 어플리케이션을 확인할수있다. 
![demo](/demo/pic17.png)   
* 첫 빌드와 배포여서 오랜시간이 걸린다. 모든 작업이 init되기때문에 잠시 기다려야 한다.
![demo](/demo/pic18.png)   
* 배포가 완료되지 않아도 엔드포인트는 생성되므로 어플리케이션이 나오지 않는다면 배포가 완료됬는지 확인한다. 
![demo](/demo/pic16.png)   
* 배포가 되는것을 잠시 기다리는 동안 주의 사항을 살펴본다. 
![demo](/demo/pic18_1.png)   
* 켜두었던 EC2 키페어 창에서 좌측 navbar 에서 인스턴스>인스턴스 로 이동한다. 
![demo](/demo/pic19.png)   
* 인스턴스가 두개 생성되어있다. 이는 본인의 웹 어플리케이션과 cloud9 서버에 해당한다. 
* 프리티어 ec2 가 두개로 사용한다면 과금이 될수있으니 데모이후 삭제하는것을 권한다. 
![demo](/demo/pic20.png)   
* 다시 codestar 대시보드로 와서 배포를 확인하면 '성공'이다.
![demo](/demo/pic21.png)   
* 엔드포인트 주소로 들어가면 AWS에서 설정해둔 기본 Rails 템플릿이 나오는것을 확인할수 있다. 
![demo](/demo/pic22.png)   
* 이제 코드 수정을 간단하게 하고 세션을 마무리 하겠다. 대시보드 우상단에서 코딩시작이나 내환경보기에서 IDE 열기를 클릭하면  Cloud9이 켜진다. 
![demo](/demo/pic22_1.png) 
![demo](/demo/pic22_2.png) 
* 본인의 Cloud9/IDE 세팅을 우선으로 하고 코드를 수정하면된다. 
![demo](/demo/pic23.png)   
* 본인은 깃 기본 설정과 IDE 색상만 바꾸고 바로 진행 하겠다. 
![demo](/demo/pic24.png)   


#### [중반부](demo2.md)
#### [README](README.md)