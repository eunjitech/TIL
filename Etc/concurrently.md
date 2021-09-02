# concurrently

서버와 클라이언트를 동시에 실행(여러개의 명령어를 동시에 실행)시킬 수 있는 라이브러리

server

```json
"scripts": {
    "backend": "NODE_ENV=development nodemon --exec babel-node server/index.js --delay 2",
    "dev": "concurrently \"npm run backend\" \"npm run start --prefix client\""
  },
```

client

```json
"scripts": {
    "start": "react-scripts start",
  },
```

- 두개의 명령어를 각각 실행하지 않고 **"concurrently \"명령어\" \"명령어\" "** 와 같이 입력해주면 다른 package.json에 있는 명령어도 동시에 실행할 수 있음
- 찾고자 하는 명령어의 경로가 바깥에 있을 때는 **cd ../폴더**
