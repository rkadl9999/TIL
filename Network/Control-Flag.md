# Control flag

> TCP 제어 플래그 ( Control flag )
> 

---

각 플래그는 1Bit 씩 소비한다.

- Synchronization ( SYN )

두 호스트간 연결을 시작하기 위한 신호 , 3-way handshake 첫번째 단계에 사용

- Acknowledgement ( ACK )

상대방으로부터 패킷을 받았다는 것을 알려주는 신호이다.

- Finish ( FIN )

커넥션 종료 요청으로 , 보낼 데이터가 없을 시에 sender가 마지막 패킷을 보낸다.

- Reset ( RST )

TCP 연결에 문제가 있다고 판단될 시, 연결을 종료하는 신호를 보낸다. ( 초기화 )

- Push ( PSH )

채팅과 같이 빠른 응답을 요하는 서비스에서 사용되는 요청, 버퍼링이 없다.

- Urgent ( URG )

긴급성을 가지는 데이터로 간주 , URG가 1로 세팅되면 맨 앞으로 보내진다.