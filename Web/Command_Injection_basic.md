# Command Injection

## 커맨드 인젝션 이란?

---

웹에서 시스템 명령을 사용하는 경우에

;( 세미콜론 ) 또는 &을 사용하여 두개의 커맨드가 실행되도록 하는 공격이다.

예를 들어보면,

어느 웹 사이트에 서버에 저장된 파일 내용을 읽을 수 있는

서비스가 구축되어 있다고 가정해보자

서비스 일부분에 system(”cat $var”) 라는 함수가 있다고 가정하고

var 변수에 사용자가 입력한 값이 들어가서 파일 내용을 볼 수 있도록 만들었을 때

정상적인 사용자가 

<aside>
⌨️ file.txt

</aside>

라고 입력했을 때는 개발자가 의도한대로 파일이 내용만이 출력 되겠지만,

공격자가 ( 리눅스는 ; (세미콜론) 으로 끊고 또 다른 명령 실행가능 )

<aside>
⌨️ file.txt; ifconfig

</aside>

라고 입력했을 때, 서버의 주요 정보 중 하나인 ip가 유출될수도 있는 상황이 생긴다.

이와 같이 여러개의 커멘드를 인젝션 하는 공격 기법이 Command Injection 공격이다.

> 대응책
> 

---

사실상 공격의 핵심인 세미콜론이나 & 등을 사용하지 못하도록

필터링을 하거나 공백들을 입력하지 못하도록 필터링을 하는 방법이 있다.

또한 다른 주요 정보를 보지 못하도록

특정 부분 외에는 읽기 권한을 막아두는 것도 좋을거 같다.
