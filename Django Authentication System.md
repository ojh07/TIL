# Django Authentication System

![image-20220411173838349](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220411173838349.png)

1. django.contrib.auth - 인증 프레임워크의 핵심과 기본 모델 포함

2. django.contrib.contenttypes - 사용자가 생성한 모델과 권한 연결

인증(신원 확인)과 권한(권한 부여, 인증된 사용자가 수행할 수 있는 작업결정) 부여를 함께 제공



## 우선 두번째 앱을 생성

python manage.py startapp accounts

app이름을 accounts로 사용하는 것을 권장!!(앱 생성 후 등록하고 url설정)



## 쿠키와 세션

HTTP : 웹에서 이루어지는 모든 데이터 교환의 기초, 클라이언트 - 서버 프로토콜

특징 2가지

* 비연결지향 - 서버는 요청에 대한 응답을 보낸 후 연결 끊음

* 무상태 - 연결 끊는 순간 클라이언트와 서버간 통신이 끝나고 상태 정보 유지X 

  ​				클라이언트와 서버가 주고 받는 메시지들은 서로 완전히 독립적

### 쿠키

서버가 사용자의 웹 브라우저에 전송하는 작은 데이터 조각

서버를 통해 사용자의 컴퓨터에 설치되는 작은 기록 정보 파일

로컬에 key-value 데이터 형식으로 저장

동일한 서버에 재요청시 저장된 쿠키 함께 전송

사용자의 로그인 상태를 유지할 수 있음(상태가 없는 HTTP 프로토콜에서 상태정보 기억시켜줌)

사용 목적 : **세션관리**(로그인 정보, 장바구니 등이 대표적인 예시), 개인화, 트래킹



### 세션

사이트와 특정 브라우저 사이의 상태 유지

클라이언트가 서버에 접속 -> 서버는 특정 **session id**를 발급 -> 클라이언트는 발급받은 session id를 쿠키에 저장(다시 서버에 접속하면 요청과 쿠키를 서버에 전달, 쿠키는 요청때마다 서버에 함께 전송됨)

ID는 세션을 구별하기 위해 필요, 쿠키에는ID만 저장

쿠키의 수명 - Session cookies(세션종료시 삭제), Persistent cookies(지정된 기간 존재)

세션은 미들웨어를 통해 구현됨



### 미들웨어

HTTP 요청과 응답 처리 중간에서 작동하는 시스템

Django는 HTTP 요청이 들어오면 미들웨어를 거쳐 해당 URL에 등록되어있는 view로 연결해주고 응답도 미들웨어를 거침



## 로그인

로그인을위한 form 

AuthenticationForm(request를 첫번째 인자로)

login함수

login(request, user)



## 로그아웃

로그아웃은 session Delete하는 로직과 같음

logout(request)

요청에대한 session data를 DB에서 삭제하고 클라이언트의 쿠키에서도 sessionid가 삭제됨



## 로그인 사용자에 대한 접근 제한

* **is_authenticated**

user model 속성 중 하나

**request.user.is_authenticated**

인증되었는지 여부를 알려줌

권한과는 관련없고 활성화 상태, 유효한 세션과는 관련없음

if else 구문으로 로그인과 비로그인 구분

* **login_required** decorator

로그인 되어있으면 정상적으로 view함수실행

인증성공시 사용자가 redirect되어야 하는 경로는 **next라는 쿼리 문자열 매개 변수**에 저장

from **django.contrib.auth.decorators** import **login_required**

next 쿼리 스트링

![image-20220412214112709](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220412214112709.png)

**form에서 action값 비우면 현재 url로 요청 보내는것!!**

redirect요청은 POST방식 불가능해서 GET방식으로 요청됨

login_required는 GET method request를 처리할 수 있는 view함수에서만 사용해야함



![image-20220411173853402](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220411173853402.png)

## UserCreationForm(회원가입)

![image-20220412214736553](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220412214736553.png)

회원가입 후 자동으로 로그인 진행

유효성 검사 후 user = form.save()

​						auth_login(request, user)    추가해주면됨



## 회원탈퇴

SQLite나 admin페이지에서 유저가 삭제되었는지 확인

탈퇴 후 세션 데이터 지울 경우 -> **반드시 탈퇴 하고 로그아웃하는 순서로 처리해야함**



## UserChangeForm(회원정보 수정)

![image-20220412215124914](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220412215124914.png)

forms.py에서 

![image-20220412215213460](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220412215213460.png)

이런식으로 UserChangeForm을 상속받아서 접근 가능한 필드를 조정

수정 시에 필요한 필드만 선택해서 작성

그리고 views.py에서 

**from .forms import CustomUserChangeForm** 적어주고

![image-20220412215724142](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220412215724142.png)

![image-20220412215604412](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220412215604412.png)



## PasswordChangeForm(비밀번호변경)

![image-20220412215808970](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220412215808970.png)

### 암호 변경시 세션 무효화 방지

![image-20220412215834104](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220412215834104.png)

![image-20220412215843347](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220412215843347.png)