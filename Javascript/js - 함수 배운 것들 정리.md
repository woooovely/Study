# JS 문법을 공부하고 알게된 것-2



## 함수

함수는 Javascript에서 기본적인 구성 블록 중 하나다. 함수는 작업을 수행하거나 값을 계산하는 문장 집합 같은

자바스크립트 절차이다. 함수를 사용하려면 함수를 호출하고자 하는 범위 내에서 함수를 정의해야만 한다.



## 함수 정의

####    함수 선언

   함수 정의(또는 함수 선언)는 다음과 같은 <u>함수</u> 키워드로 구성되어 있다.

          - 함수의 이름
          - 괄호 안에서 쉼표로 분리된 함수의 매개변수 목록
          - 중괄호 `{ }` 안에서 함수를 정의하는 자바스크립트 표현



예를 들어, 다음의 코드는 `square` 라는 간단한 함수를 정의해보겠다.

```javascript
function square(number){
  return number * number;
}
```

함수 `square` 은 `number` 라는 하나의 매개변수를 가진다. 이 함수는 인수 (즉, `number`) 자체를 곱하여 반환하는 

하나의 문장으로 구성되어 있다. <u>`return`</u>문은 함수에 의해 반환된 값을 지정한다.



```javascript
return number * number
```

기본 자료형인 매개변수(number와 같은)는 **값으로** 함수에 전달된다. 즉, 값이 함수로 전달된다. 그러나 함수가 매개변수 값을 바꾸더라도

이는 **전역적으로 또는 함수를 호출하는 곳에 반영되지 않는다.**



만약 매개변수로(예: <u>`Array`</u>이나 사용자가 정의한 객체와 같이 같이 기본 자료형이 아닌 경우)를 전달하거나 함수가 객체의 속성을 변하게 하는

경우, 다음의 예처럼 그 변화는 함수 외부에서 볼 수 있다.

```javascript
function myFunc(theObject){
  theObject.make = "Toyota";
}

var mycar = {make: "Honda", model: "Accord", year: 1998};
var x, y;

x = mycar.make; //x 의 값은 "Honda" 이다.

myFunc(mycar); //myFunc 함수의 호출로 make 속성이 변경됨
y = mycar.make; //y 의 값은 "Toyota" 이다.
```



#### 함수 표현식

위에서 함수 선언은 구문적인 문(statement)이지만, **함수 표현식(<u>function expression</u>)** 에 의해서 함수가 만들어질 수 도

있다. 이 같은 함수를 **익명**이라고 한다. 이 말은 모든 함수가 이름을 가질 필요가 없다는 것을 뜻한다. 예를 들어, 함수 `square`

은 다음과 같이 정의 될 수도 있다.

```javascript
var square = function(number) { return number * number };
var x = square(4); //x 의 값은 16이다.
```

하지만, 함수 표현식에서 함수의 이름을 지정할 수 있으며, 함수 내에서 자신을 참조하는 데 사용되거나, 디버거 내 스택 추적에서 함수를 식별하는 데 

사용될 수 있다.

```javascript
var factorial = function fac(n) { return n<2 ? 1 : n*fac(n-1) };
console.log(factorial(3));
```

함수 표현식은 함수를 다른 함수의 매개변수로 전달할 때 편리하다. 다음 예는 첫 번째 인자로 함수를, 두 번째 인자로 배열을 받는 `map` 함수를 

보여준다.

```javascript
function map(f, a) {
  var result = [],
      i;
  for(i = 0; i != a.length; i++)
    result[i] = f(a[i]);
  return result;
}
```

다음 코드에서, 함수 표현식으로 정의된 함수를 인자로 받아, 2번째 인자인 배열의 모든 요소에 대해 그 함수를 실행한다.

```javascript
function map(f, a) {
  var result = [];
  var i;
  for(i = 0; i != a.length; i++)
    result[i] = f(a[i]);
  return result;
}
var f = function(x) {
  return x * x + x;
}
var numbers = [0, 1, 2, 5, 10];
var cube = map(f, numbers);
console.log(cube);
```

함수는 [0, 1, 8, 125, 1000] 을 반환한다.

JavaScript에서 함수는 조건에 의해 정의될 수 있다. 예를 들어, 다음 함수 정의는 오직 `num`이 0일 때 경우에 만 `myFunc`을 정의한다.

```javascript
var myFunc;
if (num == 0) {
  myFunc = function(theObject) {
    theObject.make = "Toyota";
  }
}
```

여기에 기술된 바와 같이 함수를 정의하는것에 더하여 [`eval()`](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/eval) 과 같이 런타임에 문자열에서 함수들을 만들기위해 [`Function`](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Function) 생성자를 사용할 수 있다.

객체내의 한 속성이 함수인 경우 **메서드**라고 한다.



#### 함수 호출

함수를 정의하는 것은 함수를 실행하는 것이 아니다. 함수를 정의하는 것은 간단히 함수의 이름을 지어주고, 함수가 호출될 때 무엇을 할지 지정 해주는 것이다. 사실 함수를 **호출**하는 것은 나타나있는 매개변수를 가지고 지정된 행위를 수행하는 것이다. 예를 들어, 만약 함수 `square`를 정의한다면, 함수를 다음과 같이 호출할 수 있다.

```javascript
square(5);
```

위의 문장은 5라는 인수를 가지고 함수를 호출한다. 함수는 이 함수의 실행문을 실행하고 값 25를 반환한다.

함수는 호출될 때 범위 내에 있어야 한다. 그러나 함수의 선언은 이 예에서와 같이, 호이스팅 될 수 있다. (코드에서 호출 아래에 선언문이 있습니다.)

```javascript
console.log(5);
/*...*/
function square(n) { return x * x };
```

