HTML

링크가 연결된

가장 좋은 예시 : 위키백과

웹 페이지 작성, 구조화하는 언어!!

태그로 모든것을 표현



CSS

스타일 지정하기 위한 언어

선택자가 가장 중요한 개념(HTML의 문서를 바꾸기 위해 지정해주는 역할이기 때문)

Box Model - 가장 중요한 개념

모든것을 네모로 바라보아야한다(컨텐트-패딩-보더-마진)

박스모델 - 인라인 /// 블록

블록 - 아래로 쌓인다 /// 인라인 - 우측으로 하나씩 쌓여나간다

normal flow는 좌측 상단으로 가려는 것!!



HTML & CSS

Can i use? - 에서 어떤 속성을 쓸 수 있는지 확인가능

마크다운 - 마크업에 속함(마크다운 자체가 html로 만들기 위한 언어)



HTML의 헤드에는 보조적인 내용(문서제목, 인코딩 등)

바디 - 실제 본문 내용

DOM트리 - 중요!!!

---브라우저에서 어떻게 표현할지 (화면에 어떻게 그려나갈지에 대한 구조)

내용이 없는 태그들(단순 암기가 아니라 생각해보면 알 수 있다!)

Global Attribute  --- class를 작성해서 진행하는게 일반적!!(스타일을 각 태그에 적용)/// 

id class, style 많이 사용

header , footer 등은 결국 div라고 바꾸어도 똑같지만 코드를 볼때 훨씬 의미를 가지기 때문에 시맨틱 태그임

탭을 눌렀을 때 시각장애인을 위한 배려가 숨겨져있다.. 섬세함

인스타에서도 사진을 볼 수 없을 때 사진을 설명해주는 글로 설명되어있음



텍스트요소

bold / strong  강조  하지만 strong은 의미를 가진다

i / em  기울임체   em은 의미를 가진다



form 은 중요함!!!

검색창 등 모든것은 form으로 구성됨

input의 네임이 어떻게 동작하는지, 



label(checkbox, radio 버튼)

label의 for와 input의 id 가 같아야 작동함 (보통 input의 name도 같게함)

label을 해주면 좀더 체크할 수 있는 영역이 넓어진다



autofocus라는 코드 1개차이로 자동으로 커서가 가는지 안가는지 차이가 발생

---이러한 것은 디테일의 차이

----

CSS

선택자가 있어야 HTML에서 선택해서 변경할 수 있다.

외부 참조를 가장 많이사용(CSS파일을 따로 만들어서 거기서 참조해온다)

공통된 스타일이 있을 때 무엇을 우선순위로..?---> 우선순위

id  > class > element(tag)

만약 클래스가 같이 지정?  -  css 선언순서(나중에 선언한걸로!!!)



* 상속(어느영역안에서는 다 공통으로 적용)

시각적인효과들은 모두다 상속이 된다

박스모델 포지션 은 상속x (내가 위치하고싶은것   margin 등)

암기보다는 생각해보면됨!!



em / rem

em은 부모 요소에 의해 지정됨



viewport - 상대적크기



* 결합자

자손, 자식까지만 사용해도 거의 다 표현가능



* CSS Box Model

콘텐트 - 보더 - 패딩 - 마진



디스플레이

margin-right:auto;

margin-left:auto;

좌우를 묶는것이 편하다..?



box sizing

컨텐츠 영역인지 보더인지 그런 영역 중요함

![image-20220204111926265](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220204111926265.png)

보더박스로 초기화..?하는것이 편할수도

디폴트는 컨텐트 박스!!



Display

inline과 block 차이는 중요!!

block ---->>> 너비를 가질 수 없다면 자동으로 부여되는 margin!!! (남은공간을 마진으로 채워버림)

마진을 줄 때는 남은 영역을 자동으로 어딘가에 붙는걸 지정해줄 수 있음(블록이 정렬된 것처럼 보이게한다)

![image-20220204112414818](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220204112414818.png)



inline - 기본 너비는 컨텐츠 영역만큼!(내영역만)

너비, 높이, 마진, 탑바텀 지정불가

블록은 한줄다먹는다!



display none   vs    display hidden

아예 존재자체를 지우기 vs 눈가리기



* CSS Position

기본적으로는 normal flow

.relative - 흐름은 유지하되 위치만 변화(실제 원래 영역은 먹고있는것)

.absolute - 이미 흐름에서는 벗어남, 부모/조상 요소가 기준이 됨(겹침이 가능해진다) - 2차원이라고 생각하면됨

.fixed - 부모요소와 관계x viewport 기준! - 얘도 2차원



.개발자도구

지금은 elements에 있는 내용 위주로 활용

chrome dev tools 사이트에서!!

컨트롤 시프트 아이 --. 단축키

또는 우클릭해서 검사

마크업 순서도 바꿔볼수있음 개발자도구에서

computed는 결과를 볼 수 있는곳

.cls 눌러보면 알수있다

cls 왼쪽에 hov누르면 미리 볼 수 있다







absolute 는 이미 밖을 나가서 그 영역에선 나감 

relaive는 그 자리는 차지되어있음(안보이지만 차있다)

비어있는 자리에 그대로 올라가기 때문에 어떻게 배치되어야하는지 그런거 생각해보면됨



absolute는 큰박스를 기준으로 배치시키고 싶으면 relative 줘야함 안주면 난리난다





mdn css font  라고 검색하면됨

font family는 지정안되어있을때 기본값?

점선, 등 테두리도 검색

margin: 0 auto 해주면 가운데정렬

백그라운드는 패딩까지만 들어감(마진해주는거랑 패딩은 배경에서 차이점이 생길것)

width 100%하면 전체 꽉차게됨

이미지는 인라인이지만 너비나높이 지정가능한 요소임(대체요소  mdn검색해보면 나옴)

text-align: center; 이건 텍스트 가운데정렬

만들어야하는 것과 조금씩 다를때 어떻게해야할지 모르면 그럴때 구글링습관화

mdn css 키워드를 중심으로 찾아야함

line-height: ~~px 해주면 블럭안에서 글자 위에 길이 설정가능



인라인(알파벳때문에 컨텐츠 위아래로 약간의 공간이생김)

인라인을 블록으로 바꿔서 하든지 마이너스 마진..?



글자를 안에ㅔ서 -> text-align

박스자체 - 마진오토, 

패딩 - (글자 끝에 오른쪽공간 생긴다)



스타일의 기본: 마크업 후에 선택자로 잡아서 스타일을 지정해서 쓰는것

어떤 글자를 강조하고 싶으면 span같은거 사이에 글자넣어서  스타일 지정해주면됨 span style="color:">~~~</span>



text-decoration: none;  하면 밑줄같은거 없어짐

border-radius: ~~~ 하면 네모가 원이됨





마이너스 마진하면 끌어올려짐



transform: translate(-50%, -50%)   중앙에 위치



학습가이드라인 자료 참고 



