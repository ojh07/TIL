명령 - 조건과 반복

함수를 사용하는 이유

Decomposition - 기능을 분해하고 재사용 가능하게 만들기 위해

Abstraction - 복잡한 내용을 몰라도 사용할수 있도록, 

-> 재사용성과 가독성, 생산성



* 내장 함수

* 사용자 정의 함수



함수가 동작하는 원리가 가장 중요!!



### 함수의 정의

함수(Function)

특정한 기능을 하는 코드 조각의 묶음

코드를 매번 다시 작성하지 않고 필요시 간단히 사용



함수, 모듈, 클래스 바로 다음에 ''', """ 이것은 각각에 대한 설명을 해줌(docstring)

사용할일 많지 않음



사용자 함수

구현된 함수가 없는 경우 사용자가 직접 함수 작성 가능    def는 define

def function_name(값):

​	code block

​	retrun 값

![image-20220119092053749](python%ED%95%A8%EC%88%98.assets/image-20220119092053749.png)

1. 입력 , 2. 결과값, 3. 문서화



#### 선언과 호출

함수의 선언은 def키워드 활용

들여쓰기로 코드블록 작성

docstring은 함수설명



함수는 함수명()로 호출

parameter있는 경우, 함수명(값1, 값2, ...)로 호출



함수 정의시 순서 -> 함수의 이름, input이름, 로직, 결과값



선언은 로직

호출은 결과를 받을뿐



* 함수의 결과값

void function 

명시적인 return값이 없는 경우, None을 반환하고 종료

value returning function

return을 만나면 값 반환후 함수 종료

print와 return은 완전 다르다!! print는 return값이 없다(단순히 값을 보기 위한 용도임!)

주피터노트북은 print없이 찍어도 결과나옴(옆에 out붙어있음 return이기 때문)

마지막으로 작성된 코드의 리턴 값을 보여주기 때문에 같은 동작을 하는걸로 착각할 수 있음



return은 함수 안에서만 사용되는 키워드

print는 출력을 위해 사용되는 함수



return문은 반환 값으로 튜플이 반환됨(**return 뒤에 콤마로 연결 -> 2개의 값으로 보이겠지만 튜플 타입으로 묶어서 하나만 반환된 것**)

return X -> None

return O -> 하나를 반환



#### 함수의 입력

이름 - parameter(함수 정의할 때 함수 내부에서 사용되는 식별자) 매개변수 인수        정의할때

값 - argument(함수를 호출할 때 파라미터를 통해 전달되는 값)  전달인자 인자        호출할때

* 필수 argument - 반드시 전달되어야 하는 argument
* 선택 argument - 값을 전달하지 않아도 되는 경우는 기본값이 전달

![image-20220119102003018](python%ED%95%A8%EC%88%98.assets/image-20220119102003018.png)

![image-20220119133058212](python%ED%95%A8%EC%88%98.assets/image-20220119133058212.png)

기본은 무조건 앞에 나와야함 , **복잡한것은 뒤로**!!



positional arguments

기본적으로 함수 호출시 argument는 위치에 따라 함수 내에 전달됨

keyword arguments

직접 변수의 이름으로 특정 arguments를 전달

![image-20220119102737255](python%ED%95%A8%EC%88%98.assets/image-20220119102737255.png)

위치 지정 후에 키워드는 또 가능함

키워드 지정후에 위치값 넣으면 에러

-> 여기는 호출시



디폴트 값(정의할 때)

기본값 지정해서 함수호출시 argument값 설정하지 않도록(선택)



몇개의 arguments를 받을지 모르는 함수를정의할때 유용

---------패킹/언패킹 연산자(*) 사용     *args이 권장됨(이름을 복수형으로 짓는것이 좋음)

이때는 튜플로 묶임!



키와 value의 조합으로 묶고싶을때 

---------딕셔너리로 묶고싶을땐 ** 2개 사용하면됨  이름은 (**kwargs  권장됨)





함수  -  input  - 호출시에는 위치나 키워드로

​                      - 어떤 것은 선택

​         -   output  반드시 하나의 객체 반환( 0은 none 여러개는 튜플로 묶임) 

![image-20220119104908685](python%ED%95%A8%EC%88%98.assets/image-20220119104908685.png)



#### 함수의 범위    local과 global만 잘 알면됨!!

코드 내부 local scope(함수 내부에서만 참조가능) 함수 바깥으로 가면 다시 정의해야함 

그 외 공간 global scope(코드 어디에서든 참조할 수 있는 공간)

global variable   global에 정의된 변수

local variable  local scope에 정의된 변수

함수는 가장 기본 : local scope 를 가짐



#### 이름검색규칙 

파이썬에서 사용되는 이름들은 이름공간에 저장되어있음

이름공간에 있는 코드를 넣어두고 여기 있는지 찾아보고 우리에게 알려줌

안에서 바깥으로 가면서 찾아나감

함수안에 함수도 지정가능

이름찾는순서가 LocalEnclosed(함수안에 함수가 있다면 그 바깥 함수)GlobalBuiltin 순서!

![image-20220119134051672](python%ED%95%A8%EC%88%98.assets/image-20220119134051672.png)



![image-20220119134632652](python%ED%95%A8%EC%88%98.assets/image-20220119134632652.png)

![image-20220119134847168](python%ED%95%A8%EC%88%98.assets/image-20220119134847168.png)

global a 라고 해줬기 때문에 a를 3으로 바꿀 수 있어서 밑에 print(a)는 3으로 출력됨

global a -> 여기서 global a 를 사용하겠다는 뜻  -> a에 다시 값 할당하면 global a 값이 바뀜

global a 는 참조하라고할 뿐 a에 값이 할당되어있는 것은 아님(nonlocal 과 같이 쓰일때 헷갈리지않게)

global변수를 쓸 때는 상단에 써야함!



nonlocal - 글로벌까지는 아니고 근처에 있는 변수 변경

global과는 달리 이미 존재하는 이름과의 연결만 가능함



기본적으로 함수에서 선언된 변수는 local scope에 생성, 함수 종료 시 사라짐

해당 scope에 변수가 없는 경우 legb rule에 의해 이름을 검색(변수 수정할 수 없음)

----> 상위 scope에 있는 변수 수정하고 싶으면 global, nonlocal 키워드 활용가능

return해서 받아서 써야함



함수는 블랙박스

이름이 없다면 이름을 찾는 과정 legb 순서

찾아서 쓸 수 있는데 값은 바꿀 수 없다

변경할 수 있는 2가지 키워드 - globlal, nonlocal   

2개 쓰는순간 블랙박스 원칙을 깨버림

공간이 하나의 scope로 local scope로 운영되고 있는 것.

![image-20220119140244006](python%ED%95%A8%EC%88%98.assets/image-20220119140244006.png)

호출은 정의에 맞게!





### 함수의 문서화(Doc-String)

docstring - 함수나 클래스의 설명



좋은 함수와 파라미터 이름짓는법 - 상수(변하지 않을 값)이름은 영문 전제를 대문자

클래스 및 예외 이름은 각단어의 첫글자만 영문 대문자

이외 나머지는 소문자 또는 밑줄로 구분한 소문자 사용 -> 함수

* 스스로 설명 - 함수 이름만으로 어떤 역할인지 파악가능하도록
* 어떤 기능을 수행하는지, 결과 값으로 무엇을 반환하는지
* 약어 사용 지양

StudentUser - pascal case / student_user - snake case / studentUser - camel case

클래스이름 - 파스칼 케이스



#### 함수 응용(map, filter, zip, lambda)   - 4개중 가장 많이 사용되는 것 map

내장함수

* map(function, iterable)   - 형태 외우면 됨 알고리즘시 많이 사용됨

function에는 각요소에 적용하고싶은 함수이름을 넣음

순회가능한 데이터구조의 모든 요소에 함수적용하고, 그 결과를 map object로 반환

![image-20220119141527182](python%ED%95%A8%EC%88%98.assets/image-20220119141527182.png)

![image-20220119141551231](python%ED%95%A8%EC%88%98.assets/image-20220119141551231.png)

map(함수이름, list)

**map(int, input().split())**  < --------------------------------------------------------이것 외우면됨



-> 묶음(시퀀스)

-> 리스트로 반환하지 않고 object로 반환하는 이유는 리스트의 길이가 길때를 대비하여..

list 형변환을 좀 더편리하게..?

'2  3' --> split 해주면   '2', '3' 으로 쪼개줌



* filter(function, iterable)

순회가능한 데이터 구조(iterable)의 모든 요소에 함수적용하고 그 결과가 true인 것들을 filter object로 반환

![image-20220119142500957](python%ED%95%A8%EC%88%98.assets/image-20220119142500957.png)



* zip(*literables)

복수의 iterable을 모아 **튜플**을 원소로 하는 zip object를 반환

묶어주는 것 

literable한 것들이 많이 들어갈 수 있다

``` python
lst = [[1,2,3],[4,5,6],[7,8,9]] 
for i in lst:
    print(i)
print('\n-----\n')
lst2 = zip(*lst) # transpose / 전치
for i in lst2:
    print(i)
print('\n-----\n')
lst3 = list(zip(*lst))[::-1] # 90도 회전 시계 반대 방향
for i in lst3:
    print(i)
print('\n-----\n')
lst4 = zip(*lst[::-1]) # 90도 회전 시계방향
for i in lst4:
    print(i)
```



![image-20220119165311860](python%ED%95%A8%EC%88%98.assets/image-20220119165311860.png)

![image-20220119165457175](python%ED%95%A8%EC%88%98.assets/image-20220119165457175.png)

짝이 지어지지 않는다면 더 긴쪽을 잘라냄

짝을 지어야하는 변수가 많아질 때 매우 유용함!!



*  lambda 함수(익명함수)           lambda[parameter] : 표현식

선택적으로.. 굳이안써도됨

쓴다면.... 코드의 라인이 줄어들고 컴퓨터 메모리를 적게 차지함, def사용할 수 없는 곳에서도 사용o

표현식을 계산한 결과값을 반환하는 함수

return문을 가질 수는 없지만 return을 하긴함

간편 조건문 외 조건문이나 반복문을 가질 수 없음

![image-20220119170645443](python%ED%95%A8%EC%88%98.assets/image-20220119170645443.png)

(lambda 매개변수 : 결과)(값)   -> 이렇게 호출하면됨

보통은 람다식 자체가 매개변수 자리나 함수자리에 들어감!

또는 func = lambda식

func() 으로 호출하면됨

![image-20220119171046557](python%ED%95%A8%EC%88%98.assets/image-20220119171046557.png)

이렇게 그냥 함수로 풀어써도되지만 이해는 할 수 있어야하기 때문에 알고있어야함.



*filter와 lambda를 함께*

filter(function, iterable) **function자리에 함수 정의할 필요없이 lambda**를 넣어주면됨!( def~~ 대신 lambda 써주면됨)

![image-20220119171340832](python%ED%95%A8%EC%88%98.assets/image-20220119171340832.png)

----> 홀수 찾는 방법의 예시







![image-20220119143021110](python%ED%95%A8%EC%88%98.assets/image-20220119143021110.png)

![image-20220119143402237](python%ED%95%A8%EC%88%98.assets/image-20220119143402237.png)

천천히 읽어보면 됨

odd라는 함수 없을 때 lambda를 사용하면됨



* 재귀 함수   ----- 알고리즘시 다시 한번!

**자기 자신을 호출하는 함수,    언젠가 return을 하는 종료조건이 필요!**

무한한호출 x, 알고리즘 설계 및 구현에서 유용함

**1개 이상의 base case(종료되는 상황)가 존재, 수렴하도록 작성**

예시 : Factorial 

같은 문제를 다른 input을 통해서 해결

자기자신을 호출하고 마지막 base case를 만나서 return 계산이 완료되면서 위로올라가면서 

다시 계산



base case에 도달할 때까지 함수 호출

메모리 스택 넘치면 정지



반복문으로 표현가능! 알고리즘에서 재귀는 매우 중요한 개념!!!



#### 모듈

* 모듈과 패키지

모듈 - 특정 기능을 하는 코드를 파이썬 **파일(.py)**로작성한 것

패키지 - 여러 모듈의 집합



모듈과 패키지 불러오기

![image-20220119150515430](python%ED%95%A8%EC%88%98.assets/image-20220119150515430.png)

*은 패킹언패킹연산자를 제외하고는 '모든것'이라는 뜻을 가짐  (정규표현식)

import module 과 같은 뜻이지만 import module 은 module. 으로 해야한다는점이 차이점

모듈명.함수



* 파이썬 표준 라이브러리

파이썬에 기본적으로 설치된 모듈과 내장 함수

어떤 인풋을 받아서 어떤 아웃풋을 반환하는지를 보는 것이 중요!

파이썬 공식문서에서 확인가능

**파이썬 패키지관리자(pip)** - PypI에 저장된 외부 패키지들을 설치하도록 도와주는 패키지 관리 시스템(=프로그램)(예 : 주피터 노트북)

![image-20220119152024942](python%ED%95%A8%EC%88%98.assets/image-20220119152024942.png)

pip install package -> 최신버전을 설치해줌

pip install some package == 1.0.5  -------> 꼭 최신버전이 좋은것만은 아니기때문에..(내가 사용하는 버전을 명시)



삭제시에는 pip uninstall 패키지이름

설치된 패키지 정보 확인 - pip list

​            pip show package

설치목록 보는 것 - pip freeze

![image-20220120093821664](python%ED%95%A8%EC%88%98.assets/image-20220120093821664.png)

![image-20220119153017129](python%ED%95%A8%EC%88%98.assets/image-20220119153017129.png)

밑에거는 알아서 버전에맞춰서 설치해줌

설치하고 싶은 툴 공식홈페이지 들어가보면 방법도 다 있음

* 가상환경

![image-20220119154625549](python%ED%95%A8%EC%88%98.assets/image-20220119154625549.png)

![image-20220120101215680](python%ED%95%A8%EC%88%98.assets/image-20220120101215680.png)

![image-20220120101308195](python%ED%95%A8%EC%88%98.assets/image-20220120101308195.png)

보통은 python -m venv venv 라고 지음( 폴더명에 신경쓰지 않기 위해)

![image-20220119155128173](python%ED%95%A8%EC%88%98.assets/image-20220119155128173.png)

바로 내 컴퓨터로 적용 -> source 명령어

cmb bash 명령어 차이 있음

![image-20220120095147324](python%ED%95%A8%EC%88%98.assets/image-20220120095147324.png)

![image-20220120095235950](python%ED%95%A8%EC%88%98.assets/image-20220120095235950.png)

패키지 안에 패키지 가능

* 유용한 패키지와 모듈



* 사용자 모듈과 패키지





지금당장은 아니라도 나중에 필요한 내용들!