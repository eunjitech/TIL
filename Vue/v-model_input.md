# input v-model을 number형식으로 받는 법

> 들어가기 전에, v-model은 양방향 데이터바인딩을 할 수 있는 vue 속성이다.

### input창에 숫자가 아닌 문자가 입력이 되었을 때, alert창이 뜨도록 하기 위해서 무엇을 해야할까?

참고 : input에 입력된 데이터는 문자로 나오게 된다.

1. input v-model속성을 만든다.

   ```html
   <input v-model.trim="number" />
   <p>{{ number }}</p>
   ```

- v-model.number는 입력값의 데이터의 타입을 숫자로 바꿔준다.
- v-model.trim은 입력값의 앞 뒤 공백을 제거해준다.
- 공백이 입력 됐을 때도 오류가 발생되도록 한다.

2. 데이터 정의

   ```javascript
   data() {
       return {
           number: 1, //데이터 초기화
       };
   },
   watch: {
       number(a) {
           if (isNaN(a) === true) {
               alert("숫자를 입력해주세요");
               this.number = 1;
           }
       }
   },
   ```

- isNaN(a) : 매개변수 a가 숫자가 아니면 true, 숫자이면 false로 반환해준다.
- alert가 뜨고 나면 number를 다시 1로 초기화해준다.
