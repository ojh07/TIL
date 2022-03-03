# django 복습

1. variables
2. filters

chained는여러개 필터를 같이 사용할 수 있다는뜻

3. 태그

반복문, 조건문 등 문법사용하는곳?

일부는 시작, 종료태그 필요

4. 주석

잘 사용하지 않음



<실습>

variables -->   링크할 때 /~~/ 해야 가장 루트경로부터 시작해서 ~~ 라는 경로로 이동하는것

앞에 / 때면 지금 있는 위치에서 ~~ 붙여서 이동하라는 뜻!

태그같은 경우 for 나 if 치고 탭이나 엔터누르면 자동으로 편하게 형태 만들어줌

for는 굉장히 자주사용함!!



템플릿에서 굉장히 많은 반복이 일어남 -> 상속개념 등장

settings에서 

app_dirs --> 이 폴더 구조안에서 찾아

BASE_DIR은 프로젝트 루트임!!(settings 파일이 있는 부모파일의 부모파일이라서)

![image-20220303102446811](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220303102446811.png)

이 위치에서 templates 파일 찾아봐!!라는 뜻

반복될 부분을 base.html에 넣어주면됨

반복되지 않을부분을 block이라는 부분에 잡아두는것(상속받는 애들이 block안에다가 또다른 내용이 추가가능하다는 뜻)

block안에 내용 들여쓰기는 필수는 아니다!





include는 템플릿 내에 다른 템플릿 내용을 포함시키려고 하는것

다른 html코드를 가져와서 이 자리에 넣겠다

부트스트랩 cdn     nav바도 중복없이 그냥 base.html에 넣어버리면됨

따로 html파일 하나로 빼서 거기에 코드 넣고 base.html에는 include해주면됨





<HTML Form>

action 은 입력 데이터를 **어디로** 보낼지 적어주는것

method는 입력 데이터 전달 방식을 지정(GET, POST...)

GET은 어떤 데이터를 그냥 달라고 할때 

POST는 내가 글을 작성하거나 회원가입을 하거나 무언가 데이터를 저장하거나 사용할 때

의미는 차이가 있지만 기능은 둘다 가능하다



input요소는 type에 따라 동작 방식이 달라진다(사용자입력받는것)

속성 중에서 핵심 속성은 name

데이터를 서버로 넘길 때 그 데이터에 대한 이름을 지정해주는 것

key자리에 name , value자리에 사용자가 입력한 데이터가 들어가서 name으로 사용자가 입력한 데이터에 접근할 수있다는 뜻

get방식에서는 url형식으로 다 넘겨준다

~ip:port/dinner/?name=aiden & address = Seoul ...........

?부터 쿼리스트링이라고 한다           -> 이 방식은 보안에 좋지 않음

보안이 중요하지 않은 ex(검색키워드)는 get방식으로 많이 넘긴다

samsung으로 검색시 : https://www.google.com/search?q=samsung&oq=samsung



label요소는 input에 대한 설명을 나타냄

label을 input 요소와 연결해줘야한다

1. **input에 id 속성** 부여

2. label는 input의 id와 동일한 값의 **for 속성**이 필요

연결하면 좋은점 - label을 입력해서 input에 초점을 맞추거나 활성화시킬 수 있음

button, select, 등은 input의 type으로 들어가는 애들임



id는 요소 선택자



HTTP(Hyper Text Transfer Protocol)   어떠한 약속이다

HTTP request method의 종류(사용자의 요청이 뭘 하고자하는것인지 구분하기 위함)

GET, POST, PUT, DELETE.....

PUT은 서버로부터 어떤 정보를 수정

DELETE 서버에서 어떤 데이터를 삭제한다

지금은 **GET, POST**만 알면됨!!!

GET은 서버로 데이터 전송할 때 body가 아닌 쿼리스트링 파라미터를 통해 전송

POST는 URL에 담지않고 body라는 영역에 데이터를 한겹 숨겨서 전송



method는 적어주지않으면 기본적으로 GET방식으로 전송됨

ACTION은 어디로 보낼지, METHOD는 GET, POST이런 방식



views에 request.GET.get('message') ---> GET으로 요청받은것중 message를 가져와줘

![image-20220303124747280](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220303124747280.png)

view에서 print함수로 확인해볼 수 있음





URL

variable routing

url주소를 변수로 사용

url일부를 변수로 지정하여 view함수의 인자로 넘김

변수값에 따라 하나의 path에 다양한 페이지를 연결



url path converters

str이 기본값(아무것도 설정하지않으면 str이 기본값)

우선 str과 int만 이해하고 있자



문자열 -> view -> 템플릿



hello다음이 문자열이면 name이라는 변수에 담아서 hello라는 함수를 call해

views에서 name이라는 변수 넘겨받은거 함수에 담는다





app url mapping

앱별로 url패턴을 나누자!

각 앱에 urls.py를 작성!

앱 생성후 등록은 필수

앱 안에 template만들고 그 template아래 앱네임이랑 같은 폴더하나 만들기

그안에 html



사용자가 요청하면 무조건 프로젝트의 urls가 받음

pages/index

pages/와 일치하는게 있으면 pages/ 뒤의것은  include뒤에 곳으로 보내라





이런식으로하면 이제 throw같은거만 해주면 안되고 articles/throw 이렇게 해줘야함

![image-20220303141837478](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220303141837478.png)



naming url patterns

각각의 url에 이름을 붙이고 템플릿에서는 이름을 사용하자











![image-20220303164945180](django%20%EB%B3%B5%EC%8A%B5.assets/image-20220303164945180.png)

또다른예제!!