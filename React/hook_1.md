# React Hook

react hook은 react의 클래스 형식의 컴포넌트에서만 사용할 수 있었던 **state관리를 함수 형태의 컴포넌트에서도 사용**할 수 있게 만들어주는 기능입니다.

hook은 **1.코드가 간결해지며 2.상태 관련 로직을 재사용할 수 있다.**

---

- [React Hook](#react-hook)
  - [useState](#usestate)
  - [useInput](#useinput)

## useState

- useState는 배열형식으로 되어있다.
- const[변수, 함수] = useState(초기화값) 으로 state를 생성해준다.

```javascript
import React, { useState } from "react";

const App = () => {
  const [item, setItem] = useState(1);
  const incre = () => {
    setItem(item + 1);
  };
  const decre = () => {
    setItem(item - 1);
  };

  return (
    <div className="App">
      <h1>{item}</h1>
      <button onClick={incre}>+</button>
      <button onClick={decre}>-</button>
    </div>
  );
};

export default App;
```

## useInput

- input을 업데이트 해준다.

```javascript
const useInput = (initialValue, validator) => {
  const [value, setValue] = useState(initialValue);
  const onChange = (e) => {
    console.log(e.target);

    //검증부분
    let willUpdate = true;
    if (typeof validator === "function") {
      willUpdate = validator(value);
    }
    if (willUpdate) {
      setValue(value);
    }
  };
  return { value, onChange };
};
```

- useInput은 initialValue의 인자값을 받는다.

```javascript
const App = () => {
  const maxLen = (value) => value.length <= 10; //검증조건
  const name = useInput("eunji", maxLen);

  return (
    <div className="App">
      <h1>Hello</h1>
      <input placeholder="이름" {...name} />
    </div>
  );
};
```

- {...name}은 name.value, name.onChange와 같다.
