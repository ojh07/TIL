# Python 객체지향 프로그래밍2



#### 메소드 정리

![image-20220126140858467](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220126140858467.png)

사용자 정의(함수, oop 클래스)  와   활용하는 부분은 다르므로 이해에 주의!

메소드도 내가 어떻게 정의하냐에 따라..

![image-20220126141325151](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220126141325151.png)

인스턴스 메소드는 클래스에 종속되지 않음

클래스 메소드 - 클래스에 종속적인 모습

![image-20220126141437084](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220126141437084.png)

스태틱 메소드도 클래스에 종속된 모습

클래스로 어떠한 모습 쓰고 싶을때 스태틱 메소드로 

![image-20220126141954599](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220126141954599.png)





#### 객체 지향의 핵심개념

![image-20220126142059489](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220126142059489.png)

* 추상화

클래스로 표현하는 것

![image-20220126142447150](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220126142447150.png)



* 상속

![image-20220126142551904](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220126142551904.png)

상속을 통한 메소드 재사용 가능!!
![image-20220126142757199](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220126142757199.png)

![image-20220126143536587](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220126143536587.png)

![image-20220126143554171](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220126143554171.png)

![image-20220126143852452](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220126143852452.png)

boo1은 0또는 1 ,    int는 더 큰 범위

float = 정수 + 소수

내장예외 파이썬 <--- 이대로 써야함



상속관련 함수와 메소드

![image-20220126144624624](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220126144624624.png)



![image-20220126144931068](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220126144931068.png)



<상속정리>

![image-20220126145042064](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220126145042064.png)

def ~~~(cls) -------------> 정의를 하고있다는 것을 명심해야함

![image-20220126150756224](Python%20%EA%B0%9D%EC%B2%B4%EC%A7%80%ED%96%A5%20%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D2.assets/image-20220126150756224.png)

함수에서 무엇을 쓰고싶다면 무조건 input으로 넘겨야 한다   로컬스코프



다중상속

![image-20220126150839832](Python%20%EA%B0%9D%EC%B2%B4%EC%A7%80%ED%96%A5%20%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D2.assets/image-20220126150839832.png)

![image-20220126151012935](Python%20%EA%B0%9D%EC%B2%B4%EC%A7%80%ED%96%A5%20%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D2.assets/image-20220126151012935.png)

오른쪽 swim이 왼쪽 swim 오버라이드해서 사용중

위의 예시에서는 먼저 상속받은 것(Dad)의 유전자가 출력됨



상속 관련 함수와 메소드

![image-20220126151236644](Python%20%EA%B0%9D%EC%B2%B4%EC%A7%80%ED%96%A5%20%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D2.assets/image-20220126151236644.png)

순서는 (다중상속인경우) 먼저 상속받은걸로

모든 것의 끝에는 object가 포함됨!



#### 다형성

![image-20220126151604881](Python%20%EA%B0%9D%EC%B2%B4%EC%A7%80%ED%96%A5%20%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D2.assets/image-20220126151604881.png)



![image-20220126151616961](Python%20%EA%B0%9D%EC%B2%B4%EC%A7%80%ED%96%A5%20%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D2.assets/image-20220126151616961.png)

![image-20220126151652941](Python%20%EA%B0%9D%EC%B2%B4%EC%A7%80%ED%96%A5%20%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D2.assets/image-20220126151652941.png)

![image-20220126151720069](Python%20%EA%B0%9D%EC%B2%B4%EC%A7%80%ED%96%A5%20%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D2.assets/image-20220126151720069.png)





#### 캡슐화

![image-20220126151758185](Python%20%EA%B0%9D%EC%B2%B4%EC%A7%80%ED%96%A5%20%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D2.assets/image-20220126151758185.png)

![image-20220126152201420](Python%20%EA%B0%9D%EC%B2%B4%EC%A7%80%ED%96%A5%20%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D2.assets/image-20220126152201420.png)

![image-20220126152306218](Python%20%EA%B0%9D%EC%B2%B4%EC%A7%80%ED%96%A5%20%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D2.assets/image-20220126152306218.png)

![image-20220126152323189](Python%20%EA%B0%9D%EC%B2%B4%EC%A7%80%ED%96%A5%20%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D2.assets/image-20220126152323189.png)

​                                                                                                            -------> age만큼은 직접접근 x (약속)

![image-20220126153201713](Python%20%EA%B0%9D%EC%B2%B4%EC%A7%80%ED%96%A5%20%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D2.assets/image-20220126153201713.png)

![image-20220126153432114](Python%20%EA%B0%9D%EC%B2%B4%EC%A7%80%ED%96%A5%20%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D2.assets/image-20220126153432114.png)

![image-20220126153702352](Python%20%EA%B0%9D%EC%B2%B4%EC%A7%80%ED%96%A5%20%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D2.assets/image-20220126153702352.png)

property 는 속성으로 가져오는 역할



**파이썬 문서 확인하는게 좋음!!1**



![image-20220126154208628](Python%20%EA%B0%9D%EC%B2%B4%EC%A7%80%ED%96%A5%20%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D2.assets/image-20220126154208628.png)





<총정리>

![image-20220126154748241](Python%20%EA%B0%9D%EC%B2%B4%EC%A7%80%ED%96%A5%20%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D2.assets/image-20220126154748241.png)

리스트메소드 - 본인을 바꾸는 메소드 존재

스트링 메소드 - 본인 바꾸는 것 x 해당하는 문자열 결과를 리턴



![image-20220126155101760](Python%20%EA%B0%9D%EC%B2%B4%EC%A7%80%ED%96%A5%20%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D2.assets/image-20220126155101760.png)

while은 얼마나 반복할지 모를때 사용

range(len(통)) ---- 이건 인덱스 필요한 경우 매우 중요(알고리즘 풀이때)



반복 : 원하는만큼 반복되는지,  반복할때 어떤 값이 나올지 생각



<파이썬 공식문서>

자습서

라이브러리 레퍼런스 - 사전

용어집 - 정의 볼 수 있음

자주나오는 질문 