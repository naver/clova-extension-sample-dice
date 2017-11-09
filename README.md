### 개요 
'주사위 놀이'라는 Clova extension의 REST API 서버 소스 코드입니다. '주사위 놀이' 익스텐션이 어떻게 작동하는지 보시려면, Clova 앱이나 Clova 스피커(WAVE, Friens)에서 '주사위놀이 시작해줘'라고 해보시길 바랍니다. 해당 익스텐션을 실행하면 주사위 굴린 결과 값을 알려주며, 주사위는 1개부터 10개까지 굴릴 수 있으며, 2개 이상인 경우는 그 결과의 합을 알려 줍니다. 

### 사용환경
'주사위 놀이'라는 Clova extension의 REST API 서버는 node.js로 구현되어 있습니다.  Windows, MacOS, Linux 등 node.js 가 구동 가능한 OS면 실행 가능하며, 구체적인 목록들은 여기를 참고하셔서, node.js를 먼저 설치하시길 바랍니다. https://nodejs.org/ko/download/current/

### 설치방법
'주사위 놀이' REST API 서버 소스 코드 설치는 다음과 같이 해주시길 바랍니다.
1) node.js 설치: https://nodejs.org/ko/download/current/
2) 소스코드 다운로드: git clone  https://github.com/naver/clova-extension-sample-dice.git 
3) 의존성 라이브러리 설치: npm install 

### 사용법 
'주사위 놀이'라는 Clova extension의 REST API 서버는 Clova platform으로부터의 익스텐션 요청에 따라 적절한 응답을 하도록 되어 있습니다. API 서버를 실행을 하더라도, Clova platform이 보내는 것과 동일한 API 요청을 해주셔야 정확하게 작동하는 점 참고 바랍니다. 실제 서비스를 위해서는 https 기반으로 외부에서 접근 가능한 도메인으로 해주셔야 합니다.
- API 서버 실행: node app.js 
- API 서버 테스팅: Postman에서 아래와 같이 json Request를 전송하고 json이 리턴되는지 테스트 해봅니다.
	- URL: http://localhost:3000/clova
	- 요청 방법: POST 
	- Body: raw ( JSON 선택 ) 
- 요청 예시)
```
{
  "version": "0.1.0",
  "session": {
    "sessionId": "55ca6ee4-72dd-4694-b30f-4b49e238634f",
    "user": {
      "userId": "f5gYL1uYQyuXoYNvV6-BCw",
      "accessToken": "3d0e7bab-2c1a-44d4-be20-c84910b78e2c"
    },
    "new": true
  },
  "context": {
    "System": {
      "user": {
        "userId": "f5gYL1uYQyuXoYNvV6-BCw",
        "accessToken": "3d0e7bab-2c1a-44d4-be20-c84910b78e2c"
      },
      "device": {
        "deviceId": "3657ade7-e219-4a76-84c4-b701bae8350c"
      }
    }
  },
  "request": {
    "type": "IntentRequest",
    "intent": {
      "name": "ThrowDiceIntent",
      "slots": {
        "diceCount": {
          "name": "diceCount",
          "value": "1"
        }
      }
    }
  }
}
```

![image](http://static.naver.net/clova/service/native_extensions/example/dice.png)

### 라이선스
Naver & Line corp.

[LICENSE](https://github.com/naver/clova-extension-sample-dice/blob/github-public/LICENSE)

```
Copyright 2018 NAVER Corp. & LINE Corporation

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```

