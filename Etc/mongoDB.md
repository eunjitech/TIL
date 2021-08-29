# mongoDB 연결하기

### mongoDB에서 데이터베이스생성

[링크참조](https://eunjitech.notion.site/Database-7b71750772b14dfa9ec8c0b35a0bcf89)

### mongoose 설치

`npm i mongoose --save`

### mongoose 연결

기본셋팅구조

```javascript
const mongoose = require("mongoose");

mongoose
  .connect("몽고URL", {
    useNewUrlParser: true,
  })
  .then(() => {
    console.log("DB연결성공");
  })
  .catch((err) => console.error(err));
```

- useNewUrlParser는 mongoose에서 이 설정을 계속 묻기 때문에 미리 설정한다.

### User Model Schema생성

mongoose를 이용해 데이터 모델을 생성한다. 우선 models폴더를 하나 생성하여 그 곳에 스키마를 정의해본다.

스키마 타입 정의

```javascript
const mongoose = require("mongoose");

const userSchema = mongoose.Schema({
  name: {
    type: String,
    maxlength: 10,
    required: true,
  },
  email: {
    type: String,
    trim: true,
    unique: true,
  },
});

const User = mongoose.model("User", userSchema);

module.exports = { User };
```

- type은 필수 요소이고, 그 밖의 옵션들을 정의할 수 있음
- name의 최대길이를 10으로 제한함
- email은 유일해야하므로 unique: true를 주었음
- [이밖에 여러 가지 스키마 옵션](https://mongoosejs.com/docs/schematypes.html)
