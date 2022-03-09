# Django Model



ORM은 SQL대신에 사용할 수 있는 것 

SQL을 파이썬으로 매핑해서 파이썬으로 DB를 조작할 수 있도록 한 것이 ORM이다(JAVA에도 존재)

Migrations - model을 조작할 때 model의 변경사항들(히스토리) 

Database API 를 이용해서 CRUD(Create Read Update Delete) 모든 프로그램의 기본적인 기능들

Admin Site - Django 관리자 기능



## Model

Django에서 사용할 데이터의 구조를 미리 잡아두는것이 model

데이터들의 필수적인 필드들과 동작들을 포함 /  필드 여러개가 모여 하나의 구조를 형성

Django는 model을 통해 **데이터에 접근하고 관리**할 수 있다



* Database

체계화된 데이터의 모임(어떠한 규칙을 가지는)

* 쿼리(Query)

데이터를 가져오기 위한 명령어(SQL로 작성)

데이터 수정, 삭제 등의 명령어도 포함

Query를 날린다 -> DB를 조작한다



* 스키마(Schema)

데이터베이스에서 어떤 구조로 작성이 되어있는가, 안에 들어있는 각각의 필드가 어떤 관계를 갖고 있는지 정의한 구조(DB의 설계도같은 느낌)

* 테이블(Table) - 표

열(column) - 필드 or 속성

행(row): 레코드(행 1줄을 의미) or 튜플        데이터를 추가하는 것은 행이 늘어나는것이다

각 행(레코드)의 고유값 - primary key(pk 기본키) 중복불가, 데이터베이스 관리 및 관계 설정시 주요하게 활용   일반적으로 id라는 이름으로 사용



<model 요약>

장고에서 사용하는 데이터를 **구조화**하고 **조작(CRUD)**하기 위한 도구



## ORM(Object Relational Mapping)

데이터베이스를 model객체로 접근하겠다는 것

OOP프로그래밍에서 RDBMS을 연동할 때, 데이터베이스와 객체 지향 프로그래밍 언어 간의 호환되지 않는 데이터를 변환하는 프로그래밍 기법

DB는 SQL(대부분), NOSQL(테이블이 자유로운것 - 채팅같이 빠르게 변화하는것들) 2개로 나뉜다

백엔드 직무를 위해서는 SQL을 따로 공부해야한다



장점 : SQL을 잘 알지못해도 DB조작이 가능

SQL의 절차적 접근이 아닌 객체 지향적 접근으로 인해 높은 생산성

단점 : SQL의 모든 기능을 다 사용하진 못하기 때문에 완전한 서비스 구현하기 어려운 경우 있다



현대 웹 프레임워크의 요점은 웹 개발 속도를 높이는 것!(생산성)



Django 코드 안에 sql코드를 직접 작성할 수도 있다(꼭 ORM 사용해야하는 것은 아님)



model은 앱별로 나눠서 적을 수있지만 굳이 안나눠도된다

charField(max_length 지정 필수!!!)

textfield도 같은것이지만 최대글자수 적어줄필요x

pk값은 알아서 id라는 이름으로 만들어줌(0부터 1씩 증가시키면서) 실제로 데이터는 1부터 들어간다고 보면됨

![image-20220308101841302](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220308101841302.png)

필드 옵션들은 우리가 따로 정의하지 않아도 기본값이 정의되어있음, 필요할 때 해당 옵션을 찾아서 조작해주면됨

null은 데이터베이스에 null이라는 값이 들어갈지 말지 선택하는것(파이썬에서의 none과 비슷)   기본적으로 모든 필드는 false로 기본값 설정(모든 필드는 기본적으로는 null값이 허용되지 않는 상태)

blank는 해당 필드를 빈 값으로 둬도 될지 선택하는것(DB랑은 크게 관계없음)



model조작(생성, 수정, 삭제) -> 마이그레이션 생성 -> 마이그레이션 반영(적용)



runserver 이후에 한번은 migrate 해줘야함



db.sqlite3 이파일이 db파일임(이파일 날아가면 데이터 다 날라가는것)

![image-20220308103802516](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220308103802516.png)



showmigrations 해서 x되어있는것은 이미 적용되었다는 뜻

admin, auth 이런것들은 앱이름

0001, 0002 이런것들은 migrations들



자동으로 날짜 시간이 저장 DateTimeField(auto_now_add=True)  최초 데이터가 생성될때 

auto_now_add는 어떤행이 생성될때 최초 1번 자동으로 저장!

auto_now는 수정할 때마다 자동으로 변경(갱신)

**이 2개는 정말 많이 사용!!!**

![image-20220308105231850](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220308105231850.png)

2번은 migrate안만들어짐    -> default라는 필드 옵션 적어줘야함

1번은 알아서 해줌





뷰 안쪽에 모델을 orm을 이용해서 코디해줘야함

ORM을 연습할 수 있는 공간?(DB와 소통할 수 있는 공간) -> python manage.py shell

파이썬 리스트에서 할 수 있는것 다 사용가능(슬라이싱, 인덱스 등)

![image-20220308111915406](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220308111915406.png)

![image-20220308112153811](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220308112153811.png)

![image-20220308112308556](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220308112308556.png)

데이터 저장 방법엔 이렇게 3개가 있다!

article은 내가 지금 쓰고 있는 인스턴스의 데이터를 바꾸고 있는것

Article은 클래스



create는 3가지 방법

read는 전체데이터 가져오는 방법           article = Article.objects.all() 



### Create

1. 인스턴스를 만들고 save하는 방법

article = Article()

article.title="~"

article.save()



2. 키워드 인자를 넘기는 방식

article = Article(title="~~", content="text")

article.save()

3. create() 이용하는 방법

Article.objects.create(title="~~", content="text")

save는 필요없다!



objects는 모델매니저

쿼리셋 - db로부터 건네받은 객체의 목록



### read(조회)

1. 모든데이터(all)

2. 한가지 데이터(get)

   ![image-20220308134103406](Django%20Model.assets/image-20220308134103406.png)

3. 여러개의 조건에 맞는 데이터(filter사용)

   ![image-20220308134051234](Django%20Model.assets/image-20220308134051234.png)

   filter안에 들어갈 수 있는 종류가 많다

   https://docs.djangoproject.com/en/3.2/ref/models/querysets/

![image-20220308133252535](Django%20Model.assets/image-20220308133252535.png)





get은 한개의 데이터만 가져옴

중복되는 내용있으면 에러남

id로 가져오면 가능(id말고 pk라고 적어줘도 가능하다!)



### update

![image-20220308140546546](Django%20Model.assets/image-20220308140546546.png)



### delete

![image-20220308140637387](Django%20Model.assets/image-20220308140637387.png)



관리자기능











![image-20220308161812086](Django%20Model.assets/image-20220308161812086.png)



![image-20220308162627998](Django%20Model.assets/image-20220308162627998.png)

앞에 title, content는 모델에 적어준 필드명

뒤에 title, content는 위에 입력된 데이터변수







최신글이 가장 위에 올라오려면 views에서 데이터 가져올 때 [::-1] 해주면됨  --> 가져온다음에 바꾸는것

처음부터 db에서 가져올 때 정렬도 가능 articles = Article.objects.order_by('pk') 해주면 오름차순으로 정렬

pk앞에 -1붙이면 내림차순





http method  (URL에 추가된 내용 보고싶지 않으면 POST)

GET - 기본값, 서버에 리소스를 요청할때만 사용  R    URL에 쿼리스트링으로 데이터를 보냄

POST - 리소스를 생성, 수정, 삭제할 때 사용   CUD     Body안쪽에 데이터를 한겹 숨겨서 보낸다



CSRF Token으로 url에서 수정하는거 방지가능

데이터 보내는쪽이랑 받는쪽이 암호를 주고받는데 암호가 token

csrf token은 post방식에 쓰인다

![image-20220308165025567](Django%20Model.assets/image-20220308165025567.png)

form으로 post방식 사용시에는 무조건 csrf token 같이 사용해줘야한다

![image-20220308165237899](Django%20Model.assets/image-20220308165237899.png)

view도 GET이라고 쓰여있다면 POST로 변경해줘야함



render는 템플릿을 랜더해서 결과로 돌려주는 역할



템플릿을 랜더하는 것이 아니라 새로운 url로 보내버리면 됨..?



redirect - 특정 url로 사용자를 보내버림

![image-20220308170213146](Django%20Model.assets/image-20220308170213146.png)

create로 보냈으니까 view의 create함수에서 수정  기존 render를 redirect로 바꾸고 

![image-20220308170221798](Django%20Model.assets/image-20220308170221798.png)