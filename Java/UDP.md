- 편지와 같은 방식으로 상대방이 데이터를 받을 준비가 되었는지 확인하지 않고 데이터를 무조건 보낸다
- 데이터를 잃어버릴 수 있어 신뢰성이 낮다
- 항상 네트워크에 연결되지 않아도 되어 네트워크 부담이 낮다

- UDP방식 통신을 위한 클래스
	- DatagramSocket
	- DatagramPacket

- UDP 방식의 통신 프로그래밍 절차

| Receiver                               | Sender                                 |
| -------------------------------------- | -------------------------------------- |
| 1. DatagramSocket을 생성               | DatagramSocket을 생성                  |
| 2. 데이터를 받을 DatagramPacket을 생성 | 데이터를 받을 DatagramPacket을 생성    |
| 3. receive 메소드를 통해 데이터를 받는다  | send 메소드를 호출하여 데이터를 보낸다 |
| 4. DatagramSocket을 닫는다 | DatagramSocket을 닫는다 |

