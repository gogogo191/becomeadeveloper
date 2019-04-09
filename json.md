어떠한 데이터를 *요청* 한다고 해서 Request이고, 그 *요청* 에 대한 *응답* 이기 때문에 Response 죠
이 요청과 응답 간에는 다양한 내용이 포함될 수 있는데요
가정을 해봅시다
업글에서 최고의 멘토를 추천해달라는 요청을 서버쪽으로 보내기로 했어요
응답으로 선생님들의 리스트가 오겠죠
만약 일반 텍스트로 이 선생님들의 정보를 전송한다면 어떻게 될까요?

```
이름: 용준이형
나이: XX
특기: 
  A
  B
  C
  등등등

이름: 구딩
나이: XX
특기:
  A
  B
  C
  ```
특기 안에 또 계층화된 정보가 생긴다면?
또 표현하기가 어려워집니다
이런 이유 때문에 정보를 요청할때나 응답할때나
전송하는 데이터들의 특수한 포맷이 생겨났어요
첫번째는 xml입니다


대충 이런 포맷을 가진
HTML이랑 비슷한 형식을 지닌 마크업이었어요
지금도 이 포맷은 여러 플랫폼에서 요청과 응답 등 전송에 많이 사용되고 있습니다
그런데 XML은 무슨 문제가 있을까요?

believer 김용준 [10:30 PM]
음

Koo 구동현 [10:31 PM]
계층화된 데이터를 표시하는데는 별 문제가 없어보입니다
그런데 쓸데없는 문자들이 많죠
Opening tag가 있으면 반드시 Closing tag가 존재해야하고
반복된 엘리먼트들이 계속 등장해도 Opening tag & Closing tag
를 계속해서 써줘야합니다


``` 
<?xml version="1.0" encoding="UTF-8"?>
<note>
  <to>Tove</to>
  <from>Jani</from>
  <heading>Reminder</heading>
  <body>Don't forget me this weekend!</body>
  <body>Don't forget me this weekend!</body>
  <body>Don't forget me this weekend!</body>
  <body>Don't forget me this weekend!</body>
  <body>Don't forget me this weekend!</body>
</note>
 ```

이런식으로요
전송하는 데이터의 양이 많다는 것은 네트워크 트래픽의 증가를 의미하죠
불필요한 트래픽의 증가는 소모적입니다
그래서 최근 많이 사용되는 것이 JSON이예요

위에서 XML이 불필요한 데이터를 함께 전송해야하는 불편함이 있다는 걸 얘기했는데
이는 트래픽의 증가 뿐만 아니라 해석 속도에도 영향을 미칩니다
데이터가 커질수록 파싱하는 시간이 더 오래 걸리는거죠


그래서 나온게 JSON인데
JavaScript Object Notation입니다
JS에서 Object를 표현하는 방식을 데이터 전송에 차용한거라고 생각하시면됩니다

```
{
  note: {
    to: "Tove",
    from: "Jani",
    heading: "Reminder",
  }
}
```

아까 들었던 예시가 이런식으로 치환되는겁니다
당연히 JSON 자체는 JavaScript Object와 유사한 형태를 띕니다
정확히는 JavaScript Object의 subset이라고 볼 수 있어요
JSON 자체는 JS에서 차용했지만 언어에 국한되는 데이터 포맷이 아닙니다

따라서 Function 같은 것을 담아서 보낼 순 없어요

문자로 표현이 되는 데이터만 전송이 가능해요

Function을 스트링으로 만들어서 전송은 가능하지만 그 Function이 가지는 의미는 잃는다는거죠
```
 const data = JSON.stringify({id: '200'});  
 ```
JS에 내장된 JSON을 처리할 수 있게 해주는 모듈이예여

JSON.stringify가 있고
JSON.parse가 있어요
JSON.stringify는 입력으로 JS Object를 받아요
그리고 그 Object를 string으로 변환한 값을 뱉어줘요
왜 이런게 필요할까요?
왜냐면 전송의 매개체인 HTTP는 JS Object를 모르니까!

HTTP는 왕복 버스라고 생각하시면 돼요
스쿨버스가 좋겠다
HTTP가 알아볼 수 있는애만 버스에 탈수있어요
HTTP는 JS를 몰라요 왜냐면 언어에 관계없이 정립된 네트워크 전송 표준이라
그래서 HTTP가 문자열은 아니까 그걸로 바꿔서 보내주는거죠 포맷만 맞춰가지고
다른 옷을 입혀서
JSON.parse는 반대예여
버스에서 내린 애를 붙잡아서JS Object로 바꿔버려요

HTTP는 JSON도 알고 XML도 알고 String도 알지만 (Raw string 등으로 표현함)
JS Object는 모른다는것!

그리고 HTTP가 아는애들은 전부 문자열로 이루어진 데이터라는 것