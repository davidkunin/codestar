#### 합쳐지는 지점 pic35 ~ pic 46
* 잠시동안 커밋, 빌드, 배포를 기다려주면 페이지가 나오는것을 확인할수있다. 
![demo](/demo/pic35.png)
* 수정까지 끝났으면 codepipeline을 조금 살펴보는것으로 마무리 해보겠다. 
![demo](/demo/pic36.png)
* 파이프라인 우상단의 편집을 선택해보면 스테이지를 본인이 편한대로 추가/삭제/편집 할수있다.
![demo](/demo/pic37.png)
* 편집: Source 오른쪽의 스테이지편집 선택
![demo](/demo/pic38.png)
* 간단하게 remote 저장소를 추가해보자. 작업 추가 선택!
![demo](/demo/pic39.png)
* 작업 이름(githubremote), 공급자 github 설정 ( 작업이름은 공백NO)
![demo](/demo/pic40.png)
* 깃헙에 연결을 선택 하면 github 로그인 창이 나온다.
![demo](/demo/pic41.png)
* 로그인 하기전 연결할 github 레포지토리를 한개 만들고 오자.
![demo](/demo/pic42.png)
* 레포지토리가 완성됨을 확인하고 다시 돌아가서 로그인을 한다.
![demo](/demo/pic43.png)
* 레포지토리(codestar_likelion) 선택,브랜치(master) 선택후 변경탐지옵션은 webhook선택, 출력 아티펙트는 편한대로(doingtest)하고 저장
![demo](/demo/pic44.png)
* 성공적으로 작업이 끝난것을 확인할수있다. 완료를 누르고 저장 
![demo](/demo/pic45.png)
* 파이프라인 변경사항 저장 세부사항을 한번더 알려준다. 저장.
![demo](/demo/pic46.png)

#### 깃 리모트(origin/github) 푸시 따로 하기 pic47 ~ pic50
* cloud9으로 돌아와서 코드를 일부 수정하고(h3) 깃 에드 커밋 리모트 푸시(git push github master)를 해준다.
![demo](/demo/pic47.png)
* 리모트가 연결된 깃헙을 들어가면 코드가 반영된것이 확인된다. git push origin master origin저장소로 푸시해준다. 
![demo](/demo/pic48.png)
![demo](/demo/pic49.png)
* 파이프라인이 다 실행되고 웹 어플리케이션을 새로고침하면 페이지에 변경사항이 적용된것이 확인된다.
![demo](/demo/pic50.png)

#### 깃 리모트 합쳐서 푸시 한번에 하기  pic51 ~ pic54
* cloud9으로 돌아와서 코드를 일부 수정하고(h3) origin 리모트에 저장소를 추가해준다. 
![demo](/demo/pic51.png)
```
 $ git remote set-url --add --push origin https://github.com/lee-sj/codestar_likelion.git
 $ git remote set-url --add --push origin https://git-codecommit.us-east-2.amazonaws.com/v1/repos/likelion
 여기서 순서는 어떤곳에 먼저 푸시를 할것인지이다.
```
![demo](/demo/pic52.png)
* 한번에 푸시가 두곳으로 된것을 확인했고, github 과 파이프라인을 확인하고 앱을 확인하면 변경사항이 적용된것을 알수있다. 
![demo](/demo/pic53.png)
![demo](/demo/pic54.png)

### 데모 끝! 
* 코드스타 여러가지를 살펴보면서 기능을 좀더 탐구해보는것을 추천한다. 
* 데모가 끝났으니 EC2 에서 codestar 인스턴스를 종료해준다. 
* 종료하면 codestar가 정상작동 하지 않을수 있으니 codestar 기능을 사용하고자 한다면 IDE 선택에서 cloud9이외에 다른것을 선택해서 해보면된다.

#### [전반부](demo1.md)
#### [중반부](demo2.md)
#### [README](README.md)

### 다운로드 링크
<a href="https://drive.google.com/file/d/1HPKM1AsugT56hOquO3Q_0ovtypQqtPY_/view?usp=sharing" download>PDF Download</a>