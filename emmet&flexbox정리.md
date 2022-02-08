# emmet

- `>`  태그를 만들고 들여쓰기
- `*n` 반복
- `+` 줄바꿈 + 다음 태그 추가
- `.` class 지정
- `#` id 지정

- `{content}` 내용 입력





### Float

float는 normal flow를 벗어난다

아래있는 애들이 계속 위로와서 감싸게 되기 때문에 (float를 사용하면 다음요소들의 정렬이 저절로 원래있던거 다음으로 오는데 그걸 지우려면 clear해야함)

클리어하는 애부터는 플로트의 영향을 받지않음

clear:both를 많이씀

: 하나는 의사클래스     :: 2개는 의사요소(가상으로 만들어줌)    

.container::after

content:""

display:block

clear:both

이건 한묶음

묶어서 한번에 clear해주는게 훨씬편함...?



### Flexbox

인라인블록 - float처럼 쓸수있음

수직구조는 원래 자동으로 되기때문에 쉬움

수평구조가 어렵다



**컨테이너와 아이템으로 이루어져있다**

수평이 될 요소들을 컨테이너에 넣는다

그 컨테이너에 디스플레이:플렉스 해주면됨

**아이템, 컨테이너에 적용되는 속성들이 정해져있다******

* contatiner에는 dispaly, justify-content, flex flow .... ..

* item에는 order, flex, align-self..... 등이있다



### display



<컨테이너에 들어갈 수 있는 속성들    Flex Container 속성들>

- `display` - Flex Container를 정의

flex,     flex-inline이 있음

flex는 블럭방식의 컨테이너(컨테이너가 밑으로 그냥쌓임)

flex-inline - 인라인 방식의 컨테이너(컨테이너가 옆으로 쌓임)

- `flex-flow` - `flex-direction` 과 `flex-wrap` 을 줄여서 쓸 수 있음

flex-flow: flex-direction flex-wrap 순서중요함

- `flex-direction` - item들의 주 축(main-axis) 설정

기본값은 row이고 row-reverse,   column,   column reverse 4종류가 있다

- `flex-wrap` - item들의 줄 바꿈 설정

아이템들을 여러줄 묶을 방식을 설정하는 속성(어떻게 묶어서 줄바꿈할지)

nowrap이 기본값(한줄로 모든 아이템을 표시하겠다 - 화면을 줄이면 아이템면적이 줄어들더라도 결국엔 한줄로 보여짐)

wrap(브라우저 크기에 따라 줄바꿈을 하겠다 뷰포트 크기에 따라 아이템들이 여러줄로 보여지게 됨)

wrap-reverse(아래부터 쌓인다  내려가는 아이템이 첫순서부터 내려감)

3종류가 있다

- `justify-content` - 주 축(main-axis)의 정렬  방법 설정           --------**가장중요함(시험유력)**

주축의 아이템들이 어떻게 정렬될지를 설정함(6종류)

flex-start

flex-end

center(아이템들을 가운데정렬- 주축방향은 주의,  메인축을 기준으로 함)

space-between(아이템들중에 가장첫번째 마지막을 양끝에 두고 나머지 아이템들의 사이 간격이 일정하게 정렬, 양끝에 남은 간격은 제외)

![image-20220208104533212](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220208104533212.png)

space-around(아이템들의 여백을 균등한 여백으로 만들어서 정렬)

![image-20220208104552089](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220208104552089.png)

space-evenly(**모든** 여백을 균등한 여백으로 만들어서 정렬)

![image-20220208104624304](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220208104624304.png)

- `align-content` - 교차 축(cross-axis)의 정렬 방법 설정 (**2줄 이상**)

flexwrap이 nowrap이면 의미가 없음(한줄이기 때문에)

stretch(교차축을 꽉채우기 위해 아이템을 늘린다) - 기본값

flex-start

flex-end

center(교차축을 기준으로하는것이 차이점)  ------ 수직으로 컨테이너 내에서 가운데정렬(가장 많이 사용함-세로정렬)

space-between

space-around

- `align-items` - 교차 축(cross-axis)의 정렬 방법 설정 (**1줄**)

nowrap일땐 이거 써줘야함

속성값은 위에 content와 같은데   baseline이라는 것 하나 추가됨

baseline(아이템들 안에 글자 크기가 각각 다를때 문자 끝선에 맞춰서 정렬함) ----------- **시험나옴**

![image-20220208105851944](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220208105851944.png)





<Flex Item을 위한 속성들>

- order - Item의 순서를 설정

각 아이템의 우선순위를 결정해준다

기본값이 0이다(**1이든 5든 다른곳에 적용안되어있으면 맨끝으로!! 헷갈릴수있다 주의**)

음수 가능

클수록 flex-end에 가까워진다

- flex - flex-grow , flex-shrink , flex-basis 에 대한 단축 속성!(밑에 3개를 하나로 줄여쓰는것이다) 순서는 이대로

flex를 쓰면 flex-grow는 생략이 불가하다, 나머지2개는 생략가능(생략시 디폴트값으로)

flex-grow의 기본값은 1

flex-shrink의 기본값은 1

flex-basis의 기본값은 auto(**하지만 flex로 줄여쓸 때 flex-basis를 생략하게 되면 auto가 아닌 0으로 적용된다**)

- flex-grow - Item의 너비 증가(grow) 비율 설정

뷰포트를 점점 늘릴때 증가비율 설정(아마도 시험..?)

nowrap이 아니면 의미가 없다(wrap일때는 아이템 너비가 안바뀌고 줄이바뀌기 때문)

![image-20220208111759756](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220208111759756.png)

![image-20220208111814088](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220208111814088.png)

![image-20220208111838580](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220208111838580.png)



- flex-shrink - Item의 너비 감소(shrink) 비율 설정

뷰포트를 줄일 때 감소비율 설정,  기본적인 수학이 조금 들어가서 계산이 까다롭다(**시험안나옴**)

줄어든 거리를 비율만큼 나눠서 줄인다(각 아이템 크기가 같을때)

줄어든 거리를 원래너비에 비율을 곱한값을 비율로 보아서 줄인다

- flex-basis - Item의 기본 너비 설정

아이템의 기본너비 설정

width, height를 줄 수 없는 것들도 flex-basis를 이용하면 줄수있다

* align-self

교차축 기준으로 item을 정렬하는 방법을 설정(각각 아이템에 적용)

align-items(컨테이너 내의 모든아이템)와 같이 있다면 개별 아이템이 우선순위가 더 높다

기본값은 auto

align-items의 속성 그대로 다 가짐(stretch, ....)   



----

## Bootstrap

CDN은 하나의 기술(부트스트랩이 CDN을 이용하고 있는것)

js코드는 바디 닫는태그 바로 위에 적어주는것이 맞음(중간에 있으면 로딩시간이 길어짐)

css는 헤드안에 



html 기본 루트크기는 16px!!

1rem은 16px

부트스트랩은 기초알고 문서보면서 하는것!



반응형 웹디자인에서 가장 잘 쓰이는 것이 **부트스트랩 그리드 시스템**

**그리드시스템에서 문제가 많이나온다**

**container, rows, column**(가장 기본적인 레이아웃)으로 컨텐츠를 배치하고 정렬

row는 column을 감싸주는역할? 그리고 column은 안에 들어가는 아이템?

column은 아무것도 적어주지 않으면 블럭처럼 한줄을 차지함

container는 그냥 container와 container-fluid, container-브레이킹포인트 로 나누어진다(클래스이름)

그냥 container적으면 안에있는 아이템들이 반응형이 된다

container-fluid는 width를 100%로 지정해준다

container-브레이킹포인트 하면   브레이킹포인트에 뷰포터가 도달할 때마다 width가 100%가됨



**반드시 기억해야할 것!**

col-A-B 의 형태

column은 12개     (box개수를 12로 나눈것이 B에 들어가주며)

그리드 브레이킹포인트는 6개(xs,  sm,  md,  lg,  xl,   xxl)    A자리에 들어감         **시험나옴!!**

