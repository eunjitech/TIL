# OR(||) AND(&&) 연산자

- 기본 세 연산자의 반환값은 true 또는 false
- 경우에 따라 피연산자를 반환하기도 함

### OR연산자 (||)

첫번째 truthy를 찾는 연산자

```javascript
alert(1 || 0); //1
alert(0 || null || 1); //1
alert(0 || null || undefined || 0); //0(마지막)
```

- 왼쪽 -> 오른쪽 방향으로 피연산자를 읽음
- 피연산자가 true면 연산을 멈추고 해당 피연산자를 반환함
- 모든 피연산자가 false일 경우에 마지막 피연산자를 반환함

### AND연산자 (&&)

첫번째 falsy를 찾는 연산자

```javascript
alert(1 && 0); // 0
alert(1 && 5); // 5
```

- 모든 피연산자가 true일 경우 마지막 피연산자 반환

### ?? || 차이

- ||는 첫번째 truthy값을 반환
- ??는 첫번째 정의된 값을 반환

```javascript
let height = 0;

alert(height || 100); // 100
alert(height ?? 100); // 0
```

- null 병합 연산자인 ??연산자를 사용하면 값이 할당된 변수를 찾을 수 있음
