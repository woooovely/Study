# Javascript 객체를 배우고 알게된 점

## 객체 (Object)

Javascript는 객체기반의 스크립트 언어이며 Javascript를 이루고 있는 거의 모든 것은 객체이다. 객체란 **여러**

**속성을 하나의 변수에 저장할 수 있도록 해주는 데이터 타입**으로 Key / Value Pair를 저장할 수 있는 구조이다.

![img](https://media.vlpt.us/post-images/surim014/18772a40-cd3e-11e9-877d-1dda88c320e7/image.png)

## 객체 구문

```javascript
var user = new Object(); // "object constructor" syntax
var user = {}; // "object literal" syntax
```



<예시1>

* 이름 : Surim Son

* 나이 : 22

  

> Key : '이름', '나이'
>
> Value : 'Surim Son', '22'



**위 정보를 Javascript 객체로 표현해보면 아래와 같이 할 수 있다.**

![img](https://media.vlpt.us/post-images/surim014/ca9b9b60-cd3f-11e9-91f2-f10b695a4bad/image.png)

```javascript
var user = {
  name : "Surim Son",
  age : 22
};
```



## 객체의 특징

* **객체는 변수다. 그러나 객체에는 많은 값이 포함될 수도 있다.**

  (자바스크립트 변수처럼 단일 값을 포함 할 수 있다.)

* 객체는 중괄호 표기를 이용하여 만들 수 있다.

* 객체는 각각 key/value 에 대한 정보를 나열할 수 있다.

* Key는 문자열 또는 기호여야 한다.

* Value는 모든 유형이 될 수 있다.

* 객체는 한 쌍의 key/value 뒤에 쉼표를 이용하여 그 뒤에 오는 key/value 와 구분해줘야 한다.

* 객체에서 명명된 값을 프로퍼티 (Properties) 라고 한다.

* 변수는 예약어의 이름을 가질 수 없지만 객체는 어떠한 이름이어도 상관없다.

* 객체 변수를 복사하면 참조가 복사되고 객체가 복제되지 않는다.

```javascript
let user = { name : "John" };

let admin = user; // copy the reference
```

![img](https://media.vlpt.us/post-images/surim014/4710bae0-cd4f-11e9-91f2-f10b695a4bad/image.png)

## 객체의 종류

* 배열
* 함수
* 객체
* 날짜
* 수학
* 정규표현식
* Boolean은 객체일 수 있다. (new 키워드로 정의된 경우)
* 숫자는 객체가 될 수 있다. (new 키워드로 정의된 경우)
* 문자열은 객체가 될 수 있다. (new 키워드로 정의된 경우)



Javascript에서 **원시값을 제외한 모든 Javascript값은 객체이다.**

> **원시값 : 어떤 특성 또는 방법이 없는 값**
>
> **기본 데이터 형식 : 원시 값을 갖는 데이터**



### 객체가 아닌 데이터 유형

* String
* number
* boolean
* null
* undefined



## Javascript의 객체 구성

ECMA Script에서 객체는 아래와 같이 크게 3가지로 구분하고 있다.



### 1. Javascript 내장 객체 (Built-in Object)

JavaScript 엔진이 구동되는 시점에서 바로 제공되며 JavaScript코드 어디에서든 사용이 가능하다. 아래의 

내장 객체들 외에도 많은 내장 객체들이 있다.

* Global
* Object
* String
* Number
* Boolean
* Date
* Array
* Math