# 오류날 시 질문 방법
* 질문하기 위해 질문하지 말고 그냥 질문하세요.
  - 안좋은 예시) **오류가 나는데 이거 도와주실수 있으신분 있나요?** `❌`
  - **코드와 함께 오류를 보여주세요.** 이때 주의할점은 전체 코드와(토큰같이 민감한 부분은 가리고 질문해주셔도 상관없어요) 오류를 주셔야합니다.
  - 또한 디스코드의 [ToS](https://discord.com/terms)를 위반하는 질문(복구봇, 자판기) 등등의 질문은 삼가해주세요.

# 자주 실수하는 오류들
## 1. 인텐트 문제
  * 위와 같은 오류는 인텐트 문제는 **인텐트를 선언해주시지 않으셔서** 생기는 오류입니다.
  * 해결 방법은 다음과 같습니다. `👇`
  ### 1. 웹사이트에서 켜기
  * [디스코드 디벨로퍼 포탈](https://discord.com/developers/applications) 들어가셔서,
  * 자신의 봇에 들어가셔서 왼쪽의 `Bot`탭을 눌러서 아래로 내리면 **Privileged Gateway Intents**가 있는데, 그곳에서
  ```
  PRESENCE INTENT
  SERVER MEMBERS INTENT
  MESSAGE CONTENT INTENT
  ```
  * `👆️` 위의 권한 3개를 모두 켜주셔야 합니다.
  ### 2. 코드에서 켜기
  ```py
  INTENTS = discord.Intents.default()
  INTENTS.권한 = True
  client = discord.Client(intents = INTENTS)
  ```
  * 이런식으로 하나씩 권한을 추가해도 됩니다.
  ```py
  INTENTS = discord.Intents.all()
  client = discord.Client(intents = INTENTS)
  ```
  * 저는 위에 과정을 더 선호하는 편입니다.
  - 웹사이트와 코드에서 **모두** 켜야하며,
  - 더 자세한 오류 해결 방법은 [여기](https://discordpy.readthedocs.io/en/stable/intents.html)에서 확인해주세요.
## 2. **모듈 미설치 오류**
* pass