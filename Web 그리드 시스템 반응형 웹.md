# Web: 그리드 시스템/ 반응형 웹



인라인 요소 가운데정렬 -> text-align

relative top bottom 공간줄수있음

## CSS Layout

![image-20220207090744562](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220207090744562.png)

### Float(위로 뜬다)

인라인은 상하에 대한 마진을 줄 수는 없다(컨텐츠 영역만큼만 가져가기 때문에 너비, 높이도 지정불가)   span, input, img

블럭은 마진 오토 지정해서 정렬할 수 있다(좌, 우, 가운데) div, h1, p(문단)

![image-20220207091642851](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220207091642851.png)

![image-20220207091732108](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220207091732108.png)

텍스트 채워넣을 때 ---> Lorem ipsum(더미텍스트)            vscode에서 lorem300하면 글자가 생성됨

한글은 한글 입숨이라고 치면 됨

clearfix는 float에 left나 right 적용했을 때 딸려올라오는 것 방지

float 요소의 부모로 div 지정해야함!!!

그리고 content부터 clear 까지의 안의 내용이 중요한것

![image-20220207093935241](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220207093935241.png)

css after라고 검색해보면됨

clear 속성부여 _-- 부모요소에!

![image-20220207094549665](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220207094549665.png)

이후로는 float에 영향이 가지 않도록 하는것이 clearing



일열로 나열되어있는것은 보통float로 해놓는 경우많음(인라인 형태로도 가능하지만)

mdn float 쳐보면 내용이 많이나온다

inline에 float부여하면 블럭으로 바뀌면서 적용됨



네이버 사이트에서 확인해보기!!!



### Flexbox

CSS Flexible Box Layout

행과 열 형태로 아이템들을 배치하는 1차원 레이아웃 모델(메인 축을 기준으로 - 메인과 수직이 되는것이 교차축)

![image-20220207100622946](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220207100622946.png)

flex-direction이 column이면 반대로됨



![image-20220207100704873](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220207100704873.png)

수동값 부여없이 수직정렬, 아이템의 너비와 높이, 간격을 동일하게 배치 가능



![image-20220207100933008](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220207100933008.png)

1) flex - direction

역방향은 html 태그 선언 순서와 시각적으로 다르니 유의(웹 접근성에 영향)

2. flex-wrap(nowrap이 기본값(한줄에 정렬))

![image-20220207101525846](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220207101525846.png)

justify-content

start, end, center는 남은 공간을 각각 기준에 따라 맞춰놓은것

space- between(남은 공간을 아이템 사이에), around, evenly 



align-content(공간배분)는 사용할일이 거의 없음

align-items를 더 많이 사용

cross축을 기준으로 정렬

align-self(개별 아이템을 cross축 기준으로 정렬 -  컨테이너에 적용하는 것x)



![image-20220207103410976](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220207103410976.png)

블럭 가운데 정렬하는 법

flex기본방향이 행이다(가로)



flexbox froggy 라는 것으로 연습해볼 수 있음





오전 시간 --- float, flex   

flex는 새로운 패러다임!!!(기존에는 문서기준이었다면 축과 컨테이너라는 개념을 통해 컨테이너 안에서 편리하게 아이템을 배치할 수 있도록)

flexbox안에서는 마진오토로 수평수직 가운데정렬가능

selectors, selectors 심화 ---> 시험자주나옴

----

----

## Bootstrap

spacing

유틸리티, 컴포넌트



mx-0이면 mx는 x축이라서 마진 좌우가 0

my도있음

py-0이면 padding top, bottom을 0으로

이렇게 다양함

bg-

text-

색이름 쳐주면 됨

우리가 배웠던 것들이 모두 클래스로 만들어져있다

----

### Bootstrap Grid System

![image-20220207150809569](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220207150809569.png)

![image-20220207150935239](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220207150935239.png)

부트스트랩은 기본적으로 cdn을 붙여넣으면됨

![image-20220207151309921](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220207151309921.png)

small

medium

large

각 단계를 보면됨!

개수로 나눈것이 col-sm-숫자가 됨

띄우고싶은것은 offset



핵심 : 컨테이너를 하나두고

그 아래에 row를 하나씩 둔다(만들고자하는 행)

row안에 col-~~~ (~~~이 브레이크 포인트-- sm, md, lg....),  그 뒤에가 숫자(12중 몇개로 가져갈것인지)

*1:2:1일 때어떻게해야 하는지, 브레이크포인트 등 시험문제 내기 쉽다!!**

