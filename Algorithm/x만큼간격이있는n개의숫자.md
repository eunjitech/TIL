# x만큼 간격이 있는 n개의 숫자

### 문제

_함수 solution은 정수 x와 자연수 n을 입력 받아, x부터 시작해 x씩 증가하는 숫자를 n개 지니는 리스트를 리턴해야 합니다. 다음 제한 조건을 보고, 조건을 만족하는 함수, solution을 완성해주세요._

- x는 -10000000 이상, 10000000 이하인 정수입니다.
- n은 1000 이하인 자연수입니다.

### my solution

```javascript
function solution(x, n) {
  let answer = [];
  for (var i = 0; i < n; i++) {
    let item = x + i * x;
    answer.push(item);
  }
  return answer;
}
```

### better solution

```javascript
function solution(x, n) {
  return Array(n)
    .fill(x)
    .map((v, i) => (i + 1) * v);
}
```

- 배열을 미리 정의해 놓은 뒤에 인덱스 값에 따라 곱하기

### 배열의 시작 인덱스부터 끝 인덱스까지의 이전까지 정적인 값으로 채우기

array.fill(채울값, [시작인덱스], [끝인덱스])

```javascript
const array1 = [1, 2, 3, 4];

// 0을 2인덱스값부터 4인덱스값까지
console.log(array1.fill(0, 2, 4));
//[1, 2, 0, 0]

// 5를 1인덱스값부터 채우기
console.log(array1.fill(5, 1));
//[1, 5, 5, 5]

//6을 채우기
console.log(array1.fill(6));
//[6, 6, 6, 6]
```

[x만큼 간격이 있는 n개의 숫자](https://programmers.co.kr/learn/courses/30/lessons/12954)
