# Django : Template, View, Routing



## web framework 

## Django

파이썬 웹프레임워크

앱 작성에 집중할 수 있다



클라이언트(웹브라우저 : 크롬)가 서버로 요청    Django가 서버를 구축한다

서버가 클라이언트에 응답





* 정적 웹페이지

서버는 추가적인 처리과정 없이 응답 

모든 상황에서 모든 사용자에게 동일한 정보를 표시한다는 점이 가장 큰 특징

일반적으로 html, css, js 로 작성됨



* 동적 웹페이지

웹 페이지에 대한 요청을 받은 경우 서버는 추가적인 처리과정 이후 응답

방문자와 상호작용, 페이지 내용은 그때그때 다름

서버사이드 프로그래밍 언어(python, java, c++ ..)가 사용, 파일을 처리하고 데이터베이스와의 상호작용

유저가 요청하면 장고가 처리해서 html을 보여준다



* Framework

클래스와 라이브러리 모임/  재사용할 수 있는 수많은 코드를 프레임워크로 통합, 하나의 틀, 환경을 제공하겠다는 의미



* web framework

웹 페이지를 개발하는 과정에서 겪는 어려움을 줄이는 것이 주 목적

데이터베이스 연동, 템플릿 형태 표준, 세션 관리, 코드 재사용 등의 기능

결국 장고를 개발할 때 내부적으로 파이썬 코드 사용



* Django 사용해야하는 이유

검증된 python 언어 기반 웹프레임워크

대규모 서비스에도 안정적



* Framework Architecture

MVC 디자인 패턴(모델 - 뷰 - 컨트롤러)   장고뿐 아니라 여러가지 웹프레임워크가 사용

시각적 요소, 이면에서 실행되는 부분을 서로 영향없이 쉽게 고칠 수 있는 애플리케이션 가능

Django는 **MTV Pattern**이라고 한다(장고에서는 view는 template,  controller는 view로 부른다)

model - 응용프로그램의 데이터구조를 정의하고 데이터베이스 기록을 관리(추가, 수정, 삭제)   **DB**

template - 파일의 구조나 레이아웃 정의 , 실제 내용을 보여주는데 사용됨  **HTML(웹페이지)**

view - http 요청을 수신, http 응답을 반환 , model을 통해 요청을 충족시키는데 필요한 데이터에 접근  template에게 응답의 서식 설정을 맡김 // **view가 어떻게보면 가장 중요한 역할**         **조작, 가공**

![image-20220302092308322](Django%20%20Template,%20View,%20Routing.assets/image-20220302092308322.png)

모델을 받아서 VIEW에서 처리하고 템플릿에 넣어서 보낸다

1. http 요청
2. urls
3. view
4. http 응답/ model, template 가져오기는 선택적인 부분

<git bash에서>

python -m venv venv   가상환경 만들기

source venv/Scripts/activate   가상환경 활성화  (venv)라고 뜨면 활성화된것

pip list라고 해봤을 때 2개가 있으면 가상환경 설정된것



<vscode에서>

ctrl shift p      python interpreter 별표로 추천이뜬다

가상환경을 활성화하고 vscode에서 pip list치면 똑같이 확인가능

django설치하고 pip list 해보면 다시한번 확인할 수 있다



프로젝트이름에는 python이나 django에서 사용중인 키워드(django, text, class 등) 피하고 '_' 도 사용할 수 없다





init.py는 건들일 없음

asgi.py는 터치하지 않는다

settings.py는 애플리케이션의 모든 설정을 포함(여기서 거의 다 관리)

urls.py는 사이트의 url과 적절한 views의 연결을 지정

wsgi.py도 일단 쓰지않을것

manage.py는 django프로젝트와 다양한 방법으로 상호작용하는 커맨드라인 유틸리티(이것을 통해 command를 동작시킴   ex > runserver ...)

![image-20220302100821670](Django%20%20Template,%20View,%20Routing.assets/image-20220302100821670.png)

이 2개만 할 것

명령어는 일종의 규칙성이 있다

서버를 끄는 방법은 ctrl c 를 눌러주면 됨

application명은 복수형으로 하는것을 권장



application 구조

앱을 여러개 만들어야하는지는 의문 , 

![image-20220302101526738](Django%20%20Template,%20View,%20Routing.assets/image-20220302101526738.png)

admin.py - 관리자용 페이지를 관리

apps.py - 앱의 정보가 작성된곳 (수정할일 없음)

models.py - 앱에서 사용하는 model을 정의하는 곳(중요)

tests.py - 프로젝트의 테스트 코드를 작성하는곳(수업에서 사용할일 없음)

views.py - view함수들이 정의되는곳





* project

application들의 집합

여러 앱을 가질 수 있다

* application

앱은 실제 요청을 처리하고 페이지를 보여주고 하는 등의 역할

articles라고 한 이유는 게시판을 만들것이기 때문

프로젝트에서 앱을 사용하기 위해서는 반드시 installed_apps 리스트에 추가해야함



**앱은 생성후 등록**

INSTALLED_APPS에 먼저 작성하고 생성하려면 앱이 생성되지 않음



![image-20220302102537294](Django%20%20Template,%20View,%20Routing.assets/image-20220302102537294.png)

앱 등록시 순서를 지키지 않아도 문제는 없지만 지키는 것을 권장



![image-20220302102651952](Django%20%20Template,%20View,%20Routing.assets/image-20220302102651952.png)

이 순서는 반드시 기억해야한다





* 요청과 응답

admin/은 url주소의 일부

django에는 admin이 미리 구현이 되어있다

path함수가 admin이라는 주소가 포함되어 있어서 호출됨

크롬에서 url치고 엔터치는것은 서버에 요청, 그리고나서 응답을 받는 과정이 숨어있다



render 하나의 html문서로 만들어주는 것

render(request, A, B)   A는 HTML파일  B는 view와 템플릿이 데이터를 주고받는 창고



trailing comma - 장고에서는 뒤에 콤마를 붙이고 마치는것을 권장(생산성을 높이기위함)



view함수가 무조건 받아야하는 첫번째 필수인자 - request

template은 장고가 자동으로 만들어주지 않음 -> 앱에서 만들어줘야함

articles(앱폴더)안에 templates라는 파일을 만들고(**이것은 약속**) 그밑에 index.html이라고 만들기 (원래는 앱이름/templates/앱이름/html 이런형태가 장고 가이드라인임)

안될경우에는 서버 껐다켜보면됨



**프로젝트만들라하면 manage.py가 있는 같은 위치상에 만들어야함!!**

프로젝트파일과 같은 이름의 앱이 프로젝트 앱!

127.0.0.1 은 IP(내컴퓨터 주소) 8000은 port  

여기서는 내 컴퓨터가 서버(나만볼수있음)이지만 구글이나 ms, aws 등에 돈을 지불하면 배포할 수 있다

상태코드 200은 정상, 404는 에러

----

settings에서 language_code나 time_zone 을 바꿀수있음

모르는거있을때 django ~~~(키워드) 구글에서 검색후 공식문서로 타고오는것을 추천!!

i18n internalization

l10n localization

tz  timezone  이거 3개는 그냥 true로 두면됨



---

### template

django template

* 데이터 표현을 제어하는 도구이자 표현에 관련된 로직
* 사용하는 빌트인 시스템 - django template language(DTL)



DTL 

조건, 반복, 변수 치환, 필터 등의 기능제공

단순히 파이썬이 HTML에 포함된 것이 아니며 프로그래밍 로직이 아니라 프레젠테이션을 표현하기 위한것

if, for 등을 사용할 수 있지만 파이썬 코드로 실행되는것아니다



**URL -> VIEW -> TEMPLATE 순서로 코드 작성할것!** (데이터의 흐름)



1. varialble(변수)

{{ variable }} 변수와 괄호사이 공백 하나해주기

변수명은 영어, 숫자, 밑줄의 조합으로 구성(밑줄로 시작은 불가), 공백이나 구두점 문자 사용불가

dot(.)를 사용하여 변수 속성에 접근가능

render의 세번째 인자로 {key:value}와 같이 딕셔너리 형태로 넘김, key에 대당하는 문자열이 템플릿에서 사용가능한 변수명

코드변경사항은 자동으로 재시작해줌(서버 껐다 켤필요없음 ctrl c 해줄필요없다는뜻)

![image-20220302143554773](Django%20%20Template,%20View,%20Routing.assets/image-20220302143554773.png)

따로 context라는 것으로 뺄 수 있다

그리고 key value값을 똑같이 맞춘다(왼쪽의 key이름을 사용하는것이다 - 오른쪽 값에 접근해야하기 때문)

인덱스 접근도 가능



2. filters

{{ variable|filter }}

표시할 변수를 수정할 때 사용

ex: name|lower -> name변수를 모두 소문자로



3. tags

{% tag %}

출력 텍스트 만들거나 반복, 논리를 수행하여 제어흐름을 만드는 등 변수보다 복잡한 일 수행

일부 태그는 시작과 종료태그 필요

ex:     {% if %}{% endif %}

24개의 빌트인 템플릿 tags 제공



템플릿에서 연산을 하려고하면 안된다. 조작하고 연산하는 등의 역할은 view에서 다 해야한다



4. comments(주석)

{# 이것은 한 줄 주석입니다. #} 이렇게하거나

ctrl + / 해주면 됨

html 주석도 사용가능



forloop.counter - 순회 번호를 붙여주는 반복문



**built-in template tags and filters - > 공식문서에서 무조건 참조해야함!!**

함수호출시 () 없는것이 파이썬 구조와 다른점!!!



### 템플릿 상속

코드의 재사용성에 초점

사이트의 모든 공통 요소를 포함, 하위템플릿이 재정의할 수 있는 블록을 정의하는 기본 스켈레톤 템플릿을 만들 수 있다

부트스트랩 cdn을 적용할 수 있다

{% extends ' ' %}     자식 템플릿이 부모템플릿을 확장한다는 것을 알림

반드시 최상단에 작성되어야함

{% block conten %} {% endblock %} 하위템플릿이 채울 수 있는 공간

재지정할 수 있는 블록 정의



python object oriented filesystem path 구글링하면 객체지향 파일시스템 경로

BASE_DIR은 시작점을 최상단 폴더로 잡아준것

0.django~~/templates   이렇게 해주면 templates가 앱안에 없어도 읽을 수 있어진다

![image-20220302154409335](Django%20%20Template,%20View,%20Routing.assets/image-20220302154409335.png)



block뒤에는 이름붙일 수 있다(선택사항)

block태그 이름맞춰서 적어줘야 작동한다



nav 바만 수정하고 싶다 등 _--> include로 활용

템플릿안에 따로 html폴더 만들고 안에 

![image-20220302155544482](Django%20%20Template,%20View,%20Routing.assets/image-20220302155544482.png)

include해주면 됨 ( _ 사용된 이름은 include되는 템플릿이라는 뜻이라고 보통 인식함)

---> 깔끔하게 구조화할 수 있다

템플릿 내에 다른 템플릿을 가져오기 위함





django 철학!

1. 표현과 로직(view) 분리

템플릿은 표현을 제어, 표현에 관련된 로직일뿐, 기본 목표를 넘어서는 일 없기

2. 중복 배제

상속사용!!

보통 header, footer, navbar등을 한곳에 저장하기 쉽게 하여 중복 코드를 없앤다