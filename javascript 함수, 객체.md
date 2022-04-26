

![image-20220426102532960](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220426102532960.png)



while과 for 

같은 코드!



리스트는 인덱스로 접근이 가능한 특징을 가진다



함수는 '값'이다

()를 통해서 실행할 수 잇는 특징을 가진다



![image-20220426103546648](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220426103546648.png)

이 모든것들은 다 값이다 (함수포함)

1. 너무 자연스럽게 변수에 할당이 가능함
2. 변수에 들어갈 수 있다 = 다른 함수의 인자로 들어갈 수 있다
3. 다른 함수의 return값이 될수도 있다

js에서의 함수는 '일급 객체'



![image-20220426104713498](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220426104713498.png)

딕셔너리 key는 약간 고정값   value에는 어떤 값이든 올 수 있다(함수도 값이기 때문에 가능!) - 파이썬에서도 마찬가지



* 함수선언식

```javascript
function 함수명(파라미터) {
  로직
}

함수명(파라미터)()
```

* 함수 표현식 - 정의한 함수를 별도의 변수에 할당하는 것

```javascript
let 함수명 = function 함수명2(파라미터) {
    로직
}
let 함수명 = function(파라미터) {
    로직
}
아래방법으로 훨씬더 많이사용(앞에서 함수명 선언해줬기 때문에 뒤에서는 따로 안적어줌)

함수명(파라미터)
```

js는 인자개수에 상관이 없다(적게 넘겨주면 undefined로 채워지고 많으면 개수만큼만 자른다)

=> 매개변수와 인자의 개수 불일치 허용



![image-20220426111009737](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220426111009737.png)

함수 매개변수에 들어가있는 ...은 **Rest parameter**라고 한다

```javascript
const twoArgs = function(arg1, arg2, arg3){
  return arg1 + arg2 + arg3
}

const myArr = [1, 2, 3, 4, 5]
console.log(twoArgs(myArr))
console.log(twoArgs(1, 2, 3, 4, 5))
console.log(twoArgs(...myArr))

...은 배열을 한겹 벗겨주는 느낌?
```

여기서의 ...은 **Spread operator**라고 한다(배열을 펼친다?)





```javascript
//호이스팅
console.log(myVar);
console.log(myFunc());
console.log(twoArgs());
var myVar = 'dd'

//함수 선언식
function myFunc(arg1) {
  return true
}

//함수 표현식
const twoArgs = function(arg1, arg2, arg3, arg4) {
  return arg1 + arg2 + arg3 + arg4
}
```

![image-20220426112321606](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220426112321606.png)

함수선언식은 호이스팅이 일어남

함수표현식은 호이스팅이 일어나지 않음(함수가 이미 변수의 스코프가 되어버렸기 때문)

var로 선언하면 호이스팅이 일어나고 함수도 있게 되지만 선언부가 실행되기전 실행되면 함수인지 object인지 모르기 때문에 undefined로 처리함

=> undefined()로 실행해달라고 한거랑 같은뜻



매개변수 1개일 떄 소괄호 생략가능

몸통이 한줄로 끝나면 return도 생략가능

```javascript
// 일반적인 함수 표현식
const arrow1 = function(name) {
  return `${name}님 안녕하세요?`;
}
// console.log(arrow1('jun'));

const arrow2 = (name) => {
  return `${name}님 안녕하세요?`;
}
// console.log(arrow2('haley'));

const arrow3 = name => {
  return `${name}님 안녕하세요?`;
}
// console.log(arrow3('aiden'));

const arrow4 = name => `${name}님 안녕하세요?`
```

4개다 같은 코드!!



"Lexical scope"

호출했을때가 중요한것이 아니라 선언했을때가 기준이된다



```javascript
const myArr = [1, 2, 3, 4, 5]
console.log(myArr.length);
console.log(myArr[myArr.length-1]);

myArr.reverse()
console.log(myArr);

myArr.push(100)
console.log(myArr);

myArr.pop()
console.log(myArr);

myArr.unshift(300)
console.log(myArr);

myArr.shift()
console.log(myArr);

console.log(myArr.includes(5));
console.log(myArr.includes(99));

console.log(myArr.indexOf(5));
console.log(myArr.indexOf(444));

console.log(myArr.join('^^'));
```





딥카피가 된것은 1차원이었기 때문이고

![image-20220426133117628](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220426133117628.png)

2차원되면 얕아짐



진짜 깊은복사를 하고싶다면 for문으로 다 복사해줘야하지만 그렇게 쓰진 않는다

(깊은복사는 요소바꿔도 안바꿔지는것)

```javascript
const myArr = [1, 2, 3, 4, 5]

const myArr2 = [...myArr]

console.log(myArr2);

myArr[2] = 999
console.log(myArr2);
```



메서드 호출시 인자로 들어가는 함수가 콜백함수!!




```javascript
const myArr = ['딸기', '수박', '참외', '복숭아']

myArr.forEach((elem, idx) => {
  console.log(elem, idx);
})
```

<간단한 과제>

```javascript
const images = [
  {height: 10, width: 30},
  {height: 20, width: 90},
  {height: 54, width: 32},
]

const areas = []

// forEach 활용(height와 width곱한값 넣어주기)
images.forEach((elem, idx) => {
  //console.log(elem, idx);
  console.log(elem['height']);
  console.log(elem.height) // <<<< 추천형식!

  areas.push(elem.height * elem.width)
})

console.log(areas);

```

.연산자로 접근하는 것이 가능!!!



map은 기존배열 전체를 다른 배열로 바꿀 때 유용!!

```javascript
const myArr = [1, 2, 3, 4, 5]

// const newArr = myArr.map((elem, idx) => {
//   //로직처리
//   return ~~
// })

const newArr = myArr.map((elem) => {
  return elem * 10
})
console.log(newArr);
```

<간단한 과제>

```javascript
const images = [
  {height: 10, width: 30},
  {height: 20, width: 90},
  {height: 54, width: 32},
]

// heights = 높이만 가지고 있는 배열
const heights = images.map( (elem) => {
  return elem.height
})

console.log(heights);
```



filter 메소드

```javascript
// filter
myArr = [1, 2, 3, 4, 5, 6, 7, 8, 9]

myArr.filter( () => {} )
myArr.filter( (elem, idx, arr) => {
  //true인 애들만 모아서 새로운 배열로 반환
} )

const newArr = myArr.filter((elem) => {
  return elem % 2
})
console.log(newArr);
```

```javascript
const numbers = [15, 25, 35, 45, 55, 65, 75,85, 95]

const newArr = numbers.filter((elem) => {
  return elem > 50
})

console.log(newArr);
```



reduce 메소드

배열을 돌아가면서 한번씩 실행 

return하면서 acc에 누적하고 다끝나면 acc값을 return 해준다

```javascript
myArr = [1, 2, 3, 4, 5]
// myArr.reduce( () => {}, init )
// myArr.reduce( (acc, elem, idx, arr) => {} )

const rlt = myArr.reduce( (acc, elem) => {
  return (elem * 2) + acc
}, 0 )

console.log(rlt);
```



find메소드

```javascript
myArr = [1, 2, 3, 4, 5]

const rlt = myArr.find((elem, idx, arr) => {
  return elem > 3
})
console.log(rlt);
```

3보다 큰거 다찾고싶으면 filter쓰기

그냥 3보다 큰거 하나만 찾고싶을때는 find(딱 1개만 리턴해줌)

<간단한 과제>

```javascript
const avengers = [
  {name: 'Tony Stark', age: 45},
  {name: 'Steve Rogers', age: 32},
  {name: 'Thor', age: 40},
]

const rlt = avengers.find((elem)=>{
  return elem.age > 39
})
console.log(rlt);
```



some

조건에 맞는게 하나라도 있으면 true 반환

조건에맞는거까지만 딱 찾고 true반환 후 끝냄(다 돌지않음)

다 돌아도 없으면 false 반환

```javascript
const myArr = [1, 2, 3, 4, 5]

const rlt = myArr.some((elem)=>{
  return elem > 3
})
console.log(rlt);
```



every 메소드

모두 다 조건에 맞아야 true, 하나라도 아니면 false

```javascript
const myArr = [1, 2, 3, 4, 5]

const rlt = myArr.every((elem)=>{
  return elem > 0
})
console.log(rlt);
```





## 객체

객체는 속성의 집합

중괄호 내부에 key, value의 쌍으로 표현

key는 문자열타입만 가능

value는 모든 타입(함수포함) 가능

객체 접근은 점 또는 대괄호로 가능

객체 만드는것은 json형태로 만들면됨!!

**this**만 주의하면됨!!



객체 안에 들어간 함수 => 메소드

어떤 객체안에 있는 메소드 안의 this는 그 객체를 의미

```javascript
const me = {
  'firstName': 'jonghyeok',
  'lastName': 'Oh',
  getFullName: function () {
    return this.firstName + this.lastName
  }
}
```

여기서 this는 me를 의미함(전체)

key값 문자열로 안쓰고 ' ' 안해줘도 됨!

key에서 중간에 띄어쓰기 같은게 있으면 따옴표 필수!!

어떤 객체에서 바로 this를 쓰면 그 객체자체가 아닌 window를 가리킴

객체라서 이런식으로 접근가능

```javascript
console.log(me.firstName);
console.log(me.getFullName())
```



### 객체관련 ES6 문법

다 귀찮아서 줄여쓰는 것들!!

* 속성명 축약

```javascript
const books = ['Learning JS', 'Learning Python']
const magazines = ['Vogue', 'Science']

const bookShop_before = {
  books: books,
  magazines: magazines,
}

const bookShop_after = {
  books,
  magazines,
}

console.log(bookShop_after);
```

객체 정의시 key와 할당하는 변수 이름이 같으면 줄여쓸 수 있다

굉장히 자주 사용!



* 메소드명 축약

```javascript
const books = ['Learning JS', 'Learning Python']
const magazines = ['Vogue', 'Science']

const bookShop_before = {
  books: books,
  magazines: magazines,
}

const bookShop_after = {
  books,
  magazines,

  greeting1: function () {
    console.log('hola!');
  },

  greeting2() {
    console.log('hola!');
  },
}

bookShop_after.greeting2()
```

![image-20220426152038471](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220426152038471.png)



* 계산된 속성

key의 이름도 동적으로 생성가능

대괄호 안쪽에 내가 넣고싶은 변수넣어주면됨



* 구조분해할당

```javascript
const userInfomation = {
  name: 'ssafy kim',
  userId: 'ssafyStudent1234',
  phoneNumber: '010-1234-1234',
  email: 'ssafy@ssafy.com',
}

// const name = userInfomation.name
// const userId = userInfomation.userId
// const phoneNumber = userInfomation.phoneNumber
// const email = userInfomation.email

// const {name} = userInfomation
// const {userId} = userInfomation
// const {phoneNumber} = userInfomation
// const {email} = userInfomation

const {name, userId, phoneNumber, email} = userInfomation
```

맨 아랫줄로 사용!(가장 간단하다)

물론 실무에서는 다른거 쓰는곳도 있기 때문에 알아는 둬야함

아래코드는 실전에서 사용하는 방식

```javascript
const userInfomation = {
  name: 'ssafy kim',
  userId: 'ssafyStudent1234',
  phoneNumber: '010-1234-1234',
  email: 'ssafy@ssafy.com',
}

// const {userId, email} = userInfomation

function getUserInfo({userId, email}) {
  console.log(`User ID: ${userId}`);
  console.log(`User Email: ${email}`);
}

getUserInfo(userInfomation)
```

![image-20220426153758989](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220426153758989.png)



JSON.parse({'name}':'jonghyeok, 'age':'23'}) 이런식으로!

JSON => 자바스크립트 객체

JSON.stringify()         json포맷을 가진 문자열형태로바꾸는것

자바스크립트 객체 => JSON 





this 정리

```javascript
function getFullName() {
  return this.firstName + this.lastName
}

const me = {
  firstName: 'justin',
  lastName: 'kim',
  getFullName: getFullName,
}

const you = {
  firstName: 'zzulu',
  lastName: 'lim',
  getFullName: getFullName,
}

me.getFullName()  // justinkim
you.getFullName() // zzululim
getFullName()     // NaN
```

![image-20220426155927036](C:/Users/%EC%98%A4%EC%A2%85%ED%98%81/AppData/Roaming/Typora/typora-user-images/image-20220426155927036.png)



## lodash

라이브러리의 종류

array, object등 자료구조다룰때 유용하고 간편한 유틸리티 함수들 제공

sortBy(정렬), range, random(랜덤하게 샘플링), coloneDeep(딥카피)



언더바. => lodash 사용한것

```javascript
const myArr = [1, 2, 3, 4, 5, [6, 7, 8]]
// console.log(_.sampleSize(myArr,2));

// console.log(_.reverse(myArr));

// const myRange = _.range(1, 10, 2)
// console.log(myRange);

// 깊은 복사
const copyArr = _.cloneDeep(myArr)
console.log(copyArr);

// 원본 배열 변경
myArr[5][1] = 9999
console.log(myArr);
```

cloneDeep 해주면 원본만 바뀌고 cloneDeep해준 배열은 안바뀜!!