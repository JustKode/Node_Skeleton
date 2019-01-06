# Node_Skeleton
Node 프로젝트를 위한 Skeleton Project 파일 입니다.

# Setup
Node.js 설치가 선행 되어야 합니다.

.env 파일을 통해서 환경변수를 설정 할 수 있습니다.
최상위 폴더에 .env 파일을 만들어 놓으면 됩니다. 아래는 예시입니다.
```
PORT=3000
SECRET_KEY=j8f3hnaa7db401und7
```

api 폴더에는 ```express.router``` 가 있습니다. ```module.exports```로 router 객체를 반환해서 ```express``` 객체의 middleware로 사용합니다.

```javascript
app.use('/api', require('./api'))
```

router 객체에 router 객체를 미들웨어로 사용 할 수 있습니다.
```
api
ㄴindex.js
ㄴuser
  ㄴindex.js
```
이러한 구조로 되어 있을 때, api/user/index.js에서 ```module.exports = router``` 를 한 후 api/index.js에서
```javascript
router.use('/user', require('./user'))
```
를 작성, ```http://localhost:<포트번호>/api/user/~~~``` 를 이용하여 api를 사용 할 수 있습니다.

실행 방법은 다음과 같습니다.

```bash
$ npm install
$ node app.js
```