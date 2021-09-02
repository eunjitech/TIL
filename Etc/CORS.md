# CORS

### CORS란?

Cross-Orgin Resource Sharing의 약자로 다른 도메인 서버에 요청을 할 때, 보안 이슈로 인해 접근할 수 없게 만든 보안 정책

### 해결법

_proxy란 클라이언트가 다른 네트워크에 간접적으로 접속할 수 있게 해주는 중계서버_

1. proxy middleware <br>
   <https://create-react-app.dev/docs/proxying-api-requests-in-development/> - Configuring the Proxy Manually 참고

2. client package.json 에서 proxy 설정 <br>
   `"proxy":"접근할주소"`

3. backend에서 proxy 설정 <br>
   `npm i cors --save` 설치

cors 선언 후 옵션 선택

```javascript
import cors from "cors";

const cors_origin = ["http://localhost:5000", "http://localhost:3000"];

app.use(
  cors({
    origin: cors_origin, //허락할 요청주소
    credentials: true, //true시 설정한 내용을 response헤더에 추가
  })
);
```
