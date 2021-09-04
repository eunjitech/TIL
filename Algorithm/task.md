# task

### 문제 1

- 중복된 숫자를 제외하고 각 값을 1번씩만 가진 배열을 높은순으로 정렬하여 반환하는 함수를 완성하세요.
- input : [[2,2,1],[0],[2,5,5],[3,5]]
- 반환 : [5, 3, 2, 1, 0]

### 문제 1 풀이

```javascript
function test(anyArray) {
  const flatArray = anyArray.flat(Infinity);
  const setArray = [...new Set(flatArray)];
  const answer = setArray.sort(function (a, b) {
    return b - a;
  });

  return answer;
}
```

1. 모든 중첩된 배열을 하나의 배열로 만들기 위해 flat함수에 Infinity옵션을 사용하였습니다.
2. 배열안에 중복된 요소값들을 제거하기 위해 [...new Set(array)]를 사용하였습니다.
3. sort()함수로 내림차순 정렬을 하였습니다.

- flat함수를 알아보기 위해 MDN 웹 문서를 참고하였습니다. <br>
  링크 : <https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Array/flat>

### 문제 2

- 넘어온 Date에서 날짜와 시간을 다음과 같은 포맷으로 반환하는 함수를 완성하세요.
- 입력 : console.log(test(new Date()))
- 반환 : 2021년 9월 3일 금요일 오후 09시 05분

### 문제 2 풀이

```javascript
function test(anyDate) {
  const dayName = ["일", "월", "화", "수", "목", "금", "토"];
  const targetYear = anyDate.getFullYear();
  const targetMonth = anyDate.getMonth() + 1;
  const targetDate = anyDate.getDate();
  const targetDay = dayName[anyDate.getDay()];
  const targetHours = anyDate.getHours();
  const targetMinutes = anyDate.getMinutes();

  const answer = `${targetYear}년 ${
    targetMonth < 10 ? `0${targetMonth}월` : `${targetMonth}월`
  } ${
    targetDate < 10 ? `0${targetDate}일` : `${targetDate}일`
  } ${targetDay}요일 ${targetHours < 12 ? `오전` : `오후`} ${
    targetHours == 0
      ? `12시`
      : targetHours < 10
      ? `0${targetHours}시`
      : `${targetHours}시`
  } ${targetMinutes < 10 ? `0${targetMinutes}분` : `${targetMinutes}분`}`;

  return answer;
}
```

1. 년도, 월, 일, 요일, 시, 분, 초를 나타내는 날짜 변수를 각각 정의하였습니다.
2. 템플릿 리터럴을 사용하여 결과값을 하나의 문자열안에 작성하였고, 입력된 시간에 따라 오전 또는 오후를 나타낼 수 있는 조건문을 사용하였습니다.
