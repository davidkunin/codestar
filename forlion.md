서버리스라고 하면 서버가 없다고 생각할수 있다. 
이는 데이터 센터에서 세팅해주는것을 몇주만에 해주는것을 몇초만에 해주는것을의미해졌다. 
데이터 센터 > 가상서버amazon ec2 -> 콘테이너amazon ecs -> 서버리스 aws lambda

서버리스 컴퓨팅의 이점
서버 준비나 관리 불필요
함수 실행 시간만 과금
사용량 기반 자동 확장
고가용성 및 손쉬운 배포가 가능해진다. 

이러한 서버리스 컴퓨팅이랑 aws lambda 가 나오면서 대중화 되기 시작했다. 
처음 시작할때는 이벤트 소스가 있을때 그 소스에 대해서 프로그램을 실행하는 니즈가 있어서 나오게 되었다. 
이미지의 업로드에서 썸네일등을 만들때 등등의 간단한 서비스 에서 
이때 람다가 실행하면 그 기능만 작동하고 끝나는 식으로 람다가 작동할때만 과금이 된다. 

람다는 비동기적인 실행에 의해서 혹은 동기적으로 API  등을 호출할때 
그리고 데이터가 스트리밍으로 들어올때도 사용하고 있다. 
서버리스 웹 애플리케이션 

기존에 서버에 배포하지 않고 html css javascript 등을 CDN으로 제공하고 이를 람다로 제공하고 이를 API 게이트로 실행한다. 

in ppt 
Amazon S3 에 HTML, CSS JS 이미지 등의 정적 콘텐츠를 제공하고 이른 cloudfront 와 같은 CDN 서비스로 사용자에게 제공
HTML 에서 REST API 요청시, 사용자 인증 및 권한 확인 및 DDos 방어 등의 기능 수행후 AWS lambda에 이벤트 호출 
Lambda 함수가 비즈니스 로지긍 수행하고 데이터 베이스 및 다른 백엔드 서비르를 연결하여 필요한 기능 수행

이러한 것들을 많은 사람들이 사용하기 시작했다. 

그렇다면 이를 어떻게 하면 쉽게 배포할수 있을까 
>> 오픈소스로 프레임워크들이 많이 실행되고 있을까로 판단하게 된다. 

AWS 에서도 이를 만들게 되어서  AWS serverless applicatioln mdoel  SAM 
Cludformation 기반으로 배포 하고 

서버리스 앱을 만들고나서 개발 배포하는것이 쉬운것은 아니다. 

깃헙같은  AWS codecommit 소스 관리 
코드 빌드는 젠킨스 같은 코드 빌드를 해준다. 
테스트도 UI 나 API  등을 사용하고 
배포도 codedeploy 등을 사용할수 있다. 
여기에 다양한 또다른 AWS 서비스들이 붙어지고 이를 순서도로 만들어주는 
code pipeline을 쓸수도 있고 인증도  AWSiam 을 사용할수도 있다. 

이렇게 굉장히 많은 세팅할것들이 있는데 
AWS 가 자체적으로 이런것들이 합쳐진 Codestar 를 만들게 되었다. 나머지 서비스들을 한꺼번에 세팅하고 자동화해준다. <팀단위에서도 손쉽게 진행하게 해준다. 
이를 c9을 통해서 개발 자체도 클라우드를 통해서 진행할수있게되었다. 

이렇게 되면 
ide 를 세팅하고 스택과 ci/cd를 파이프라인으로 만들고 , 이를 코드 개발을 통해서 배포 까지 갈수 있다. 

데모 시작 
node.js 앱 한개 를 데모로 만들어 본다. 
코드스타 클릭  이후 가운데 있는 프로젝트 시작 클릭 언어별로도 확인할수있다
aws lambda 에 들어가고 node.js 프로젝트 템플릿 선택 하고 여기서
코드커밋을 통해서 진행하고 프로젝트 이름을 설정하고 다음 선택 
이렇게 하면 코드 커밋에 샘플 앱이 배포가 된다. 그리고 빌드와 배포 모니터링까지 한번에 진행한다. 
프로젝트 생성을 누르면 코드 편집할 방법을 선택하고 
클라우드9을 생성하고 t2 마이크로로 기본 세팅을 한다. 첫 세팅에서 는 조금 오래 걸릴수 있다. 코드 커밋을 확인하면 기본으로 어떻게 세팅되어있는지 간단히 확인해보면 aws 람다 함수가 있다. 이는 호출이 들어오면 퍼블릭 밑에 있는 index.html을 가져와서 뿌려주는것이다. 
빌드 스펙을 확인해보면 npm 을 설치하고 pip 도 설치 그리고 s3로 카피를 하고 이를 클라우드 포메이션으로 패키징하는 빌드에 대한 빌드 패키징 예시이다. 이렇게 잠깐 살펴보면
프로젝트가 성공정으로 세팅 되었고, 배포는 되어있지는 않고 빌드를 하고 디플로이를 하면 되는 상태까지 된것이다. 이 세팅은 처음에만 이렇게 조금 시간이 걸리고 다음부터는 조금더 빠르게 진행된다. 코드 빌드를 확인해보며 이미 완성되있지만 코드빌드를 통해서 완성된것이 코드스타에 적용되는 시간이 잠깐 딜레이되는것이다. 

이러한것을 전체적으로 한번에 하는것을 코드 파이프라인이라고 한다. 지금 파이프라인을 보면 빌드와 디플로이가 완료된것을 알수 있다. 이때 
본인이 해당 프로젝트에서 추가로 단계를 넣을수도 있고 빌드를 하기전에 어떤것이 있는지도 확인 할수 있고 이를 수동 인증을 추가로 넣을수도 있다. 

이때 추가적으로 서드파티투를 넣을수 있다. 
예를 들어서 아틀라시안에 있는 지라 이슈 트레커를 넣을수도 있다. 혹시나 사용하고있다면 이를 사용해서 디플로이 할수도 있다. 
그리고 팀원을 추가해서 커밋등을 다른 팀원들이 할수있게 도와주기도 한다. 
그리고 확장을 통해서 깃헙 연결까지고 가능하다. 
이 프로젝트에서 코드스타를 통해서 씨나인 코드커밋 빌드 파이프라인 등등이 모두 완성된다. 

배포를 통해서 실제로 배포되고있는것을 확인할수 있다. 그리고 이제 람다에 가서 실제로 람다가 만들어져있는 상태를 확인할수 있다.

aws 검색을 통해서 람다로 가면 코드스타로 만들어진 람다함수를 확인할수 있다.  
클릭해서 확인해보면 클라우드 포메이션으로 관리되서 마음대로 변경을 하면 안된다. 

 api 게이트 웨이는 엔드포인트가 나왔을 때 람다함수로 이벤트를 보내고 받아서 그것을 호출을 통해서 실행해서 결과를 반영하는것으로 확인이된다. 
실행해보면 퍼블릭에 들어와있는 html 을 받아온다. 이를 클라우드 나인을 통해서 수정배포를 해보자 . c9 은 웹브라우저를 통해서 확인할수 있다. 

첫 세팅이후 node.js 는 이미 세팅이 되어있고 기본 깃 세팅을 미리 해준다면 (깃 컨피그 두개 모두 실행 ) 
그리고 콘솔 한개씩 확인 시작 하z고 퍼블릭의 인덱스를 수정하고 수정사항을 업데이트 시켜보자. 글자 바꿔보고 깃 에드 커밋 푸시 하면 코드 커밋에 푸시가 되는것이다.
그러면 푸시가 되자마자 자동으로 배포가 시작된다. (변경사항에 대해서 )







파이프라인 추가 >> action 추가로 source 에서 코드커밋이랑 깃헙 동시에 추가 가능한 엑션 릴리즈 되고있는 중에는 안된다. 
