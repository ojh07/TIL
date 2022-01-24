# Python : 데이터 구조 및 활용



데이터 구조 

메서드(method)

string.split()   -> string이 split 한다

앞에것이 ~을 한다  로 알기(주어, 동사)

조건문, 반복문으로 해결해야하는 것도 메서드로 알아볼 수 있음

메서드는 입력값과 반환값이 중요!







#### 순서가 있는 데이터 구조

* 문자열(immutable) 일부만을 수정할 수 없음

'문자열'.메서드()

문자들의 나열,  모든 문자는 str타입

find와 index 는 다른점 주의하기

하나가 아닌 모든 위치를 찾고싶다면 반복문 사용해야함

is가 붙어있으면 반환하는 것은 boolean 형(T/F)임.



istitle 은 중간에 공백을 기준으로 각자 첫번째 단어가 대문자인지 여부

isnumeric()이 가장 넓은 범위를 가진다



![image-20220124134512255](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220124134512255.png)

문자열이 immutable이지만 원본을 변경하는것이 아니라 변경된 값을 반환하는 것이기 때문에 가능

repalce에서 count는 선택

![image-20220124134752561](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220124134752561.png)

strip은 매우 자주 활용(데이터분석시)

![image-20220124134855401](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220124134855401.png)

split은 알고리즘 문제에서 많이 사용됨

![image-20220124135019547](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220124135019547.png)

sep는 구분자

![image-20220124135100471](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220124135100471.png)

join은 **string메서드**라는 것을 명심해야함

요소가 문자열이 아닌경우에는 리스트를 map(str, numbers) 해주면 됨

구분자는 , 공백 ! 등 여러가지

![image-20220124135436211](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220124135436211.png)



.title()은 공백과 ' 을 기준으로 대문자가 되게함





* 리스트

![image-20220124140330400](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220124140330400.png)

리스트의 요소를 변경시키는 것들이 있음(문자열과 다른점... 리스트는 mutable이기 때문)



하나하나씩 모으는 통을 만들 때- 빈 통을 만들고 append 함수 많이 사용할것..

.extend(**iterable**)  ----- 리스트끼리 붙이는 것   

![image-20220124140652285](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220124140652285.png)



.remove(x) 리스트에서 값이 x인 것 삭제,   없는 경우 valueError

.pop(i)   정해진 위치 i에 있는 값 삭제, 그 항목 반환( i가 지정되지 않으면 마지막 항목 삭제 후 반환) -- **값을 넣는 것이 아니라 인덱스를 넣는 것** 주의

.clear()    모든 항목 삭제(빈 리스트가 됨)

.index(x)   x값을 찾아 해당 index 반환

.count(x)    원하는 값의 개수를 반환

.sort()          원본 리스트를 정렬함. none이 출력됨

sorted()함수와 비교                                         .은 메서드 .없으면 함수로 보면됨

함수는 원본이 아니라 정렬된 리스트를 반환하는 것, 메서드는 원본 자체를 정렬시킴

![image-20220124141741889](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220124141741889.png)

![image-20220124141844117](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220124141844117.png)



.reverse()은 순서를 반대로 뒤집는 것(정렬하는 것이 아님),           원본 자체의 순서를 뒤집는 것

sort하고 reverse해주면 정렬된 상태로 뒤집힘       





* 튜플(핵심 : 변경불가)

튜플은 변경할 수 없어서 값에 영향을 미치지 않는 메소드만 지원

리스트 메소드 중에 항목 변경하는 메소드를 제외하고 대부분 동일

![image-20220124142339797](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220124142339797.png)

튜플을 직접 만들어서 쓰는 경우가 없을것..





#### 순서가 없는 데이터 구조

* 셋

변경, 삽입, 삭제 가능

집합과 동일한 구조

순서가 없음(정렬된 것처럼 보여도 그건 눈속임이다)

![image-20220124143724760](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220124143724760.png)



.update(*others)

.remove(elem)  -  셋에서 삭제하고 **없으면 keyError**

.discard(elem) - remove와 다른점은 없어도 **error 발생하지 않음**

.pop() -  임의의 원소를 제거해 반환(순서가 없기 때문 -----리스트는 순서있어서 pop했을 때 마지막이라고 지정됨)





* 딕셔너리

딕셔너리 - 알고리즘과는 관련이 별로 없음

![image-20220124144254291](Python%20%20%EB%8D%B0%EC%9D%B4%ED%84%B0%20%EA%B5%AC%EC%A1%B0%20%EB%B0%8F%20%ED%99%9C%EC%9A%A9.assets/image-20220124144254291.png)

.get(key)    ---key로 value를 가져옴,  keyerror 발생x 

.pop(key)   --- 디폴트값이 없으면 error

![image-20220124144458518](Python%20%20%EB%8D%B0%EC%9D%B4%ED%84%B0%20%EA%B5%AC%EC%A1%B0%20%EB%B0%8F%20%ED%99%9C%EC%9A%A9.assets/image-20220124144458518.png)



.update()  --- 값을 제공하는 key, value로 덮어씀

![image-20220124145012674](Python%20%20%EB%8D%B0%EC%9D%B4%ED%84%B0%20%EA%B5%AC%EC%A1%B0%20%EB%B0%8F%20%ED%99%9C%EC%9A%A9.assets/image-20220124145012674.png)



**파이썬 자습서에 가서 보면 좋음**(가능하면 영어로)





### 얕은 복사와 깊은 복사

복사방법

* 할당

대입연산자(=) 

![image-20220124145603306](Python%20%20%EB%8D%B0%EC%9D%B4%ED%84%B0%20%EA%B5%AC%EC%A1%B0%20%EB%B0%8F%20%ED%99%9C%EC%9A%A9.assets/image-20220124145603306.png)

![image-20220124145802871](Python%20%20%EB%8D%B0%EC%9D%B4%ED%84%B0%20%EA%B5%AC%EC%A1%B0%20%EB%B0%8F%20%ED%99%9C%EC%9A%A9.assets/image-20220124145802871.png)

리스트 통을 같이 바라보고 있다!

![image-20220124150001359](Python%20%20%EB%8D%B0%EC%9D%B4%ED%84%B0%20%EA%B5%AC%EC%A1%B0%20%EB%B0%8F%20%ED%99%9C%EC%9A%A9.assets/image-20220124150001359.png)

슬라이싱 활용해서 다른 통으로 또는 리스트 함수 이용

리스트를 그대로 할당 - 주소가 들어가있어서 같은 통을 바라보게 됨

안에가 복잡한 구조라면 깊은 복사해야함!

* 얕은 복사
* 깊은 복사

import copy

copy.deepcopy()

같은 값이지만 참조를 다르게 하려면 깊은 복사 하면됨

리스트 안의 값으로..



* 메서드는 암기가 필요하다