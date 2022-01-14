# Git이란?

### 분산 버전 관리 시스템

- 코드의 **히스토리(버전)**을 관리하는 도구
- 개발되어온 **과정** 파악 가능(에러 발생시 얼마든지 이전버전으로 돌아가는게 가능)
- 이전 버전과의 **변경 사항 비교 및 분석**(어떻게 변경되어왔는지를 볼 수 있어서 무엇이 추가되었는지 알 수 있음)



분산 <-> 중앙집중

중앙집중형 - 은행

분산형 - 블록체인(모두가 거래내역을 가지고있음 -> 하나의 파일이 변조되어도 이전파일과 비교해서 잡아낼 수 있음) -> 분산형의 장점



#### Git과 GitHub의 차이

* Git - 분산버전관리 시스템

* GitHub - Git기반의 저장소 서비스



#### 간단한 Unix/Linux 명령어



* 현재 위치의 폴더, 파일 목록보기 **ls**
* 현재 위치 이동하기 **cd<path>**

​                                         **cd..** 상위폴더로 이동

* 폴더 생성하기 **mkdir<name>**
* 파일 생성하기 **touch<name>**
* 삭제하기 **rm<name>**

​				       **rm -r<name>**



**특정버전**으로 남긴다 = **커밋(commit)**한다

커밋은 **3가지 영역**을 바탕으로 동작

* working directory - 내가 작업하는 실제 디렉토리
* staging area - 커밋으로 남기고 싶은, **특정버전**으로 관리하고 싶은 파일이 있는 곳
* repository - 커밋들이 저장되는 곳



git **status** - 현재 git으로 관리되고 있는 파일들의 **상태**를 알 수 있음

git **add** . - 추적 되지 않은 모든 파일과 추적 하고 있는 파일 중 수정 된 파일을 모두 staging area에 올림

git **commit** -m "commit_message" - 커밋메시지는 **자세하게!**

git config user.name "user_name"

git config user_email "user_email"



git diff -> commit ID 앞에 4자리만 적어도 비교가능



#### Github 시작하기



git **remote** add origin{origin_repo}

git **push** -u origin master

git **clone** {remote_repo}  - remote repo를 local로 복사

git **push** origin master  - local repo의 최신 커밋을 remote repo로 push함



**push**는 local에서 remote로 변경사항 보냄

**pull**은 remote에서 local으로







