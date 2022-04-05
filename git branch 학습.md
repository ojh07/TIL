# git branch 학습



![image-20220405145225119](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220405145225119.png)

![image-20220405145233251](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220405145233251.png)

![image-20220405145302764](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220405145302764.png)

clone은 레퍼지토리 자체를 복사하는 것

pull은 변경사항을 땡겨오는 것

![image-20220405145340145](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220405145340145.png)

conflict해결하기도 해봤음(하나의 파일에서 두사람이 같은 줄을 동시에 수정하려고 할 때)

=> 최종상태를 만들어주고 깔끔하게 파일 만들어서 add commit push 하면 됨



![image-20220405145729944](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220405145729944.png)

git restore --staged file이름  => staging area에서 내려오게됨

실제 파일이 있는 곳(.git이 있는 곳) - working directory

git add 하면 변경사항들이 잠시 머무는 곳 - staging area

git commit 하게 되면 - reqository



![image-20220405150113886](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220405150113886.png)

=>마지막 커밋 이후 모든 변경사항을 이전 커밋 이후로 돌려버림

![image-20220405150233496](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220405150233496.png)

=> 이전 커밋으로 돌아가고 싶을 때(c_id는 돌아가고싶은 커밋의 아이디)



![image-20220405150509652](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220405150509652.png)

![image-20220405150602288](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220405150602288.png)

![image-20220405150821477](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220405150821477.png)

![image-20220405150852801](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220405150852801.png)





브랜치 개념 => 현업에서 자주 쓰게됨

![image-20220405151328423](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220405151328423.png)

![image-20220405151346543](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220405151346543.png)

git은 그대로 pointer만 이동하는 것

![image-20220405151736903](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220405151736903.png)

master브랜치 위에있는 것이 현재 우리의 product

featureA, B는 새로 추가할 기능

master브랜치가 가리키는 c4버전이 사용자들이 사용할 버전임

B2커밋을 가리키도록(C4와 B2를 merge해주세요) => M1이 됨

![image-20220405152302877](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220405152302877.png)

최종버전이 M1이 된다(새로운 버전이 업데이트되었습니다 가 이런 과정으로 이루어짐)

featureA 개발자는 따로 있는데 마찬가지로 M1이랑 A2랑 merge해서 M1처럼 새로운거 또 만들면됨



![image-20220405152339093](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220405152339093.png)

![image-20220405153126325](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220405153126325.png)

feature-a 에서 master로 이동하면 feature-a에 있던거는 사라짐

![image-20220405153433637](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220405153433637.png)

feature-b에서 a로 이동하면 커밋바뀜

branch만 바꿔주면 커밋을 이동할 수 있는것



여기서 feature-b브랜치 삭제하면 4번 커밋에는 아무일도 일어나지 않는다(커밋은 그대로 남아있고 가리키던 포인터만 사라질뿐이다 - 만들어진 history는 사라지지 않음)

![image-20220405153800667](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220405153800667.png)

![image-20220405153845539](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220405153845539.png)

![image-20220405153852603](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220405153852603.png)



merge를 당할 커밋으로 가서 해야함

master로 가서 git merge feature-a해주면

![image-20220405154211761](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220405154211761.png)

feature-b도 개발이끝나서 merge 해주세요

=> 충돌 발생

VSCODE에서 accept both change와 같은 옵션들제공함

add commit 후 merge feature-b해주면 이렇게됨

![image-20220405155533047](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220405155533047.png)

=> merge commit case라고 함(conflict난 상황에서는 무조건 merge commit case로)



여기서 필요없는 feature-a, feature-b 브랜치 삭제

git branch -d feature-a

이미 merge해서 둘다 지워도됨

![image-20220405155741332](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220405155741332.png)

=> 이렇게됨

브랜치는 삭제해도 커밋은 남아있어서 상관없다(대부분 다 삭제한다)



![image-20220405162545764](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220405162545764.png)

![image-20220405172407333](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220405172407333.png)