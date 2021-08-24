# This

> javascript에서 쓰이는 this 키워드에 대해 알아보자.

- this는 함수 내에서의 **함수 호출 맥락**이다.
- 함수안에서 사용하는 일종의 **변수**이면서
- 함수를 어떻게 호출하냐에 따라 달라진다.

1. 전역 문맥에서의 this

   ```javascript
   console.log(this); //window
   var a = 30;
   console.log(this.a); //30
   ```

   가장 최상위에서의 this는 window를 가리킨다.

2. 함수 문맥

   - 단순 호출

     ```javascript
     function f1() {
       return this;
     }

     f1() === window; //true
     ```

     this의 값이 호출에 의해 설정되지 않으므로 기본값인 window 전역 객체를 참조한다.(엄격모드일 때에는 undefined)

   - arrow 함수

     ```javascript
     var global = this;
     var globalFn = () => this;
     console.log(global === globalFn()); //true
     ```

   - 객체의 메서드

     ```javascript
     var object = {
       name: "min",
       fn: function () {
         return this.name;
       },
     };

     console.log(object.fn()); //min
     ```

     객체의 소속인 메서드의 this는 메서드가 소속된 객체를 가리킨다.

     메서드란 객체의 속성으로 정의된 함수를 말한다.
