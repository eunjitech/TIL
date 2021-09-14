# ajax

### ajax 정의

AJAX란 Asynchronous JavaScript And XML의 약자로, 서버와 통신하기 위해 XMLHttpRequest 객체를 사용하는 것을 말한다. XML 뿐 만 아니라 JSON, HTML, 텍스트 등 다양한 포맷의 데이터를 주고 받을 수 있다.

### ajax 구현 - XMLHttpRequest

```javascript
const xhr = new XMLHttpRequest();
xhr.open("POST", url);
xhr.responseType = "json";
xhr.setRequestHeader("Content-type", "application/json; charset=UTF-8;");
xhr.onload = function (e) {
  if (this.status == 200) {
    alert("성공");
  }
};
xhr.send(JSON.stringify(data));
```

### ajax 구현 - fetch

```javascript
fetch(url)
  .then((response) => {
    return response.json();
  });
  .then((myJson) => {
    console.log(JSON.stringify(myJson));
  })
  .catch((error) => {
    console.err(error);
  });
```

출처 : [https://aljjabaegi.tistory.com/520], []
