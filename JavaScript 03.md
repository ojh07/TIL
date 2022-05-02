# JavaScript 03



## AJAX

Asynchronous JavaScript And XML (비동기식 자바스크립트와 XML)

서버와 통신을 위해 XMLHttpRequest 객체 사용

JSON을 더 많이 사용!



### AJAX 특징

* 페이지 전체를 새로고침 하지 않아도 수행되는 **비동기성**

* 서버의 응답에 따라 전체가 아닌 일부분만 업데이트도 가능



## Asynchronous JavaScript

* 동기식

순차적, 직렬적, 요청보내고 응답받아야 다음동작이 이루어짐(Blocking)

* 비동기식

병렬적, 요청보내고 응답기다리지 않고 다음동작이 이루어짐(Non-Blocking)



**JavaScript는 single threaded**

Threads - 프로그램이 작업을 완료하기 위해 사용할 수 있는 단일 프로세스

각 스레드는 한번에 하나의 작업만 수행

이벤트를 처리하는 **Call Stack**이 하나인 언어이다



1. 즉시 처리하지 못하는 이벤트들을 Web API로 보내서 처리하도록 하고
2. 처리된 이벤트들은 처리된 순서대로 Task queue에 줄세워놓고
3. Call Stack이 비면 Event Loop가 대기줄에서 가장오래된 이벤트를 Call Stack으로 보냄

![image-20220502132403580](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220502132403580.png)

* Call Stack - 요청이 들어올 때마다 해당 요청을 순차적으로 처리하는 Stack형태의 자료구조 (LIFO)

* Web API - 자바스크립트 엔진이 아닌 브라우저 영역에서 제공하는 API

setTimeout(), DOM events, AJAX로 데이터를 가져오는 시간이 소요되는 일들을 처리

* Task Queue - 비동기 처리된 콜백함수가 대기하는 queue형태의 자료구조(FIFO), 

메인 thread가 끝나고 실행되어 후속 자바스크립트 코드가 차단되는것 방지

* Event Loop - Call Stack이 비어있는지 확인

비어있는 경우 Task queue에서 실행대기중인 callback함수가 있는지 확인

Task queue에 대기중인 callback함수가 있다면 가장 앞의 callback함수를 call stack으로 push



#### Zero delays

* 실제로 0초 이후에 콜백 함수가 시작된다는 의미 x
* setTimeout 함수에 특정 시간제한을 설정했어도 대기 중인 메시지의 모든 코드가 완료될 때까지 대기해야함



### 순차적인 비동기 처리를 위한 2가지 작성방식

1. Async callbacks

백그라운드에서 실행을 시작할 함수를 호출할 때 인자로 지정된 함수

1. promise-style

XMLHttpRequest 객체를 사용하는 구조보다 조금 더 현대적인 버전



## Callback Function

다른 함수에 인자로 전달된 함수

작업의 단위

동기식, 비동기식 모두 사용됨(비동기 작업이 완료된 후 코드 실행을 계속하는데 주로 사용됨 -> 비동기 콜백)

* 일급 객체 -다른 객체들에 적용할 수 있는 연산을 모두 지원하는 객체(함수)

인자로 넘길 수 있어야함

함수의 반환값으로 사용할 수 있어야함

변수에 할당할 수 있어야 함



### Async callbacks

백 그라운드에서 코드 실행을 시작할 함수를 호출할 때 인자로 지정된 함수



콜백함수를 사용하는 이유 

* 명시적인 호출이 아닌 특정 루틴 혹은 action에 의해 호출되는 함수

* 비동기 로직을 수행할 때 callback함수는 필수



callback Hell

여러개의 연쇄 비동기 작업을 할 때 마주하는 상황

해결방법

1. 코드의 깊이를 얕게
2. 모듈화
3. 모든 단일 오류 처리
4. promise callbacks

**4번방식**이 가장 현실적으로 많이사용됨!!



## Promise

비동기 작업의 최종 완료 또는 실패를 나타내는 객체

미래의 완료 또는 실패와 그 결과값, 미래의 어떤 상황에 대한 약속

성공(이행)에 대한 약속 **.then()**

실패(거절)에 대한 약속 **.catch()**



**.then(callback)**

이전 작업이 성공했을 때 수행할 작업을 나타내는 callback 함수

각 콜백함수는 이전 작업의 성공결과(return값)을 인자로 전달받음

성공했을 때의 코드를 콜백함수안에 작성



**.catch(callback)**

.then이 하나라도 실패하면 동작

이전작업의 실패로 생성된 error객체는 catch 블록 안에서 사용가능



각각의 .then() 블록은 서로다른 promise를 반환

.then()을 여러개 사용하여 연쇄적인 작업을 수행

여러 비동기 작업을 차례대로 수행가능



.then()과 .catch()메서드는 모두 promise를 반환하기 때문에 chaining 가능

**반환값 반드시 있어야함(없으면 콜백함수가 이전의 promise결과 못받음**



.finally(callback)

결과와 상관없이 callback함수 실행



### promise가 보장하는것

1. 현재 실행중인 콜스택을 완료하기 이전에는 절대 호출되지 않음
2. 비동기 작업이 성공하거나 실패한 뒤 .then() 메서드를 이용하여 추가한 경우에도 1번과 똑같이 동작



## Axios

Promise based HTTP client for the browser

브라우저를 위한 promise 기반의 클라이언트

