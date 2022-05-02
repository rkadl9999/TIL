# SOP ( Same Origin Policy )

> 동일 출처 정책
> 

---

쿠키는 `클라이언트 브라우저`에 저장이된다.

예를 들어 사용자가 페이스북에 `로그인을 했던 상태`로 `악의적인 사이트에 접속`했다고 가정.

악의적인 사이트에서 페이스북에 `비밀번호를 변경하는 요청`을 보내는 버튼이 있는데

`(Ex. https://www.facebook.com/password=(공격자가 정한 특정 값) )`

이를 클릭했을 시에 자신의 페이스북 계정의 암호가 `공격자가 설정한 암호로 바뀌게 되는 피해`가 일어난다.

이를 막기 위해 나타난 정책이 `SOP` 이다.

> SOP 구분 방법
> 

---

Origin

1. `Protocol` = 프로토콜이 같은지 확인
2. `포트` = 포트 번호가 같은지 확인
3. `호스트` = 호스트가 같은지 확인

## CORS ( Cross Origin Resource Sharing )

> 출현 배경
> 

---

- 카페 : https://cafe.hyeonuk.com
- 블로그 : https://blog.hyeonuk.com
- 메일 : https://mail.hyeonuk.com
- 메인 : https://hyeonuk.com

이와 같이 `호스트가 다를 경우 SOP에 위반`된다.

이를 해결하기 위해 등장한게 `CORS`이다.