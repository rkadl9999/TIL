# OSI 7 layer

## OSI 7계층

---

물리 계층

---

- 전송 단위 : 0,1 비트
- 각 프로토콜의 역할 : RS-232 = PC와 모뎀 등을 접속하는 직렬 방식 인터페이스 역할이다.
X.25 = DTE, DCE간의 인터페이스를 제공해주는 역할이다.

데이터 링크 계층

---

- 전송 단위 : Frame
- 각 프로토콜의 역할 : PPP = 서로 다른 업체의 소프트웨어들을 TCP/IP로 통신 가능하도록 만든 규약
MAC = 공유된 채널에 다수의 사용자가 접속할 수 있도록 도와주는 프로토콜

네트워크 계층

---

- 전송 단위 : Packet
- 각 프로토콜의 역할 : IP = 네트워크에서 장치들이 통신을 하기위해 사용하는 번호.
ICMP = 여러 정보를 전달 OR 컨트롤하는 역할이다.

전송 계층

---

- 전송 단위 : TCP : Segment / UDP : Datagram
- 각 프로토콜의 역할 : TCP = 연결형 서비스를 지원, 인터넷에서 기본으로 사용
UDP = 비연결형 서비스를 지원, 일방적으로 데이터를 전달

세션 계층

---

- 전송 단위 : Message
- 각 프로토콜의 역할 : SSL = 데이터를 안전하게 전송하기 위한 인터넷 암호화 통신 프로토콜 ( 443번 = HTTPS )
TLS = 여러가지 인증을 제공하는 것, SSL에서 업그레이드 된 버전. ( 443번 )

표현 계층

---

- 전송 단위 : Message
- 각 프로토콜의 역할 : JPEG = 사진을 위해서 만들어진 손실 압축 방법.
ASCII = 아스키코드, 문자를 숫자로 표현하는 인코딩 기법

응용 계층

---

- 전송 단위 : Message
- 각 프로토콜의 역할 : HTTP = 웹에서 사용되는 프로토콜, TCP와 UDP 사용 ( 80번 )
FTP = 컴퓨터끼리 파일을 주고받는데 사용되는 프로토콜 ( 21번 )
