# TCP(Transmission Control Protocol) UDP(User Datagram Protocol)
TCP와 UDP는 OSI 표준모델과 TCP/IP 모델의 전송계층에서 사용되는 프로토콜

cf) 전송계층 : 송신자와 수신자를 연결하는 통신 서비스 제공 및 IP에 의해 전달된 패킷 오류 검사

```
ㅇ TCP와 UDP 모두 '포트 번호'를 이용하여 어떤 Application에 데이터를 전달 할지 식별
ㅇ 포트 번호는 0 ~ 65535 까지의 숫자
ㅇ 0 ~ 1023은 well-known port => 웹 서버나 메일 서버 
ㅇ 1024 ~ 49151은 registered port, 49152 ~ 65525는 dynamic port 서버가 클라이언트를 식별하기위해 사용

```
### TCP(Transmisson Control Protocol)
TCP는 연결 지향형 프로토콜로, 연결 지향형 프로토콜이란 클라이언트와 서버가 연결된 상태에서 데이터를 주고 받는 프로토콜을 의미

#### TCP 3-way-handshake 방식 (SYN, ACK)
![3-way-handshake](https://user-images.githubusercontent.com/86729396/166445231-d8981d9a-3b36-4c8e-a920-0a28c6db97ad.jpg)

1. Client에서 Server에 연결 요청을 하기위해 SYN 데이터를 보낸다.
2. Server에서 해당 포트는 LISTEN 상태에서 SYN 데이터를 받고 SYN_RCV로 상태가 변경된다.
3. 그리고 요청을 정상적으로 받았다는 대답(ACK)와 Client도 포트를 열어

클라이언트가 연결 요청(SYN)을 하고, 서버가 연결을 수락하면 모든 데이터는 고정된 선로를 따라 순차적으로 전달 된다. 이를 통해 호스트간 신뢰성 있는 데이터 전달과 흐름제어를 한다.

