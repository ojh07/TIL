# Web PJT 반응형 웹페이지 구성



![image-20220211090246226](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220211090246226.png)



* 반응형 웹, Media Query 

고정폭 레이아웃 (브라우저 크기 변화해도 컨텐츠는 변화x)

유동적 레이아웃(이미지 및 글씨 등 영역이 유동적으로 변화) 너비 등을 %로 준 경우..?

최근?에는 디바이스에 따라 별도의 사이트로 구분됨(별도 사이트)

**반응형 레이아웃(디스플레이 종류에 따라 화면의 크기가 자동으로 변함)



Media Query

@media 키워드로 브라우저 및 디바이스 등 환경에따라 css를 적용하는 방법



**브레이크포인트

각각 다넣어줄필요는 없다 (같으면 뒤에거는 상관없다 어차피 앞에애가 적용해주기때문)

![image-20220211093608583](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220211093608583.png)



html/css 는 스타일가이드에 맞춰서 해봐도 좋다(하나의 규칙, 깔끔하게 보이도록)

부트스트랩과 비슷 - BEM (클래스이름..?)



파비콘 

여러개 넣는이유는 브라우저 호환? 맞추기위해서..(디바이스)

![image-20220211101916362](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220211101916362.png)



아이콘

색변경, 사이즈변경도 가능함(이미지와의 차이)



reboot css, normalize css, ....



<bootstrap을 활용한 레이아웃 구성>

문서 탐색능력이 핵심(부트스트랩사이트가 기본, 개발자도구 활용, 코드가 길어지면 접어놓는것이 좋다)

부트스트랩은 클래스싸움이다(어떤 클래스를 적용했는지 보면서 수정도하고!)

일단 css와 js 붙여넣기!!!!!!!!!!!!!!!!!!!!!!!!(주석으로 나눠놓는것도 좋음)

navbar -  아이템들 색이 다르면 active 보면됨(active가 되면 내가 현재있는 페이지를 나타내면서 흰색으로 볼드체가됨)

alt누르고 마우스찍으면 다같이 찍을수있다

이미지 넣고(주소 주의하고), alt는 이미지 안들어갔을때 들어갈 문자?

navbar 위에 고정시키는 방법 - sticky-top(밑요소와는 별개로!-마진을 별도로 안줘도됨),  fixed-top(밑에요소의 위쪽이 navbar만큼 잘린다   nav클래스안에 sticky-top 넣어주면됨)



반응형으로 하기위해 먼저 생각해야하는 것은 그리드, 브레이크포인트

항상 container, row, col 순서로

section.container>div.row>article.col*4 이런식으로하면 빠르게 형태 작성됨

복사할때는 접어서 복사하면 확실히 복사가능

my, mx 등 마진 주는거 기억하기!!(요소들 띄우기)



Modal --------------가장많이 실수한 부분

구조를 이해해야한다

모달의 id    와 눌렀을때  #

![image-20220211110250977](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220211110250977.png)

샵 써주는거 필수

분홍 박스 일치해야하는거 중요



모달은 버튼에 있는 코드에 넣으면 안된다(바디태그안에 젤위쪽에 작성해달라  - 다른요소에 의해 영향을 받을 수 있는 부분을 피하기 위해서)

단순복사가 아니라 버튼이랑 연결작업을 해줘야한다(버튼에 button trigger modal을 넣어줘야함!!!!!!)

modal은 id가 중요하며 id는 문서안에서 하나씩만 사용해야한다- 그렇게해야 각각 동작할수있다

modal안에 form을 넣어주면 이메일형태??같은거처럼 보이게도 가능

무언가는 모달, 폼, 링크 등 눌렀을때 동작은 다르게 설정가능



**빨리하려고 하지말고 천천히 하나씩 순서대로!!**



django에서는 반복문으로 돌려서 중복되는 코드가 없게 web을 만들 수 있다

id는 javascirpt에서 많이 사용됨



**부트스트랩 치트시트에 모든것이 다나와있다**











web 정리

단순 나열된것들 암기(px, 등등...)

선택자 중요!!(id, class, 속성,테이블 등등..),  우선순위 매우 중요

박스모델(컨텐트-패딩-보더-마진)    하나, 둘, 셋, 넷 표현하는것(상하좌우 묶는거)

인라인, 블록요소 각각특징

포지션(스태틱, relative, absolute, fixed, sticky) - absolute와 fixed는 out of flow)

float는 안나오고 flex는 나온다(align-content빼고는 다 기억해야함)   axis, container,...

![image-20220211112045098](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220211112045098.png)

반응형웹 0-- 부트스트랩 (그리드시스템, 브레이크포인트 기억하기 )

![image-20220211112137519](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220211112137519.png)

![image-20220211112151303](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220211112151303.png)





![image-20220211112537832](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220211112537832.png)

a태그, 등등 여러가지 태그별 속성들 기본적으로 알아야함

레이아웃은 flex(부트스트랩은 d-flex,     justify-content 이런거..) 사용하면 웬만하면 다 가능함

개발자도구보면서 맞춰가는것

스타일은 컬러, 사이즈, 배경색, 각태그별 속성 등...



### 웹개발

마이리얼트립 최적화(해외에서 로딩속도나 그런거 최적화..?)

animate.css 

animate.css cdn 검색후 적용가능!!!





문서읽는 능력(영어가 중요할듯..!!!!)







-----

------





# web 과목평가

html은 각태그별로 가질수있는 속성

inline요소 대표적으로 a, span(inline요소에는 마진탑바텀, 너비, 높이설정 불가)



css

선택자 매우 중요함!!(24단계정도까지만 봐도 됨- 선택자 게임)

물결, 플러스, 곱하기, 콤마 등 여러가지 다 알아야함

박스모델(콘텐트-패딩-보더-마진)

요소와 요소 떨어뜨리는건 마진줘야함

포지션, 디스플레이 ( 블록, 인라인, 인라인-블록)



css layout(2번째 피피티에서 문제 많이나옴)

flexbox,  grid,  bootstrap 이렇게 3개가 가장 중요

float는 아예안나옴

flexbox에서는 container row col 

ex : flex-direction은 container에 주는 옵션

가운데정렬 하는방법 같은거 알아야함



기타속성은

flex-grow 만 보면됨   width를 보고 창을 잡아끌었을때 어떻게 되는지 

수직수평정렬 중요



align-items와 align-self가 다른점  ---> items는 2줄이상 self는 1줄

우선순위는 self가 높다



bootstrap -- > 문제가 많이나올것

spacing-- mt, mx, my, 이런거 알아야함

mt-1이라면 1이 무엇인지    (1은 0.25rem이고 4px이다)

1rem은 16px

spacing종합 부분 ( t, b, s ,e x, y // m, p 이런거)



색상 어떻게 설정할 수 있는지 (색상이름, rgb, #... rgba(투명도) 이런거)

#000000   검은색, 흰색 같은거 나올것

rgb에서는 숫자범위가 0에서 255

r에 0 g에 255 b에 0 이면?? 이런거(나머지 0이고 하나 극단적일때 어느색상인지는 알아야한다)

부트스트랩의 색상표현은 알아야한다(primary는 파랑 이런거)



d- 하면 display 설정하는것



flexbox를 부트스트랩에서 어떻게사용하는지 알아야한다

d-flex ~~~



반응형웹(그리드)

컬럼 몇개 구성인지, 왜 그 숫자인지, 브레이크포인트

col - A - B               -------->이 형태 매우중요

A는 뷰포인트사이즈, B는 컬럼(12개로 이루어짐)

A는 브레이크포인트((none), sm, md, lg, xl, xxl) - 6개

브레이크포인트 기준으로 반응형이 완성됨

변화하는 포인트는 알아야한다

sm md lg 기준으로 스마트폰, 태블릿, 데스크탑





피피티만 보아서는 안된다

지금 집어준 키워드들 공식문서 참고하기 !



부트스트랩으로 그리드시스템 구현할때 어떤 요소필요한지

container, row col 이 3개!!



**그리드 시스템 브레이크포인트 연습하는 거 1장으로 주신거 연습해보기**

**col 블럭 그림주어지고 col-## 어떤 숫자 들어가야하는지 이런거 문제로나온다**



어떻게 구현해야하지 라는거 시험에 나온다

