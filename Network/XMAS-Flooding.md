# XMAS-Flooding

> XMAS Packet
> 

---

XMAS Packet이란 TCP flag 종류 모두 1로 세팅한 패킷을 말한다.

이러한 패킷은 비정상적인 패킷으로 취급된다.

> XMAS Flooding
> 

---

위에 설명한 거 처럼 XMAS Packet을 대량으로 서버에 보내서

정상적인 서비스를 방해하는 공격 기법이다.

공격원리

---

대표적인 예로 3way handshake으로 설명하자면,

3way handshake에는 주고받는 패킷들에 대한 규칙이 있는데

( 처음 패킷 = SYN, 두번째 = ACK, SYN / 등등 )

모든 플래그가 1로 세팅되있는 패킷을 받으면 서버가 막말로 당황하게 된다.

어떻게 처리할지 모르는 상황이기 때문에 패킷을 버리지 못하고 계속 손에 들고 버벅이게 된다.

이에 따라 서버의 처리가 느려지고 정상적인 서비스가 불가능 하도록 유도하는 공격이다.

잘 이해가 되지 않는다면 일상생활을 예로 들어보자,

> Example
> 

---

지금 현재 쓰레기 분리수거장에 서있는 상태이다.

분리수거장에는 각각 플라스틱, 종이, 캔으로 분류 할 수 있도록 나눠져있다.

여기서 저렇게 정해져있는 쓰레기를 버린다면 고민하지 않고 바로바로 버릴 수 있을 것이다.

하지만 여기서 갑자기 들고 간 쓰레기 봉투에서 노트북이 나왔다.

그러면 쓰레기를 쉽게 분리수거 하지 못하고 버벅이게 될 것이다.

오랜시간 붙잡고 있다가, 일단 놔두고 다른 쓰레기부터 분리하자고 생각했는데

계속 노트북이 나온다면 많이 당황하게 될 것이다.

위와 같은 것이 XMAS Flooding 의 매커니즘을 대충 설명한 것이다.

요즘 나오는 네트워크 장비들은

비정상적인 패킷들을 고민하지 않고 바로 버리게끔 만들어져 있기 때문에

서버 관리자라면 따로 이러한 공격으로 힘들어하지 않아도 될 거 같다.