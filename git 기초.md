### 레포지토리

* 커밋이 저장되는 곳



git init - 로컬 레포지토리 생성

* .git이라는 폴더가 생성이되고 git이 관리하는 모든정보가 여기 들어감(편집하거나 지우면안됨)

git status - 현재 레포지토리에 git이 어떤 상태인가를 체크

README.md - 내 현재 레포지토리에 대한 설명서 같은 역할을 하는 파일(어떤 식으로 작성했는지를 역에 적어서 같이 제출하게 될것)

touch README.md 라고 하면 readme.md파일 생성됨

마크다운 파일 같은 경우 타이포라 연결되어있지 않으면 연결프로그램에 다른앱선택 누르고 타이포라 항상 이앱을 사용해서~ 에 체크하면됨



이 상태에서 git status 해보면 untracked 라고 뜸 

git add .  -> 변경사항 및 모든 정보      (.한개는 현재위치  .2개는 이전위치)

	* staging area로 올리는 역할 
	* git에게 추적하는 파일들을 선언

git add 후 git status 치면 commit을 할 수 있는 상태가 됨을 알 수 있음

git commit을 치면 이메일과 유저네임 입력해야함(글로벌 옵션은 전역에서 이정보를 쓰게됨 하지만 싸피에서는 깃랩도 사용하기 때문에..)

git config user.name "ojh07"

git config user.email "jonghyuck134@gmail.com"    레포지토리한번 만들어지면 다시칠일 없음 

이렇게 하고 다시 **git commit -m "메시지"** 입력해주면 커밋됨



modified(수정)되면 working directory로 가는데 다시 staging area로 올리고 commit 하면 됨 

그리고 git log하면 확인가능



local과 remote 연결하는법은 !!

git remote add origin 주소

git push -u origin master (최초에만 -u)