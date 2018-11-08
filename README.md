AWS CODESTAR
=

### 서버리스?  
    - 서버에 대한 고민 없이 애플리케이션을 구축 및 작동  
    
![alt text](/images/serverless.PNG)  

서버리스는 그 단어의 뜻처럼 서버가 없는것이 아니라 서버가 없는것 처럼 세팅이 간편해지고 있다는 뜻이다.  

### serverless computing의 이점
![alt text](/images/positive.PNG)   

그렇다면 이를 어떻게 하면 쉽게 코드만 작성해서 배포까지 할수 있게 되었는가? 
![alt text](/images/framework.PNG)   
오픈소스 프레임워크들이 생겨나고 있고, AWS 에서도 이를 만들게 된것이 AWS SAM (serverless applicatioln mdoel)이다.   
CloudFormation 기반이고, 람다함수와 기타 리소스도 배포하며, 정해진 템플릿에서 공개표준기반 (아파치2.0)으로 만들어졌다.  

일반적으로 개인이 혼자서 서버리스 앱을 만들고 개발 배포하는것이 쉬운것은 아니다.   
### 일반적인 개발 및 배포 단계
![alt text](/images/normal.PNG)   
### AWS 기반 개발 및 배포 단계 - 통합 개발환경
![alt text](/images/aws_dev.PNG)   

codestar와 c9으로 빠르게 서버리스 개발 및 배포 환경구축
클라우드 기반 IDE를 통한 개발 협업
바로 앱 패키징 및 자동 배포 가능

### 서버리스 앱 개발 및 배포 과정 
* AWS CodeStar로 샘플 앱 프로젝트 (API 호출 시 간단한 HTML 파일 출력) 배포  
* 소스코드, 빌드, 배포 및 파이프라인 서비스 살펴보기
* 각종 AWS 리소스 생성 내역 확인하기
* AWS Cloud9 기반 클라우드 IDE로 수정 및 배포하기

### 데모 시작!

