# 4-way Handshaking

- 3-way handshake로 연결 성립 후 4-way handshake로 세션 종료

  



![img](https://blog.kakaocdn.net/dn/qUXSw/btqDWsFNWJw/hVdKIneSYb7UK3wc0pj6Z0/img.png)



 

 ## TCP의 4-way Handshaking 과정 

1. 클라이언트 -> 서버로 연결 종료 하겠다는 FIN플래그 전송
   - 클라이언트는 `FIN-WAIT` 상태

2. 서버는 FIN플래그를 받고, 확인 메시지 ACK를 보낸 후 자신의 통신이 끝날 때까지 기다림.
   - 이때 서버는 `CLOSE-WAIT`상태
3. 연결을 종료할 준비가 되면, 연결해지를 위한 준비가 되었음을 알리기 위해 클라이언트에게 FIN플래그를 전송
   - 서버는 `LAST-ACK` 상태

4. 클라이언트가 ACK 확인 메시지 전송
   - 클라이언트 상태는 `FIN-WAIT` -> `TIME-WAIT`으로 변경



`* 서버에서 FIN 전송 이전 전송한 패킷이 Routing 지연이나 패킷 유실로 인한 재전송 등으로 FIN 패킷보다 늦게 도착하는 것을 방지 하기 위해
 클라이언트는 서버로부터 FIN을 수신하더라도 일정시간(디폴트 240초) 동안 세션을 남겨놓고 잉여 패킷을 기다리는 과정을 거치게 되는데 이 과정을 "TIME_WAIT" 일정시간이 지나면, 세션을 만료하고 연결을 종료시키며, "CLOSE" 상태로 변화합니다. `
