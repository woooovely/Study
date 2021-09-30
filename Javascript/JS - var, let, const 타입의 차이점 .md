# JS문법을 공부하고 알게된 것-1



## var, let, const 타입의 차이점

1. var (변수 **재선언 가능**)

   ```js
   var variable = '변수선언함';
   console.log(variable); //변수선언함
   
   var variable = '또 변수선언함';
   console.log(variable); //또 변수선언함
   ```

   변수 선언을 여러번 해도 에러없이 각기 다른 값이 출력 될 수 있다.

   이는 필요할 때 마다 변수를 사용 할 수 있다는(편리하다는) 장점이 될 수도 있지만, 같은 이름

   의 변수명을 남용하는 문제를 야기할 가능성이 높아지기에 단점이 더 크다고 할 수 있다.

   이를 보완하기 위해 `let`, `const` 가 추가되었다.



2. let (변수 **재선언 불가능**, 변수 **재할당 가능**)

   ```js
   let variable = '변수선언함';
   console.log(variable); //변수선언함
   
   variable = '변수 재할당함';
   console.log(variable); //변수 재할당함
   
   let variable = '또 변수선언함';
   console.log(variable); //에러! 변수 재선언 불가능
   ```

   let은 변수의 재할당은 가능하지만 var처럼 재선언은 되지 않는다. 실제로 재선언 후 크롬 개발자 도구에서 확인해보면, 에러 문구가 나타난다.

   

3. const (변수 **재선언 불가능**, 변수 **재할당 불가능**)

   ```js
   const variable = '변수선언함';
   console.log(variable);
   
   variable = '변수 재할당함';
   console.log(variable); //에러! 변수 재할당 불가능
   
   const variable = '또 변수선언함';
   console.log(variable); //에러! 변수 재선언 불가능
   ```

   const의 경우 constant(상수)의 의미 그대로 한 번만 선언하고 또 값을 재할당을 통해 바꿀 수도 없다.

