# 자바스크립트 기초 강좌 : 100분 완성 by.코딩앙마

### #1 -변수

![2](js공부중/어치/2.PNG)문자는 ' ', " ", ``로 감싼다.

cf) alert() // 경고창을 띄우는 함수

console.log() // 콘솔에 출력하는 함수 



**let** : 

![1](js공부중/어치/1.PNG)

**const** :절대로 바뀌지 않는 상수

-> 자바스크립트에서 변수를 선언할때 변하지 않는 값은 `const`, 변할 수 있는 값은 `let`으로 선언한다.







### #2 -자료형

1) `문자열형`

'', "", ``로 감싼다.

※주의 : 백틱은(``) 문자열 내부에 변수를 표현할 때 사용한다. 달러중괄호(${ }) 사이에 **변수**나 **표현식** 사용 가능

일반 따옴표 사용시 변수값이 아니라 변수명이 그대로 노출됨

![3](js공부중/어치/3.PNG)![4](js공부중/어치/4.PNG)

2) `숫자형`

사칙연산(+, -, *, /) 가능

Infinity : 무한대를 나타내는 상수, 어떠한 수를 0으로 나누거나 Infinity를 어떠한 수로 사칙연산한 결과

NaN : 계산식의 결과가 숫자가 아님을 나타내는 상수( == Not a number)

3) `boolean`

비교연산의 결과값으로 true 또는 false중 하나의 값을 갖는다.

( false : 비어있는 문자열, 0, null, undefined)

4)  `null`

변수를 선언하고 null을 할당함, 값이 없거나  비어있음을 의미함

5. `undefined`

변수에 선언만하고 아무것도 할당하지 않았을 때



위 5가지를 제외한 모든 값은  `객체형`이다.   cf. `심볼형`



![5](js공부중/어치/5.PNG)

문자형+문자형 = 문자형

문자형+ 숫자형 = 문자형



typeof 연산자 사용시, 변수의 자료형을 알 수 있다.

typeof null <= Object,	null != 객체, 하위호환성

typeof undefined <= Undefined



### #3 -alert, prompt, confirm

**대화상자**

![alert](js공부중/어치/alert.PNG)

`alert()`			알려줌   ex. 삭제 되었습니다.



![prompt](js공부중/어치/prompt.PNG)

![7](js공부중/어치/7.PNG)

![6](js공부중/어치/6.PNG )

prompt()함수의 첫번째 파라미터는 사용자에게 보여줄 메시지, 경우에 따라 추가하는 두번째 파라미터는 입력 받을수 있는 필드의 디폴트 값(초기값) 

`prompt()`	  입력 받음 <= 사용자에게 메시지 보여주고 입력받을 수 있는 필드 제공



![confirm](js공부중/어치/confirm.PNG)

`confirm()`	  확인받음   true, false를 return 받음





### #4 -형변환

![10](js공부중/어치/10.PNG)

![12](js공부중/어치/12.PNG)

`Boolean(0) // false` 

Boolean('0') // true 

`Boolean('') //false` 

Boolean(' ') //true





### #5 -기본 연산자

사칙연산 : +-*/%

거듭제곱 : **     

```java
const num = 2**3;
console.log(num); // 8
```





### #6 -비교 연산자, 조건문(if, else)

`비교 연산자`

![17](js공부중/어치/17.PNG)

=== : 타입까지 비교

1=="1"(true)

1==="1"(false)



`조건문(if, else)`

if - 조건이 true일 때 실행되는 문장

else - 조건이 false일 때 실행되는 문장





### #7 -논리 연산자(AND, OR, NOT)

![20](js공부중/어치/20.PNG)

![18](js공부중/어치/18.PNG)

![19](js공부중/어치/19.PNG)





### #8 -반복문(for, while, do while)

`for`

![21](js공부중/어치/21.PNG)

`while`

![22](js공부중/어치/22.PNG)



`do_while`

![23](js공부중/어치/23.PNG)

break; // 반복문을 중단 빠져나감

continue; // 반복문을 중단 다음 반복으로 넘어감





### #9 -switch문

cf) if,else문

![24](js공부중/어치/24.PNG)

![25](js공부중/어치/25.PNG)





### #10 -함수(function)의 기초

#### 함수를 사용하는 이유

![0](C:\Users\multicampus\Desktop\js공부중\0.PNG)

-> 재활용성, 유지보수성 향상을 위하여

-> 자바스크립트에서 함수는 1급 객체다.

ex) 브라우저 내장 함수 : console, alert, confirm, prompt 등

#### 함수의 형태 : 함수 선언문

![1](C:\Users\multicampus\Desktop\js공부중\1.PNG)

-> 함수, 함수명, 매개변수

->함수의 호출

`매개 변수가 없는 함수`

![2](C:\Users\multicampus\Desktop\js공부중\2.PNG)

`매개변수가 있는 함수`

![3](C:\Users\multicampus\Desktop\js공부중\3.PNG)

![4](C:\Users\multicampus\Desktop\js공부중\4.PNG)

const -> let 지역변수, 선언된 블록 안에서 사용 가능함(block scope)   cf. var function scope 

sayHello();

매개변수가 없을때, name은 undefined -> undefined의 불린값 false -> if문 안들어감.  

![5](C:\Users\multicampus\Desktop\js공부중\5.PNG)

+연산자 활용하여 문자열 만들기

![ ](C:\Users\multicampus\Desktop\js공부중\6.PNG)

`(백틱) 활용하여 문자열 만들기

![7](C:\Users\multicampus\Desktop\js공부중\7.PNG)

함수 내부에서 선언된 변수(지역 변수)는 함수 내부에서만 사용 가능하다.

<-> 전역 변수

※ 전역 변수, 지역 변수 서로 간섭X <- 동일한 이름으로 2개다 가능함.

![8](C:\Users\multicampus\Desktop\js공부중\8.PNG)

`let newName = name || 'friend';` // name이 false 즉, undefined일때만 newName에 'friend'가 할당됨.

undefined의 boolean값 : false

![9](C:\Users\multicampus\Desktop\js공부중\9.PNG)

name 매개변수 없을 때만 default value로 'friend' 할당됨



return

![10](C:\Users\multicampus\Desktop\js공부중\10.PNG)

![11](C:\Users\multicampus\Desktop\js공부중\11.PNG)



![12](C:\Users\multicampus\Desktop\js공부중\12.PNG)

return값이 없는 경우 undefined 반환함

* undefined, null, NaN

![13](C:\Users\multicampus\Desktop\js공부중\13.PNG)



### #11 -함수 표현식, 화살표 함수(arrow function)

#### 함수의 형태 : 함수 표현식

![14](C:\Users\multicampus\Desktop\js공부중\14.PNG)

`함수 표현식` : 익명함수를 변수에 할당하는 방식, 변수명을 함수명으로 사용함

 ![15](C:\Users\multicampus\Desktop\js공부중\15.PNG)

함수 선언문을 통하여 선언한 함수는 어디서든 호출 가능한 이유 ?

: JavaScript 내부의 알고리즘 때문! 

코드를 한줄씩 해석하여 실행하는 인터프리터 언어지만, 실행 전 함수 선언문을 찾아서 함수를 생성해 둠(호이스팅)



 ![16](C:\Users\multicampus\Desktop\js공부중\16.PNG)

함수 표현식을 통하여 선언한 함수는 호이스팅 안된다.



#### 화살표 함수(arrow function)

![17](C:\Users\multicampus\Desktop\js공부중\17.PNG)

![18](C:\Users\multicampus\Desktop\js공부중\18.PNG)

파라미터 앞 `function` 대신에, 파라미터 뒤 `=>`

![19](C:\Users\multicampus\Desktop\js공부중\19.PNG)

return문은 {} 대신에 ()호 함수를 붂을 수 있다.

![20](C:\Users\multicampus\Desktop\js공부중\20.PNG)

return문이 1줄이라면 괄호 생략 가능

![23](C:\Users\multicampus\Desktop\js공부중\23.PNG)

return문 전 코드가 여러줄이면 일반괄호 사용 불가능

![21](C:\Users\multicampus\Desktop\js공부중\21.PNG)

파라미터가 1개라면 괄호 생략 가능

```javascript
const printPie = () => 3.14;
const result = printPie();
```



파마미터가 없다면 괄호 생략 불가능 





![22](C:\Users\multicampus\Desktop\js공부중\22.PNG)

파라미터가 없다면 괄호 생략 불가능



```javascript
const getObject = () =>({
    name : "철수",
    age : 20,
});
```

객체 리턴



```javascript
const outer = (x) => () => x*x; 
```

함수 리턴



※ 함수 선언문 -> 함수 표현식 ->화살표 함수(ES6)

​     함수명			  변수명





### #12 -객체(Object)

![2-1](C:\Users\multicampus\Desktop\js공부중\2-1.PNG)

![2-2](C:\Users\multicampus\Desktop\js공부중\2-2.PNG)

접근이나 추가 시 . 또는 [] 사용, 삭제시 delete 명령어 사용함 

![2-3](C:\Users\multicampus\Desktop\js공부중\2-3.PNG)

![2-4](C:\Users\multicampus\Desktop\js공부중\2-4.PNG)

위 두 코드는 같다. property이름 == 변수명일 때, 변수명은 생략 가능

![2-5](C:\Users\multicampus\Desktop\js공부중\2-5.PNG)

객체에 없는 프로퍼티 접근 시, `undefined`

객체에 해당 프로퍼티 있는지 없는지 볼때는 `in` 사용함.    cf. 프로퍼티 in 객체

(in 예제)

![2-7](C:\Users\multicampus\Desktop\js공부중\2-7.PNG)

undefined의 boolean값은 false

age가 user에 없으면 'age' in user는 false

![2-6](C:\Users\multicampus\Desktop\js공부중\2-6.PNG)

(for...in 반복문 예제)

![2-8](C:\Users\multicampus\Desktop\js공부중\2-8.PNG)

x 는 name, age 객체의 속성들을 가져옴





### #13 -객체(Object)-method, this 

![2-9](C:\Users\multicampus\Desktop\js공부중\2-9.PNG)

객체에 함수 할당

![2-10](C:\Users\multicampus\Desktop\js공부중\2-10.PNG)

function 키워드 생략 가능

![2-11](C:\Users\multicampus\Desktop\js공부중\2-11.PNG)

![2-12](C:\Users\multicampus\Desktop\js공부중\2-12.PNG)

boy라는 객체에 sayHello() 함수를 넣음

boy.sayHello(); // 여기서 sayHello함수의 this는 `이 함수를 가지고 있는 객체 boy`가 된다.

메소드 내에서는 `객체명`을 직접 써주기보단 `this`를 활용하는 것이 더 좋다.



![2-13](C:\Users\multicampus\Desktop\js공부중\2-13.PNG)

`화살표 함수는 자신만의 this를 가지지 않는다.` 따라서 this != boy, this== window 또는 global

-> 객체, 메소드, 메소드 내의 this(==>해당 객체 가르킴)





### #14 -배열(Array)

: 순서가 있는 리스트

![3-1](C:\Users\multicampus\Desktop\js공부중\3-1.PNG)

![3-2](C:\Users\multicampus\Desktop\js공부중\3-2.PNG)



![3-3](C:\Users\multicampus\Desktop\js공부중\3-3.PNG)

```javascript
arr.length // 배열의 길이 : 5
```

​         

![24](js공부중/24.PNG)

`push()` : 배열 끝 요소 추가

![25](js공부중/25.PNG)

`pop()` : 배열 끝 요소 삭제

![26](js공부중/26.PNG)

`shift(), unshift()` : 배열 앞에 요소 추가/제거

![27](js공부중/27.PNG)

![28](js공부중/28.PNG)

반복문 : for 사용 가능, for...of(인덱스 얻지 못한다는 게 단점임)     cf. for...in
