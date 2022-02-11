# 파이썬 알고리즘 APS 기본

![image-20220209090137705](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220209090137705.png)

알고리즘 : 문제를 해결하기 위한 절차나 방법(유한한 단계)

알고리즘 표현방법은 2가지 ----  의사코드(슈도코드) / 순서도

의사코드로 문제표현할것!

![image-20220209090535312](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220209090535312.png)

__1가지문제에 대한 2~3가지 방법정도 공유하고 고민해보기__

가장 중요한것은 정확성이다



![image-20220209091018689](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220209091018689.png)

그림으로 배우는 수학책?? 정도는 도움될수도,  이산수학, 



실행되는 명령문의 개수, 연산의 횟수에 따라 시간 복잡도가 결정됨

시간 복잡도 - 빅-오(O) 표기법

최고차항만 남긴다, O(1) 은 항상 일정하다는뜻



![image-20220209091623565](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220209091623565.png)

위쪽으로 갈수록 (시간복잡도로만 비교한다면) 효율적인 알고리즘



* 배열

일정한 자료형의 변수들을 하나의 이름으로 열거하여 사용하는 자료구조

![image-20220209092011183](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220209092011183.png)

노트나 A4를 많이 사용(많이 그려보고 써봐야함)



![image-20220209092409512](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220209092409512.png)

크기를 미리 정해놓는것이 빠를수도

![image-20220209092449647](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220209092449647.png)



* 정렬

오름차순 또는 내림차순으로 재배열하는 것

키 - 자료를 정렬하는 기준이 되는 특정값

![image-20220209093146852](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220209093146852.png)

삽입 정렬빼고는 아마 다 언급할 것

sort와 sorted는 사용금지(실전에서는 관계없지만 과목평가와 월말평가때는 사용하지 않는문제가 많음)



<버블정렬>

선택정렬과 헷갈리지 않도록..(**시험**)

![image-20220209093535115](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220209093535115.png)

나에게 주어진 인덱스 범위 확인

비교할때 구간안에서 왼쪽 오른쪽? 기준을 정해야함

첫번째는 왼쪽 정렬시 0->3(N-2까지)

구간을 결정하는 for문 하나, 구간 내부에서 인덱스를 도는 for문 하나

구간 결정은 원소갯수 -1개

비교할 원소중 왼쪽 원소만 세주면 되니까 구간 개수 -1개 



<앞으로 사용할 툴과 사이트>

SWEA로 알고리즘 문제(LEARN-COURSE-PROGRAMMING INTER+ADVANCED)

TALK 에서 solving talk에서도 참고할 수 있음(올릴때는 코드 스니펫으로 업로드해야 그대로 올릴수있음)

code에 problem에 가서는 키워드로 검색하면 몇가지 문제가 나온다(ex:정렬으로 검색..)

툴은 파이참(IDE 통합개발환경) pypy와 python의 문법이 약간은 다를수있어서 pypy를 설치하는 것을 추천

알고리즘 수업은 파이참으로 진행!



빨간점 - 이 줄을 실행하기 전에 멈춰봐 그 후에 디버그 누르면 상태를 볼수있다(중간값)

**디버깅을 배우면 좋다** (프린트문으로 체크해볼때는 그 줄말고 다른줄까지 지우지않도록 주의)



<카운팅 정렬>

항목들의 순서를 결정하기 위해 집합에 각항목이 몇개씩 있는지 세는 작업,   선형 시간에 정렬하는 효율적인 알고리즘

![image-20220209103043887](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220209103043887.png)

![image-20220209103053693](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220209103053693.png)

범위가 주어질것

배열크기가 백만개 이내면 괜찮음

원래 주어진 것을 처리하기 위해 별도의 저장공간을 만든다

**나에게 주어진 정수의 개수를 세는 방법을 꼭 알아두어야한다, 누적하는 방법까지도**

카운트정렬의 1단계까지는 무조건 알아야함

개수 정보를 이용해서 정렬을 하는것이 카운트 정렬

![image-20220209111642573](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220209111642573.png)



![image-20220209111838504](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220209111838504.png)

원래의 조건만큼 만들어놓으면된다(최댓값)

![image-20220209112626201](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220209112626201.png)

배열의 최댓값을 알지 않아도 자료 값의 범위만큼 카운트 배열을 만들어도된다

딕셔너리는 순서가 없기 때문에 주의



## Ground Rule (알고리즘)

알고리즘 = 생각하는 힘(로직)

1. 같이 + 반응
2.  생각 -> 코드로 표현(로직은 여러가지, 각자를 존중)

---

월/수 - 라이브 + web(live 연습문제)

화/목 - 웹엑스 (4문제)

금 - 관통pjt( 4문제 + 남은시간은 보충)

매일 homework가 1문제

화/목/금은 매일 문제푼다고 생각하면됨

---

<완전검색>

모든 경우의 수를 나열해보고 확인하는 기법

경우의 수가 상대적으로 작을 때 유용하다

![image-20220209140804123](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220209140804123.png)



<순열>

![image-20220209141300513](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220209141300513.png)

0부터 r-1까지 -> r개

nPr = n! / (n-r)!



<탐욕 알고리즘>

특정문제보다는 큰 분류?

최적해를 구하는데 사용되는 근시안적 방법(가장 적은 횟수?)

![image-20220209142944536](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220209142944536.png)

거스름돈 줄이기라는 예시에서 봤을 때 상황에 따라 달라진다



카운트할때 counts만들 때 6칸으로 하지 않고 0부터 9까지 10칸으로 해야하는 것 주의!

![image-20220209144853748](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220209144853748.png)

![image-20220209151010302](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220209151010302.png)

이 형태 자주쓸것..

저기 위에서 while num>0:

으로 해준것도 많이사용함!

순서 신경쓰고 for문이나 while, if 구간 얼마나 적용되는지 같은거 신경잘쓰기

![image-20220209152624286](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220209152624286.png)







최댓값 구하는 방법중에 하나

![image-20220209153712161](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220209153712161.png)

![image-20220209153859948](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220209153859948.png)

maxV를 0으로 할당해줘도 되는이유 (10억이하의 자연수이기 때문)

절대값 10억이하인 n개의 정수라고 주어진다면 maxv를 0으로 주면 안됨

큰숫자라도 숫자를 지정하자

2개의 합이 최대인경우..? 같은거는 두번째 방식으로 하면됨



최댓값의 위치는?

![image-20220209154833392](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220209154833392.png)

위치와 인덱스값은 1 차이가 나므로 주의



만약 최댓값이 같은값이 있다면..?(문제에 주어질것, ex 최댓값이 여러개인 경우 맨 마지막 값)

맨마지막이면 if arr[maxidx]<=arr[i]   로 =추가해주면됨(= 넣어서 같은 경우는 또 바꾸면서 오른쪽으로가면서 맨 마지막거)

맨처음값이면 위에 사진 그대로





