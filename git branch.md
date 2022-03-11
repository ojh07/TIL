git branch

독립적으로 작업(다른사람과 협업시에 같은 환경에서 가능하도록)



master - branch중에 가장 중심이 되는 것(원본)



하나의 작업은 하나의 브랜치로 진행(관리 측면에서 체계적인 개발이 가능)

master branch는 상용(언제든 세상에 공개가 되어있다, 실제 서비스로서 사용되는 역할)

master는 맘대로 건드릴 수 없으므로 다른 별도의 브랜치를 만들어서 master에 영향을 주지 않도록해서 작업 후 master에 반영



로컬 저장소로 지정 -> git init   -> master가 뜸

git branch -> branch 목록 확인

git branch 브랜치 이름 -> 새로운 브랜치 생성

git branch -d 브랜치 이름-> 특정 브랜치 삭제(병합된 브랜치만 삭제)

git branch -D 브랜치 이름 -> 강제 삭제

git switch 브랜치 이름-> 다른 브랜치로 이동   -> 완전 독립된 환경

git swtich -c 브랜치 이름-> 브랜치를 새로 생성과 동시에 이동(브랜치 생성 과정 생략 가능) 

git merge 병합할 브랜치 이름 -> 병합 (merge하기 전에 다른 브랜치를 합치려고 하는, 즉 메인 브랜치로 switch해야함)

* fast-forward

merge가 최신버전으로 앞으로 나아가는것(HEAD가 앞으로 나간것) -> 이미 병합된 브랜치는 지워주면됨

* 3-way merge(merge commit이 새로생김)

공통조상 하나를 이용해서 병합 -> 새로운 버전이 하나 생김

* merge conflict(merge를 했을 때 충돌한 상황 - merge하는 두 브랜치에서 같은 파일의 같은 부분을 동시에 수정하고 merge하는 경우 git은 해당 부분을 자동으로 merge하지 못함), 동일 파일이라도 서로 다른 부분을 수정했다면 conflict없이 자동으로 merge commit된다

conflict 이후의 commit은 git commit 이후 -m "" 이거 작성하지 않아야한다

그러면 vim 에디터가 뜬다 -> esc누르고 :wq enter 해주면 됨





git status

git add . (add해주지않으면 git의 관리를 받고 있지 않는것)

git commit -m ""

git log   (git log --oneline) -> 한줄로 확인

git log --oneline --all 해주면 어떤 브랜치에서건 모든 브랜치 확인가능

git log --oneline --all --graph  해주면 어떻게 브랜치가 갈라지고 있는지 시각적으로 볼 수 있다

git branch 해주면 어떤 브랜치 있는지 볼 수 있다

HEAD는 지금 어떤 브랜치를 가리키고있는지를 보여줌

merge - 독립된 공간(브랜치에서 작업)에서 작업하고 마스터로 병합하는것