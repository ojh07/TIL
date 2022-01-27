# Python : 객체지향 프로그래밍



파이썬은 모든 것이 **객체**



![image-20220126090407244](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220126090407244.png)

![image-20220126090437875](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220126090437875.png)

어떠한 것 = 객체               상태와 동작이 같이 있는 어떠한 것

대상의 정보와 동작         S + V

(3+4j).rael  =>  복소수의 실수부분을 뜻함

[3, 2, 1].sort() => 리스트를 정렬



클래스와 인스턴스



* 객체지향 프로그래밍

파이썬은 모두 객체로 이뤄져 있다.    모든 것들이 객체!!

객체는 특정 타입의 인스턴스이다.

속성(value, attribute) + 동작(method)

함수가 더 큰 모양, 메소드가 더 작은 것

![image-20220126091037479](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220126091037479.png)

-----> 정수들이 int라는 클래스의 인스턴스        

type 찍으면 class 라고 앞에 나옴(class 'int')

인스턴스  ====>  사례, 예시 (클래스로 만들어진 객체)

* 클래스와 인스턴스의 차이(붕어빵틀, 붕어빵)

클래스는 설계도, 인스턴스는 만들어진것!!!!!

![image-20220126091119094](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220126091119094.png)

type - 어떤 클래스로 만들어졌는지를 말함

객체  ---- 속성(데이터) + 메소드(함수)



![image-20220126091212152](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220126091212152.png)

객체를 지향하는(객체가 중심이 되는) 프로그래밍

![image-20220126091427928](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220126091427928.png)

[].sort()       ---------> 리스트 원본을 바꿀 수 있는 메소드가 있다는 점이 절차지향과 차이점

데이터를 직접적으로 조작가능

![image-20220126091923657](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220126091923657.png)



오른쪽을 보았을 때 직접 변경도 가능하고 추가도 가능하고.....

S + V 라고 했을 때 객체를 주어라고 이해하면 됨.



절차지향 프로그래밍이 필요한 이유 - 현실 세계를 프로그램 설계에 반영(추상화)

![image-20220126092337665](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220126092337665.png)

class 하고 :

밑에 속성과 메소드를 적어주면 설계도가 완성됨 

데이터의 타입은 클래스를 말함

클래스를 만드는건 새로운 데이터 타입을 만드는것과 같다

클래스 안에 정의된 함수 - 메소드

인스턴스 변수 - 속성

dir() --- 어떠한 타입(클래스)에 속성과 메소드가 무엇이있는지 다 나옴

양쪽으로 언더(_)가 2개 붙은 것들은 필요하다면 만들어줘야하는 것들

클래스 안의 속성과 메소드에 접근하게 하는 연산자(.           dot연산자임)

len()같은 함수들은 python안에 내장되어있는 것이기 때문에 . 을 붙이지 않고 사용할 수 있는 것 

어떤 객체의 class 가 궁금하다면 .--class__ 해보면됨        앞에 int라면 (int). 해주ㅜ야함

![image-20220126131613408](Python%20%20%EA%B0%9D%EC%B2%B4%EC%A7%80%ED%96%A5%20%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D.assets/image-20220126131613408.png)

파이썬은 내부적으로 bool 과 int는 99% 같음(bool은 int를 조금 다르게 표현한 것뿐)



리터럴(literal) --  인스턴스를 만드는 방법 중 하나(123 찍거나 a =123 해주는 등 이러한 것)

별도의 클래스를 호출하지 않고 객체를 생성하는 특별한 방법 중 하나(모르고 써도 알아서 객체를 만들어줌)



직접 클래스로 인스턴스를 만드는 방법은 밑에!



클래스는 나만의 타입을 만드는것

타입을 비교하는 것도 필요하다면 만들어줘야하는것



 공통된 속성을 모아놓고 

데이터를 각각에 맞춰 정의할 수 있다





![image-20220126093200690](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220126093200690.png)

![image-20220126093213204](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220126093213204.png)

CLASS는 붕어빵 틀,  객체는 붕어빵



![image-20220126093836231](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220126093836231.png)

어떠한 클래스에서 만들어진 것인지가 매우 중요      TYPE!!

클래스 - 어떠한 것을 나누는 기준..?



쉽게 생각하면

클래스는 사람             객체를 만들어내는 설계도

인스턴스는 아이유       생성된 것  

속성      정보   값   데이터                              

메소드    행동 (def 뒤에 정의되는 부분)       

일반적으로 인스턴스 변수는 메소드 안에서 생성됨

self.name 이라고 하면 인스턴스 변수는 name 

클래스변수는 그 클래스로 만들어진 모든 인스턴스가 클래스 변수를 가짐(공유)

인스턴스 변수는 만들어진 하나하나 인스턴스에 독립적

설계하고싶은 방식대로 사용하면됨



![image-20220126134012864](Python%20%20%EA%B0%9D%EC%B2%B4%EC%A7%80%ED%96%A5%20%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D.assets/image-20220126134012864.png)

클래스 변수는 모두 공유

같은 이름으로 변수만들어버리면 안됨

인스턴스로부터 인스턴스변수를 만들어낼수 있기 때문

모든변수에 공통적으로 필요할지, 인스턴스 하나에 필요한지 잘 생각해야함

같은 이름으로 한번더 정의하면 밑에걸로 적용됨

![image-20220126134532395](Python%20%20%EA%B0%9D%EC%B2%B4%EC%A7%80%ED%96%A5%20%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D.assets/image-20220126134532395.png)

헤일리는 클래스 변수,   에이든은 인스턴스 안의 인스턴스 변수 



클래스를 비교할 때는 구현해주어야함 (__eq_ _) 이런거 써줘야함!!(안쓰면 ==도 false로 나옴!)





isinstance(인스턴스명, 클래스명)  ---> 인스턴스가 클래스 것인지 물어보는 것







#### OOP 기초

![image-20220126095546023](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220126095546023.png)

클래스 - 함수 정의하듯이

인스턴스 생성 - 함수 호출하듯이

메소드 호출 - 함수 호출하듯이

속성 - 값



클래스 : 객체들의 분류

인스턴스 - 하나하나의 실체/예

파이썬은 모든 것이 객체, 모든 객체는 특정 타입의 인스턴스



사용자정의타입 



속성 - 특정데이터타입/클래스의 객체들이 가지게 될 상태/데이터  ( 변수의 데이터 )

속성을 여러가지로 추가할 수 있음



메소드 - 특정 데이터 타입/클래스의 객체에 **공통적**으로 적용가능한 행위(함수)

CLASS 내부에 정의된 함수를 메소드라고 부르는 것(기존 함수와 달라지는 것은 없음)



객체 비교하기

- ==

동등한

변수가 참조하는 객체가 동등한 경우 True

같아보이지만 실제로 동일한 대상을 가리키고 있다고 확인해준 것은 아님

* is

동일한

두 변수가 동일한 객체를 가리키는 경우 True

얕은 복사 생각하면됨!!

if a is None   -----    none 비교시에는 이게 더 적절



#### 인스턴스 변수

인스턴스가 가지고 있는 변수  /   각각의 인스턴스에 독립적 /  클래스 변수에 접근하고 싶으면 클래스로 접근해야함

![image-20220126100848914](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220126100848914.png)

![image-20220126100934742](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220126100934742.png)





#### 인스턴스 메소드

![image-20220126100958107](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220126100958107.png)

첫번째 인자로 인스턴스 자기자신이 전달된다는게 핵심

첫번째에 self 해주는 것은 변경할 수는 있지만 **바꾸지 않는 것이 맞음**



##### self

![image-20220126101127903](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220126101127903.png)

self를 해주지 않으면 인스턴스를 정의할 수가 없다

인스턴스 메소드는 자기자신이 전달되니까 self를 붙여놓는다



생성자메소드***********

클래스가 생성(인스턴스가 만들어질때)될때 무조건 불리는 함수

클래스가 인스턴스로 만들어질 때는 무조건 호출됨





![image-20220126102425319](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220126102425319.png)





인스턴스 생성시에 호출할 메소드

![image-20220126102712845](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220126102712845.png)

---->거의 기본적인 구조

인스턴스 변수를 정의하기 위해 사용    (self.name = name 이런거)

![image-20220126103002289](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220126103002289.png)

![image-20220126103117620](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220126103117620.png)





소멸자메소드         del

![image-20220126103220493](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220126103220493.png)

![image-20220126103402554](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220126103402554.png)



매직메소드

![image-20220126103553420](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220126103553420.png)

lt  less than

gt   greater than 

![image-20220126104154729](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220126104154729.png)

![image-20220126104301802](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220126104301802.png)

![image-20220126104553682](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220126104553682.png)

p1은 보여주는 의미 / return을 더 잘 써야함

어떻게 돌아가는지 생각하는게 더 중요함

![image-20220126104810767](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220126104810767.png)



dir 해보면 함수랑 메소드 볼 수 있음

파이썬 공식문서   특수 메서드 이름들에 더 많은 정보 확인 가능



#### 클래스

![image-20220126110359857](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220126110359857.png)

객체 : 속성 + 메소드

클래스 변수/ 메소드

인스턴스  변수/ 메서드



![image-20220126110709745](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220126110709745.png)

클래스 영역내에서 선언하면됨

![image-20220126111100005](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220126111100005.png)

self랑 비슷한 느낌..?

![image-20220126111206404](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220126111206404.png)

클래스메소드는 클래스를 조작하기 위한것 !   그래서 첫번째 인자로 클래스(cls)를 넘겨줌

그래서 cls 를 클래스 내에서 사용이 가능하게 됨(출력 등..)

![image-20220126111316566](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220126111316566.png)

클래스변수가 myclass 와 같다고 나옴!



함수, 변수의 이름은 snake_case,   클래스 이름은 pascal case



클래스는 정의하는 순간 클래스의 공간이 생성됨

인스턴스는 인스턴스를 만드는 순간 init 함수가 실행되면서 circle instance에 공간이 생성됨

![image-20220126111800047](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220126111800047.png)

![image-20220126111840324](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220126111840324.png)





스태틱 메소드

![image-20220126111911613](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220126111911613.png)

어떠한 인자도 자동으로 넘겨주지 않는다

인자로 아무것도 넘겨주면 안됨 (괄호안에 넣으면 안됨)



![image-20220126112546552](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220126112546552.png)

