## TCP 3-way Handshake 

- Clinet-Server 사이 논리적인 접속을 성립(establish)하기 위하여 3-way handshake를 사용한다.
- TCP/IP 프로토콜을 이용해 통신을 하는 응용프로그램이 데이터를 전송하기 전에 `정확한 전송`을 보장하기 위해 사전에 세션을 수립하는 과정
  - 데이터 전송한 준비가 되어있꼬, 데이터 전달전 다른 쪽이 준비되었다는 것을 알 수 있도록 함.

1. Client > Server : **TCP SYN**

2. Server > Client : **TCP SYN, ACK**

3. Client > Server : **TCP ACK**

   `* syn :synchronize sequence numbers,  요청`

   `* ACK : acknowledgment, 요청 확인` 



![img](https://blog.kakaocdn.net/dn/bNwPCT/btqD0hCftBa/4fUpGdt1ddNBtk9RGmfKw0/img.png)



 

### TCP의 3-way Handshaking 과정

1. 클라이언트 -> 서버로 SYN 패킷 전송
   - 클라이언트는 SYN을 보내고 SYN/ACK 응답을 기다리는 `SYN_SENT`
   - 서버는 `Wait for Client` 상태

2. 서버는 SYN 요청을 받고, 클라이언트에게 요청을 수락한다는 ACK + SYN Flag가 설정된 패킷 발송,
   서버가 다시 ACK로 응답하기를 기다림.
   - 서버는 `SYN_RECEIVED` 상태

3. 클라이언트는 서버에게 ACK를 보내고, 이후로부터는 연결 성립되어 데이터 전송
   - 서버 상태가 ESTABLISHED





`*참고 사이트`

[티스토리](https://bangu4.tistory.com/74)

